---
id: ccf25afb-a122-4920-acea-ade2cb22b572
title: Clojure
desc: ''
updated: 1607119597544
created: 1607033721392
stub: true
parent: ef5162eb-1f61-4878-a1c5-c9a776726629
children:
  - 2de363d3-7d29-4f84-9614-e9a305da35d9
fname: lang.clojure
hpath: lang.clojure
---
## Functions



<div class="portal-container">
<div class="portal-head">
<div class="portal-backlink" >
<div class="portal-title">From <span class="portal-text-title">lang.clojure.func.slurp</span></div>
<a href="83e4d120-7d0b-4a4d-988c-d2deeb3581df.html" class="portal-arrow">Go to text <span class="right-arrow">→</span></a>
</div>
</div>
<div id="portal-parent-anchor" class="portal-parent" markdown="1">
<div class="portal-parent-fader-top"></div>
<div class="portal-parent-fader-bottom"></div>        
  
```clojure
(defn Example []
   (def string1 (slurp "Example.txt"))
   (println string1))
```



</div>    
</div>




<div class="portal-container">
<div class="portal-head">
<div class="portal-backlink" >
<div class="portal-title">From <span class="portal-text-title">lang.clojure.func.partial</span></div>
<a href="25876a61-5dc8-4b6a-8ceb-d1897d6e530a.html" class="portal-arrow">Go to text <span class="right-arrow">→</span></a>
</div>
</div>
<div id="portal-parent-anchor" class="portal-parent" markdown="1">
<div class="portal-parent-fader-top"></div>
<div class="portal-parent-fader-bottom"></div>        
  
```clojure
(def add-5 (partial + 5))
(add-5 10)
; 15
```



</div>    
</div>




<div class="portal-container">
<div class="portal-head">
<div class="portal-backlink" >
<div class="portal-title">From <span class="portal-text-title">lang.clojure.func.interleave</span></div>
<a href="aebace56-ddfb-4f76-828e-d1fdd3f514ca.html" class="portal-arrow">Go to text <span class="right-arrow">→</span></a>
</div>
</div>
<div id="portal-parent-anchor" class="portal-parent" markdown="1">
<div class="portal-parent-fader-top"></div>
<div class="portal-parent-fader-bottom"></div>        
  
Turn an array of keys and an array of values into a map:

```clojure
(apply assoc {}
   (interleave [:fruit :color :temp]
               ["grape" "red" "hot"]))
```



</div>    
</div>

