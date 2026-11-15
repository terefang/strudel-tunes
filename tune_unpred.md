```
$: n("<1 - 1 - >*16").scale("C:minor")
  .s("supersaw")
.acidenv(slider(0.47,0,1,.01).pow(2))
  .o(3).diode("1:.7  1:.5")
  .delay(perlin.range(0,20).mul(.1))
  .postgain(GLOBALGAIN)
._scope()
```
