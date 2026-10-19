```
samples('http://127.0.0.1:2323/strudel.json')

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



//$BASS: n(bline.sub("11")).clip(slider(1,0,5,0.1))
$BASS: n("C#").clip(slider(1.06,0,2,0.01))
.acidenv(slider(1))
.o(2).detune(slider(0.085))
  .gain(slider(1.3,0,2,.1))
.diode("1:.6 1:.75 2:.5 1:.75 1:1 1:.75")
.s('ess_bass').unison(slider(0.304))
    .lpsustain(slider(0.3,0,1,.1))._scope()
  $: s("aod_epad1").note("{60 55 65 60 65} < {58 } {57 } {58} {55}>")
    .struct(bstruct)
    .acidenv2(
    slider(0.6,0,2,.01),
    slider(0.62,0,1,.01),
    slider(0.093,0,.5,.001),
    slider(52,0,200,4)) 
  .delay(slider(0,0,2,.01))
  .room(slider(0,0,2,.1))
  .gain(slider(0.3,0,2,.1))
  ._scope()

```
