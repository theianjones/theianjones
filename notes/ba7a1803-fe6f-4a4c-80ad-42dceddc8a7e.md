---
id: ba7a1803-fe6f-4a4c-80ad-42dceddc8a7e
title: Security
desc: ''
updated: 1607456164467
created: 1607455811896
parent: 91cff2b3-1121-41f0-aefd-06a6d7e80111
children: []
fname: cli.security
hpath: cli.security
---
# `security`

On macs, you can access values on your keychain through the `security` command. To add a value you can run:

```sh
security add-generic-password -a "$USER" -s "SOME_KEY_NAME" -w "some-secret-value"
```

To access this value, run:

```sh
security find-generic-password -a "$USER" -s "SOME_KEY_NAME" -w
```

You can then export these specific values in your `.zshrc` or `.bash_profile` like so:

```sh
export SOME_KEY_NAME=$(security find-generic-password -a "$USER" -s "SOME_KEY_NAME" -w)
```

Then in a some dot file file you can reference this value like in a `.npmrc`

```
//npm.remix.run/:_authToken=${SOME_KEY_NAME}
```

