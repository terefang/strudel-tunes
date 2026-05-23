```js
/*
  @title   break junking
  @by      DJ_Terefang
  @license CC0
*/
samples('github:switchangel/breaks')

register('acidenv2', (x,xs,xp,xf,pat) => pat.lpf(xf)
  .lpenv( x * 9 ).lps(xs).lpd(xp)
)


setcpm(160)

// Melody
let notes = "<G G G G G> <A D C F C> <C# C# D# E# C#> <- F - H ->"
let notes1 = "<C C C G G A# A#>"
let notes2 = "<C# C# A# C# C# A# C#>"
//let notes = "C H I C K E N"
//;

_$: s("9000_cb*4").note(notes)
    .acidenv2(
    slider(0.93,0,2,.01),
    slider(0.13,0,1,.01),
    slider(0.17,0,.5,.001),
    slider(104,0,200,4)) 
  .delay(slider(0.4,0,2,.01))
  .room(slider(1.7,0,2,.1))
  .gain(slider(0.2,0,2,.1))
  ._scope()
$: s("breaks/8").fit()
  .o(2)
  ._scope()
$: s("sine*4")
    //.scale("d:minor")
    .note("[ <A A A C> <C C D F> ] [ <D D D C> <H H F H> ]")
//    .fmwave("<sine square sawtooth square>")
    .fm(slider(0.282,0,5,.001))
    .fmh(slider(10,0,10,.001))
    .o(2)
  .delay(slider(0.12,0,2,.01))
  .room(slider(0.3,0,2,.1))
    .gain(slider(0.587,0,2.5,.001))
    ._scope()

$: s("supersaw*4").note(notes)
    .acidenv2(
    slider(0.43,0,2,.01),
    slider(0.78,0,1,.01),
    slider(0.052,0,.5,.001),
    slider(128,0,200,4)) 
  .delay(slider(0,0,2,.01))
  .room(slider(0.1,0,2,.1))
  .gain(slider(0.2,0,2,.1))
  ._scope()


```
