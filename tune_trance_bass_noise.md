### trance bass noise

```
register('acidenv', (x,pat) => pat.lpf(100)
  .lpenv( x * 9 ).lps(.2).lpd(.12)
)

setcpm(120/4)

const bline = `<[3 5@15] [3@12 0@4] [5 7@15] 7>`

const bstruct = `<
1 1@3 1@2 1 1@2 1 1@2 1 1@2 1 
2 1@3 1@2 2 1@2 2 1@2 2 2 2 2
1 1@2 1 1@2 1 1@2 1 1@2 1 1@2 1
1 1 1 1 1@3 1 1@2 1 1@2 1 1 1@2
>*17`
$NOISE: n(bline.sub("11")).clip(slider(1.9,0,5,0.1))
  .struct(bstruct)
.acidenv(slider(0.229))
.o(2).detune(slider(0.543))
  .gain(slider(1.6,0,2,.1))
.diode("1:.6 1:.75 2:.5 1:.75 1:1 1:.75")
.s('supersaw').unison(slider(0.304))
    .lpsustain(slider(0.6,0,1,.1))._scope()

```
