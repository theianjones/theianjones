---
id: aebace56-ddfb-4f76-828e-d1fdd3f514ca
title: Interleave
desc: ''
updated: 1607009254824
created: 1606958219705
parent: 2de363d3-7d29-4f84-9614-e9a305da35d9
children: []
fname: lang.clojure.func.interleave
hpath: lang.clojure.func.interleave
---
Turn an array of keys and an array of values into a map:

```clojure
(apply assoc {}
   (interleave [:fruit :color :temp]
               ["grape" "red" "hot"]))
```

