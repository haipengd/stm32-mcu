# Mic -> ADC -> DAC pipeline

## ADC configuration

- Resolution: 12bit (0 ~ 4096)
- SYSCLK: 80MHz
- Clock prescaler: 1
- Total clock cycle: 60usec
- Oversampling ratio: 32x (0 ~ (4096*32)/2^5=4096)
- Oversampling right shift: 5bit

Audio sampling frequency: 80Hz/1/32/60 = 41.7kHz

## TMR6 configuration for memory-to-peripheral(DAC) DMA

TMR6 counter period: 32 * 60 - 1 = 1919

## Pins on Arduino connector

```
                                     [ ]
                                     [ ]
                                     [ ]
                                     [ ]
  [ ]                                [*]
  [ ]                                [ ]
  [ ]                                [ ]
  [*] 3.3V                           [ ]
  [ ] 5V                             [ ]
  [*] GND                            [ ]
  [ ]
  [ ]                                [ ]
                                     [ ]
  [ ]                                [ ]
  [ ]                                [ ]
  [*]                                [ ]
  [ ]                                [ ]
  [ ]                                [ ]
  [*] PC0(ADC1 IN1)                  [ ]
  ```