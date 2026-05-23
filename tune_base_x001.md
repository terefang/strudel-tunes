```js

register('acidenv', (x,pat) => pat.lpf(100)
  .lpenv( x * 9 ).lps(.2).lpd(.12)
)
setcpm(160/3)

$: s("< bd:2 sd:2 >*2")
  .struct("<1 0 0 0 1 0 1 1>*12")
  //.acidenv(slider(0.4,-1,1,.1))
  .o(2)
  .gain(slider(0.601,.1,1.1))
  .room(slider(0.5769,.1,2))
  .delay(slider(0.0435,.0,.25))
  ._scope()

  ```
