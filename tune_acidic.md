```js

register('acidenv', (x,pat) => pat.lpf(100)
  .lpenv( x * 9 ).lps(.2).lpd(.12)
)
setcpm(160/4)

$: note("<c a f e>*8").n("0 <1 [2 2] 3 [4 5]>")
  .s("bd")
  .acidenv(slider(0.129))
  .gain(slider(0.3828,.0,1.1))

$: n("<0>*16").scale("g:minor").trans(-24)
  .detune(rand)
  .s("supersaw")
  .acidenv(slider(0.796))
  .gain(slider(0.882,.1,1.1))
._pianoroll()

```
