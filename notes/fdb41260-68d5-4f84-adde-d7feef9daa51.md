---
id: fdb41260-68d5-4f84-adde-d7feef9daa51
title: Alfred
desc: ''
updated: 1608057628079
created: 1608056646130
parent: 7d3efa53-c72c-4277-972c-7424e29353c1
children: []
fname: p.alfred
hpath: p.alfred
---
# Alfred

## Workflows

### Call applescript from a hot key

Open up Alfred's Preferences and navigate to the `Workflows` tab.

Now we are going to create a `blank workflow`.

![](/assets/images/2020-12-15-13-26-47.png)

It will ask for a name, the script I'm using finds a url in your browser and focuses that tab so we'll call it "Focus Github".

Now that the workflow is created, right click and add a `Trigger` for this workflow.

![](/assets/images/2020-12-15-13-29-26.png)

Click on the trigger and add the hotkey you want to use to kick the workflow off. I'm using `OPT+CTRL+G`.

Now we'll add an action off of this trigger.

Right click the trigger, hover actions, and select Run NSAppleScript.

![](/assets/images/2020-12-15-13-31-41.png)

This is where we will add our applescript:

```applescript
on alfred_script(q)
  set _win to false
  tell application "Microsoft Edge Dev"
    set {idList, urlList} to {id, URL} of every tab of every window
  end tell

  set AppleScript's text item delimiters to return

  if (urlList as text) contains "https://github.com" = true then
    set theWin to 1
    repeat with i in urlList
      set theTab to 1
      repeat with n in i
        if n starts with "https://github.com" then
          set {_win, _tab} to {theWin, theTab}
        end if
        set theTab to theTab + 1
      end repeat
      set theWin to theWin + 1
    end repeat
  end if

  if _win ≠ false then
    tell application "System Events"
      if quit delay ≠ 0 then set quit delay to 0
      tell process "Microsoft Edge Dev"
        perform action "AXRaise" of window _win
      end tell
    end tell
    tell application "Microsoft Edge Dev"
      tell front window to set active tab index to _tab
    end tell
  else
    tell application "Microsoft Edge Dev"
      set newWin to make new window
      tell newWin to set URL of active tab to "https://github.com"
    end tell
  end if
end alfred_script
```

Click save an now you can use your new hotkey to open github. This script will look for a tab with the url of `https://github.com` and focus that one or create a new one if its not found.

