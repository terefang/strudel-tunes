```
// chord sample four stacks
register('acidenv', (x,pat) => pat.lpf(100)
  .lpenv( x * 9 ).lps(.2).lpd(.12)
)

setcpm(240/4)

const chords = chord(`
  <D- F  G-@2  D- F  G@2   D- A-7 G@2  D- F  G-@2 >
  <D# C# F# G# D# C# F# G# D# C# F# G# D# C# F# G#>
  <D- F  G-@2  D- F  G@2   D- A-7 G@2  D- F  G-@2 >
  <D  C  F  G  D  C  F  G  D  C  F  G  D  C  F  G >
  `)
//---------------------------------------------------------------------
$: chords.voicing().s("sine").clip(1)
  .transpose("<0 -12 -12@2 1 2 1 -2>")
  .room(slider(0.8,0,4,0.1))
  .roomsize(slider(1,0,7,1))
  .decay(slider(0.5,0,3,.1))
  //.lpf(slider(1100,0,20000,100))
  .acidenv(slider(0.2,0,4,0.1))
  .sometimes(x => x.acidenv(perlin.range(0.2,2.2)))
  .orbit(3)
  .gain(slider(0.1,0,2,0.1))
  ._scope()


```
