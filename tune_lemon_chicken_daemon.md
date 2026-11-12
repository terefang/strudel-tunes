```
// @title lemon chicken in the frier
// @by DJ Terefang
// @based on: title lemon chicken example (by tzwaan)

setcpm(130/4)

register('acidenv', (x, pat) => pat.lpf(100)
  .lpenv(x * 9).lps(.2).lpd(.12).lpq(2)
)

const CHARMAP = {
  a: "35",  b: "36",  c: "37",  d: "38",  e: "39",  f: "40",  g: "41",  h: "42",
  i: "43",  j: "44",  k: "45",  l: "46",  m: "47",  n: "48",  o: "49",  p: "50",
  q: "51",  r: "52",  s: "53",  t: "54",  u: "55",  v: "56",  w: "57",  x: "58",
  y: "59",  z: "60",
  A: "30",  B: "32",  C: "34",  D: "36",  E: "38",  F: "40",  G: "42",  H: "44",
  I: "46",  J: "48",  K: "50",  L: "52",  M: "54",  N: "56",  O: "58",  P: "60",
  Q: "62",  R: "64",  S: "66",  T: "68",  U: "70",  V: "72",  W: "74",  X: "76",
  Y: "78",  Z: "80",
};

$PAD2: "<t h e d a e m o n h a s s p o c k e n>*16".pickSqueeze(CHARMAP).note().s("supersaw")
  //.detune(.3).lpf(100).lpenv(4).lpq(7).lpdecay(.1)
.acidenv(slider(0.5,0,2,0.1))
  .o(2)
  .room(1)
  .roomsize(slider(0.8,0.1,2,.1))
  ._scope()
  
$PAD1: "< L E M O N C H I C K E N I N T H E F R I E R E >*16".pickSqueeze(CHARMAP).note().s("supersaw")
  //.detune(.3).lpf(100).lpenv(4).lpq(7).lpdecay(.1)
.acidenv(slider(1.1,0,2,0.1))
  .o(2)
  .room(1)
  .roomsize(slider(0.5,0.1,2,.1))
  ._scope()

$BASE: s("sbd*4")
  .room(1)  
  .roomsize(slider(0.9,0.1,1,.1))
  .delay(.2)
  ._scope()
```

### nice

```
$PAD: "< M i s s i s s i p p i - >*16"
  .pickSqueeze(CHARMAP)
  .note()
  .s("square")
  .acidenv(perlin.range(10,99).mul(.01))
  .o(2)
  .room(1)
  .roomsize(slider(0.3,0.1,2,.1))
 .postgain(GLOBALGAIN)
._pianoroll()
```

### loving vibe

```
$PAD: note("< C C C C G G A# A# >*16")
  .transpose("<0 2 0 2 0 0 1 0>*16")
  .s("supersaw")
  //.acidenv(perlin.range(10,99).mul(.01))
  .acidenv(slider(61.6,0,100).mul(.01))
  //.o(2)
  //.accent(slider(0.3,0.1,2,.1))
  .room(1)
  .roomsize(slider(0.8,0.1,2,.1))
 .postgain(GLOBALGAIN)
._pianoroll()
```

### running

```
_$PAD: note("< C C C C G G A# A# >*16")
  .transpose("<0 2 0 2 0 0 1 0>*16")
  .s("supersaw")
  //.acidenv(perlin.range(10,99).mul(.01))
  .acidenv(slider(61.6,0,100).mul(.01))
  //.o(2)
  //.accent(slider(0.3,0.1,2,.1))
  .room(1)
  .roomsize(slider(0.8,0.1,2,.1))
 .postgain(GLOBALGAIN)
._pianoroll()
```
