```js

/*
  @title   a structure in sound
  @by      DJ_Terefang
  @license CC0
*/

register('acidenv2', (x,xs,xp,xf,pat) => pat.lpf(xf)
  .lpenv( x * 9 ).lps(xs).lpd(xp)
)
setcpm(160/8)

// Melody
$: note("C").s("bytebeat").struct("<1 1 1 1> <1 1 ~ 1> <1 1 1 ~> <1 ~ 1 1> <~ 1 1 1> <1 ~ 1 ~> <1 ~ ~ 1> <~ 1 ~ 1> <~ ~ 1 1>")
  .acidenv2(
    slider(0.51,0,2,.01),
    slider(0.21,0,1,.01),
    slider(0.139,0,.5,.001),
    slider(36,0,200,4)) 
  .delay(slider(0.51,0,2,.01))
  .room(slider(1.1,0,2,.1))
  .gain(slider(0.6,0,2,.1))
  ._scope()
$: s("bd*16").n("1 2 1 3")
  .delay(slider(1.18,0,2,.01))
  .room(slider(0.6,0,2,.1))
  .gain(slider(0.1,0,2,.1))
  ._scope()
  $: s("kawai*4").note("c# f a e#")
  .delay(slider(1.18,0,2,.01))
  .room(slider(0.7,0,2,.1))
  .gain(slider(0.2,0,2,.1))
  ._scope()

```
