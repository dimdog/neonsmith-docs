# WLED Effects Reference

Complete reference for all WLED effect IDs (0-217), their parameters, and recommendations for 1D (25-pixel strip) and 2D (matrix) configurations.

## Data String Format

Effect `_data` strings follow this format:

```
"Name@slider1,slider2,custom1,custom2,custom3,check1,check2,check3;color1,color2,color3;palette;flags;defaults"
```

- `@` separates name from sliders
- `;` separates sections: sliders | colors | palette | flags | defaults
- `!` means "uses default label" (Speed or Intensity for the first two sliders)
- **Flags:** `1` = 1D only, `2` = 2D only, `12` = both 1D+2D, `01` = uniform/all pixels same, `1v` = 1D volume reactive, `1f` = 1D frequency reactive, `2v` = 2D volume reactive, `2f` = 2D frequency reactive

## Type Legend

| Type | Description |
|------|-------------|
| 1D | 1D strip effect |
| 2D | 2D matrix effect |
| 1D+2D | Works on both 1D and 2D |
| 1D Vol | 1D volume-reactive (audio) |
| 1D Freq | 1D frequency-reactive (audio) |
| 2D Vol | 2D volume-reactive (audio) |
| 2D Freq | 2D frequency-reactive (audio) |

## Recommendation Legend

| Value | Meaning |
|-------|---------|
| Show | Works well in this configuration |
| Show* | Works but may look limited (see Notes) |
| Hide | Not suitable (2D only, RSVD, or needs more pixels) |

## Effects Table

| ID | Name | Type | Palette | Speed | Intensity | Custom 1 | Custom 2 | Custom 3 | Check 1 | Check 2 | Check 3 | 1D Rec | 2D Rec | Notes |
|----|------|------|---------|-------|-----------|----------|----------|----------|---------|---------|---------|--------|--------|-------|
| 0 | Solid | 1D+2D | No | | | | | | | | | Show | Show | Static solid color |
| 1 | Blink | 1D+2D | Yes | Speed | Duty cycle | | | | | | | Show | Show | Uniform effect (all pixels same) |
| 2 | Breathe | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Uniform effect |
| 3 | Wipe | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | |
| 4 | Wipe Random | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 5 | Random Colors | 1D+2D | Yes | Speed | Fade time | | | | | | | Show | Show | Uniform effect |
| 6 | Sweep | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | |
| 7 | Dynamic | 1D+2D | Yes | Speed | Intensity | | | | Smooth | | | Show | Show | |
| 8 | Colorloop | 1D+2D | Yes | Speed | Saturation | | | | | | | Show | Show | Uniform effect |
| 9 | Rainbow | 1D+2D | Yes | Speed | Size | | | | | | | Show | Show | |
| 10 | Scan | 1D+2D | Yes | Speed | # of dots | | | | | | Overlay | Show | Show | |
| 11 | Scan Dual | 1D+2D | Yes | Speed | # of dots | | | | | | Overlay | Show | Show | |
| 12 | Fade | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Uniform effect |
| 13 | Theater | 1D+2D | Yes | Speed | Gap size | | | | | | | Show | Show | |
| 14 | Theater Rainbow | 1D+2D | Yes | Speed | Gap size | | | | | | | Show | Show | |
| 15 | Running | 1D+2D | Yes | Speed | Wave width | | | | | | | Show | Show | |
| 16 | Saw | 1D+2D | Yes | Speed | Width | | | | | | | Show | Show | |
| 17 | Twinkle | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Default m12=0 |
| 18 | Dissolve | 1D+2D | Yes | Repeat speed | Dissolve speed | | | | Random | Complete | | Show | Show | |
| 19 | Dissolve Rnd | 1D+2D | Yes | Repeat speed | Dissolve speed | | | | | | | Show | Show | |
| 20 | Sparkle | 1D+2D | Yes | Speed | | | | | | | Overlay | Show | Show | Default m12=0 |
| 21 | Sparkle Dark | 1D+2D | Yes | Speed | Intensity | | | | | | Overlay | Show | Show | Default m12=0 |
| 22 | Sparkle+ | 1D+2D | Yes | Speed | Intensity | | | | | | Overlay | Show | Show | Default m12=0 |
| 23 | Strobe | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Uniform effect |
| 24 | Strobe Rainbow | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Uniform effect |
| 25 | Strobe Mega | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Uniform effect |
| 26 | Blink Rainbow | 1D+2D | Yes | Frequency | Blink duration | | | | | | | Show | Show | Uniform effect |
| 27 | Android | 1D+2D | Yes | Speed | Width | | | | | | | Show | Show | Default m12=1 |
| 28 | Chase | 1D+2D | Yes | Speed | Width | | | | | | | Show | Show | |
| 29 | Chase Random | 1D+2D | Yes | Speed | Width | | | | | | | Show | Show | |
| 30 | Chase Rainbow | 1D+2D | Yes | Speed | Width | | | | | | | Show | Show | |
| 31 | Chase Flash | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 32 | Chase Flash Rnd | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 33 | Rainbow Runner | 1D+2D | Yes | Speed | Size | | | | | | | Show | Show | |
| 34 | Colorful | 1D+2D | Yes | Speed | Saturation | | | | | | | Show | Show | |
| 35 | Traffic Light | 1D+2D | Yes | Speed | US style | | | | | | | Show | Show | |
| 36 | Sweep Random | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 37 | Chase 2 | 1D+2D | Yes | Speed | Width | | | | | | | Show | Show | |
| 38 | Aurora | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Default sx=24, pal=50 |
| 39 | Stream | 1D+2D | Yes | Speed | Zone size | | | | | | | Show | Show | |
| 40 | Scanner | 1D+2D | Yes | Speed | Trail | Delay | | | Dual | Bi-delay | | Show | Show | Default m12=0, c1=0 |
| 41 | Lighthouse | 1D+2D | Yes | Speed | Fade rate | | | | | | | Show | Show | |
| 42 | Fireworks | 1D+2D | Yes | | Frequency | | | | | | | Show | Show | Default ix=192, pal=11 |
| 43 | Rain | 1D+2D | Yes | Speed | Spawning rate | | | | | | | Show | Show | Default ix=128, pal=0 |
| 44 | Tetrix | 1D+2D | Yes | Speed | Width | | | | | One color | | Show | Show | Default sx=0, ix=0, pal=11, m12=1 |
| 45 | Fire Flicker | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Uniform effect |
| 46 | Gradient | 1D+2D | Yes | Speed | Spread | | | | | | | Show | Show | Default ix=16 |
| 47 | Loading | 1D+2D | Yes | Speed | Fade | | | | | | | Show | Show | Default ix=16 |
| 48 | Rolling Balls | 1D | Yes | Speed | # of balls | | | | Collide | Overlay | Trails | Show | Hide | 1D only; default m12=1 |
| 49 | Fairy | 1D+2D | Yes | Speed | # of flashers | | | | | | | Show | Show | |
| 50 | Two Dots | 1D+2D | Yes | Speed | Dot size | | | | | | Overlay | Show | Show | |
| 51 | Fairytwinkle | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Default m12=0 |
| 52 | Running Dual | 1D+2D | Yes | Speed | Wave width | | | | | | | Show | Show | |
| 53 | Image | 1D+2D | No | Speed | Blur | | | | | | | Hide | Hide | RSVD - requires WLED_ENABLE_GIF (not in build) |
| 54 | Chase 3 | 1D+2D | Yes | Speed | Size | | | | | | | Show | Show | |
| 55 | Tri Wipe | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 56 | Tri Fade | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 57 | Lightning | 1D+2D | Yes | Speed | Intensity | | | | | | Overlay | Show | Show | |
| 58 | ICU | 1D+2D | Yes | Speed | Intensity | | | | | | Overlay | Show | Show | |
| 59 | Multi Comet | 1D | Yes | Speed | Fade | | | | | | | Show | Hide | 1D only |
| 60 | Scanner Dual | 1D+2D | Yes | Speed | Trail | Delay | | | Dual | Bi-delay | | Show | Show | Default m12=0, c1=0 |
| 61 | Stream 2 | 1D+2D | No | Speed | | | | | | | | Show | Show | |
| 62 | Oscillate | 1D+2D | No | | | | | | | | | Show | Show | No parameters |
| 63 | Pride 2015 | 1D+2D | No | Speed | | | | | | | | Show | Show | |
| 64 | Juggle | 1D+2D | Yes | Speed | Trail | | | | | | | Show | Show | Default sx=64, ix=128 |
| 65 | Palette | 1D+2D | Yes | Shift | Size | Rotation | | | Animate Shift | Animate Rotation | Anamorphic | Show | Show | Default ix=112, c1=0, o1=1, o2=0, o3=1 |
| 66 | Fire 2012 | 1D | Yes | Cooling | Spark rate | | 2D Blur | Boost | | | | Show | Hide | 1D only; default pal=35, sx=64, ix=160, m12=1, c2=128 |
| 67 | Colorwaves | 1D+2D | Yes | Speed | Hue | | | | | | | Show | Show | Default pal=26 |
| 68 | Bpm | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Default sx=64 |
| 69 | Fill Noise | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 70 | Noise 1 | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Default pal=20 |
| 71 | Noise 2 | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Default pal=43 |
| 72 | Noise 3 | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Default pal=35 |
| 73 | Noise 4 | 1D+2D | Yes | Speed | | | | | | | | Show | Show | Default pal=26 |
| 74 | Colortwinkles | 1D+2D | Yes | Fade speed | Spawn speed | | | | | | | Show | Show | Default m12=0 |
| 75 | Lake | 1D+2D | Yes | Speed | | | | | | | | Show | Show | |
| 76 | Meteor | 1D | Yes | Speed | Trail | | | | Gradient | | Smooth | Show | Hide | 1D only |
| 77 | Copy Segment | 1D+2D | No | | Color shift | Lighten | Brighten | ID | Axis(2D) | FullStack(last frame) | | Show | Show | Default ix=0, c1=0, c2=0, c3=0 |
| 78 | Railway | 1D+2D | Yes | Speed | Smoothness | | | | | | | Show | Show | Default pal=3 |
| 79 | Ripple | 1D+2D | Yes | Speed | Wave # | Blur | | | | | Overlay | Show | Show | Default c1=0 |
| 80 | Twinklefox | 1D+2D | Yes | Speed | Twinkle rate | | | | Cool | | | Show | Show | |
| 81 | Twinklecat | 1D+2D | Yes | Speed | Twinkle rate | | | | Cool | Reverse | | Show | Show | |
| 82 | Halloween Eyes | 1D+2D | Yes | Eye off time | Eye on time | | | | | | Overlay | Hide | Show | Too few pixels at 25 LEDs; eyeLength calculation leaves no room |
| 83 | Solid Pattern | 1D+2D | Yes | Fg size | Bg size | | | | | | | Show | Show | Default pal=0 |
| 84 | Solid Pattern Tri | 1D+2D | No | | Size | | | | | | | Show | Show | Default pal=0 |
| 85 | Spots | 1D+2D | Yes | Spread | Width | | | | | | Overlay | Show | Show | |
| 86 | Spots Fade | 1D+2D | Yes | Spread | Width | | | | | | Overlay | Show | Show | |
| 87 | Glitter | 1D+2D | Yes | Speed | Intensity | | | | | | Overlay | Show | Show | Default pal=11, m12=0 |
| 88 | Candle | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Uniform; default sx=96, ix=224, pal=0 |
| 89 | Fireworks Starburst | 1D+2D | Yes | Chance | Fragments | | | | | | Overlay | Show | Show | Default pal=11, m12=0 |
| 90 | Fireworks 1D | 1D+2D | Yes | Gravity | Firing side | | | | | | | Show | Show | Default pal=11, ix=128 |
| 91 | Bouncing Balls | 1D | Yes | Gravity | # of balls | | | | | | Overlay | Show | Hide | 1D only; default m12=1 |
| 92 | Sinelon | 1D+2D | Yes | Speed | Trail | | | | | | | Show | Show | |
| 93 | Sinelon Dual | 1D+2D | Yes | Speed | Trail | | | | | | | Show | Show | |
| 94 | Sinelon Rainbow | 1D+2D | Yes | Speed | Trail | | | | | | | Show | Show | |
| 95 | Popcorn | 1D+2D | Yes | Speed | Intensity | | | | | | Overlay | Show | Show | Default m12=1 |
| 96 | Drip | 1D+2D | Yes | Gravity | # of drips | | | | | | Overlay | Show | Show | Default m12=1 |
| 97 | Plasma | 1D+2D | Yes | Phase | Intensity | | | | | | | Show | Show | |
| 98 | Percent | 1D+2D | Yes | Speed | % of fill | | | | One color | | | Show | Show | |
| 99 | Ripple Rainbow | 1D+2D | Yes | Speed | Wave # | | | | | | | Show | Show | |
| 100 | Heartbeat | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Uniform; default m12=1 |
| 101 | Pacifica | 1D+2D | Yes | Speed | Angle | | | | | | | Show | Show | Default pal=51 |
| 102 | Candle Multi | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Default sx=96, ix=224, pal=0 |
| 103 | Solid Glitter | 1D+2D | No | | Intensity | | | | | | | Show | Show | Default m12=0 |
| 104 | Sunrise | 1D+2D | Yes | Time [min] | Width | | | | | | | Show | Show | Default pal=35, sx=60 |
| 105 | Phased | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | |
| 106 | Twinkleup | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Default m12=0 |
| 107 | Noise Pal | 1D+2D | Yes | Speed | Scale | | | | | | | Show | Show | |
| 108 | Sine | 1D+2D | Yes | Speed | Scale | | | | | | | Show | Show | |
| 109 | Phased Noise | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | |
| 110 | Flow | 1D+2D | Yes | Speed | Zones | | | | | | | Hide | Show | Too few visible zones at 25 LEDs |
| 111 | Chunchun | 1D+2D | Yes | Speed | Gap size | | | | | | | Show | Show | |
| 112 | Dancing Shadows | 1D+2D | Yes | Speed | # of shadows | | | | | | | Show | Show | |
| 113 | Washing Machine | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | |
| 114 | Rotozoomer | 2D | Yes | Speed | Scale | | | | Alt | | | Hide | Show | 2D only; default pal=54 |
| 115 | Blends | 1D+2D | Yes | Shift speed | Blend speed | | | | | | | Show | Show | |
| 116 | TV Simulator | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | Uniform effect |
| 117 | Dynamic Smooth | 1D+2D | Yes | Speed | Intensity | | | | | | | Show | Show | |
| 118 | Spaceships | 2D | Yes | Speed | Blur | | | | Smear | | | Hide | Show | 2D only |
| 119 | Crazy Bees | 2D | Yes | Speed | Blur | | | | Smear | | | Hide | Show | 2D only; default pal=11, ix=0 |
| 120 | Ghost Rider | 2D | Yes | Fade rate | Blur | | | | | | | Hide | Show | 2D only |
| 121 | Blobs | 2D | Yes | Speed | # blobs | Blur | Trail | | | | | Hide | Show | 2D only; default c1=8 |
| 122 | Scrolling Text | 2D | Yes | Speed | Y Offset | Trail | Font size | Rotate | Gradient | | Reverse | Hide | Show | 2D only; default ix=128, c1=0 |
| 123 | Drift Rose | 2D | Yes | Fade | Blur | | | | Smear | | | Hide | Show | 2D only; default pal=11 |
| 124 | Distortion Waves | 2D | Yes | Speed | Scale | | | | Fill | Zoom | Alt | Hide | Show | 2D only; default pal=0 |
| 125 | Soap | 2D | Yes | Speed | Smoothness | Density | | | | | | Hide | Show | 2D only; default pal=11 |
| 126 | Octopus | 2D | Yes | Speed | | Offset X | Offset Y | Legs | fasttan | | | Hide | Show | 2D only |
| 127 | Waving Cell | 2D | Yes | Speed | Blur | Amplitude 1 | Amplitude 2 | Amplitude 3 | | Flow | | Hide | Show | 2D only; default ix=0 |
| 128 | Pixels | 1D Vol | Yes | Fade rate | # of pixels | | | | | | | Show | Hide | 1D volume reactive; default m12=0, si=0 |
| 129 | Pixelwave | 1D Vol | Yes | Speed | Sensitivity | | | | | | | Show | Hide | 1D volume reactive; default ix=64, m12=2, si=0 |
| 130 | Juggles | 1D Vol | Yes | Speed | # of balls | | | | | | | Show | Hide | Uniform 1D volume reactive; default m12=0, si=0 |
| 131 | Matripix | 1D Vol | Yes | Speed | Brightness | | | | | | | Show | Hide | 1D volume reactive; default ix=64, m12=2, si=1 |
| 132 | Gravimeter | 1D Vol | Yes | Rate of fall | Sensitivity | | | | | | | Show | Hide | 1D volume reactive; default ix=128, m12=2, si=0 |
| 133 | Plasmoid | 1D Vol | Yes | Phase | # of pixels | | | | | | | Show | Hide | Uniform 1D volume reactive; default sx=128, ix=128, m12=0, si=0 |
| 134 | Puddles | 1D Vol | Yes | Fade rate | Puddle size | | | | | | | Show | Hide | 1D volume reactive; default m12=0, si=0 |
| 135 | Midnoise | 1D Vol | Yes | Fade rate | Max. length | | | | | | | Show | Hide | 1D volume reactive; default ix=128, m12=1, si=0 |
| 136 | Noisemeter | 1D Vol | Yes | Fade rate | Width | | | | | | | Show | Hide | 1D volume reactive; default ix=128, m12=2, si=0 |
| 137 | Freqwave | 1D Freq | No | Speed | Sound effect | Low bin | High bin | Pre-amp | | | | Show | Hide | Uniform 1D frequency reactive; default m12=2, si=0 |
| 138 | Freqmatrix | 1D Freq | No | Speed | Sound effect | Low bin | High bin | Sensitivity | | | | Show | Hide | Uniform 1D frequency reactive; default m12=3, si=0 |
| 139 | GEQ | 2D Freq | Yes | Fade speed | Ripple decay | # of bands | | Bin | Color bars | | | Hide | Show | 2D frequency reactive; default c1=255, c2=64, pal=11, si=0, c3=0 |
| 140 | Waterfall | 1D Freq | Yes | Speed | Adjust color | Select bin | Volume (min) | | | | | Show | Hide | Uniform 1D frequency reactive; default c2=0, m12=2, si=0 |
| 141 | Freqpixels | 1D Freq | Yes | Fade rate | Starting color and # of pixels | | | | | | | Show | Hide | 1D frequency reactive; default m12=0, si=0 |
| 142 | RSVD | - | No | | | | | | | | | Hide | Hide | Reserved (Binmap - no implementation) |
| 143 | Noisefire | 1D Vol | No | Speed | Intensity | | | | | | | Show | Hide | Uniform 1D volume reactive; default m12=2, si=0 |
| 144 | Puddlepeak | 1D Vol | Yes | Fade rate | Puddle size | Select bin | Volume (min) | | | | | Show | Hide | 1D volume reactive; default c2=0, m12=0, si=0 |
| 145 | Noisemove | 1D Freq | Yes | Move speed | Fade rate | | | | | | | Show | Hide | Uniform 1D frequency reactive; default m12=0, si=0 |
| 146 | Noise2D | 2D | Yes | Speed | Scale | | | | | | | Hide | Show | 2D only |
| 147 | Perlin Move | 1D | Yes | Speed | # of pixels | Fade rate | | | | | | Show | Hide | 1D only |
| 148 | Ripple Peak | 1D Vol | Yes | Fade rate | Max # of ripples | Select bin | Volume (min) | | | | | Show | Hide | 1D volume reactive; default c2=0, m12=0, si=0 |
| 149 | Firenoise | 2D | Yes | X scale | Y scale | | | | Palette | | | Hide | Show | 2D only; default pal=66 |
| 150 | Squared Swirl | 2D | Yes | | Fade | | | Blur | | | | Hide | Show | 2D only |
| 151 | PacMan | 1D | Yes | Speed | # of PowerDots | Blink distance | Blur | # of Ghosts | Dots | Smear | Compact | Hide | Hide | Needs SEGLEN > 26 with defaults; shows solid at 25 LEDs |
| 152 | DNA | 2D | Yes | Scroll speed | Blur | | | | Smear | | | Hide | Show | 2D only; default ix=0 |
| 153 | Matrix | 2D | No | Speed | Spawning rate | Trail | | | Custom color | | | Hide | Show | 2D only |
| 154 | Metaballs | 2D | Yes | Speed | | | | | | | | Hide | Show | 2D only |
| 155 | Freqmap | 1D Freq | Yes | Fade rate | Starting color | | | | | | | Show | Hide | 1D frequency reactive; default m12=0, si=0 |
| 156 | Gravcenter | 1D Vol | Yes | Rate of fall | Sensitivity | | | | | | | Show | Hide | 1D volume reactive; default ix=128, m12=2, si=0 |
| 157 | Gravcentric | 1D Vol | Yes | Rate of fall | Sensitivity | | | | | | | Show | Hide | 1D volume reactive; default ix=128, m12=3, si=0 |
| 158 | Gravfreq | 1D Freq | Yes | Rate of fall | Sensitivity | | | | | | | Show | Hide | 1D frequency reactive; default ix=128, m12=0, si=0 |
| 159 | DJ Light | 1D Freq | No | Speed | | | | | | | | Show | Hide | Uniform 1D frequency reactive; default m12=2, si=0 |
| 160 | Funky Plank | 2D Freq | No | Scroll speed | | # of bands | | | | | | Hide | Show | 2D frequency reactive; default si=0 |
| 161 | Shimmer | 1D | Yes | Speed | Interval | Size | Granular | Flow | Zebra | Reverse | Sporadic | Show | Hide | 1D only; default pal=15, sx=220, ix=10, c2=0, c3=0 |
| 162 | Pulser | 2D | Yes | Speed | Blur | | | | | | | Hide | Show | 2D only |
| 163 | Blurz | 1D Freq | Yes | Fade rate | Blur | | | | | | | Show | Hide | 1D frequency reactive; default m12=0, si=0 |
| 164 | Drift | 2D | Yes | Rotation speed | Blur | | | | Twin | Smear | | Hide | Show | 2D only; default ix=0 |
| 165 | Waverly | 2D Vol | Yes | Amplification | Sensitivity | | | | | | Blur | Hide | Show | 2D volume reactive; default ix=64, si=0 |
| 166 | Sun Radiation | 2D | No | Variance | Brightness | | | | | | | Hide | Show | 2D only |
| 167 | Colored Bursts | 2D | Yes | Speed | # of lines | | | Blur | Gradient | Smear | Dots | Hide | Show | 2D only; default c3=16 |
| 168 | Julia | 2D | Yes | | Max iterations per pixel | X center | Y center | Area size | Blur | | | Hide | Show | 2D only; default ix=24, c1=128, c2=128, c3=16 |
| 169 | RSVD | - | No | | | | | | | | | Hide | Hide | Removed slot |
| 170 | RSVD | - | No | | | | | | | | | Hide | Hide | Removed slot |
| 171 | RSVD | - | No | | | | | | | | | Hide | Hide | Removed slot |
| 172 | Game Of Life | 2D | Yes | Speed | | Blur | | | | | Mutation | Hide | Show | 2D only; default pal=11, sx=128 |
| 173 | Tartan | 2D | Yes | X scale | Y scale | | | Sharpness | | | | Hide | Show | 2D only |
| 174 | Polar Lights | 2D | Yes | Speed | Scale | | | | Flip Palette | | | Hide | Show | 2D only; default pal=71 |
| 175 | Swirl | 2D Vol | Yes | Speed | Sensitivity | Blur | | | | | | Hide | Show | 2D volume reactive; default ix=64, si=0 |
| 176 | Lissajous | 2D | Yes | X frequency | Fade rate | Blur | | Speed | Smear | | | Hide | Show | 2D only; default c1=0 |
| 177 | Frizzles | 2D | Yes | X frequency | Y frequency | Blur | | | Smear | | | Hide | Show | 2D only |
| 178 | Plasma Ball | 2D | Yes | Speed | | Fade | Blur | | | | | Hide | Show | 2D only |
| 179 | Flow Stripe | 1D | Yes | Hue speed | Effect speed | | | | | | | Show | Hide | 1D only; default pal=11 |
| 180 | Hiphotic | 2D | Yes | X scale | Y scale | | | Speed | | | | Hide | Show | 2D only |
| 181 | Sindots | 2D | Yes | Speed | Dot distance | Fade rate | Blur | | Smear | | | Hide | Show | 2D only |
| 182 | DNA Spiral | 2D | Yes | Scroll speed | Y frequency | Blur | | | Smear | | | Hide | Show | 2D only; default c1=0 |
| 183 | Black Hole | 2D | Yes | Fade rate | Outer Y freq. | Outer X freq. | Inner X freq. | Inner Y freq. | Solid | | Blur | Hide | Show | 2D only; default pal=11 |
| 184 | Wavesins | 1D | Yes | Speed | Brightness variation | Starting color | Range of colors | Color variation | | | | Show | Hide | 1D only |
| 185 | Rocktaves | 1D Freq | Yes | | | | | | | | | Show | Hide | Uniform 1D frequency reactive; default m12=1, si=0 |
| 186 | Akemi | 2D Freq | No | Color speed | Dance | | | | | | | Hide | Show | 2D frequency reactive; default si=0 |
| 187 | PS Volcano | 2D | Yes | Speed | Intensity | Move | Bounce | Spread | AgeColor | Walls | Collide | Hide | Show | 2D PS; default pal=35, sx=100, ix=190, c1=0, c2=160, c3=6, o1=1 |
| 188 | PS Fire | 2D | Yes | Speed | Intensity | Flame Height | Wind | Spread | Smooth | Cylinder | Turbulence | Hide | Show | 2D PS; default pal=35, sx=110, c1=110, c2=50, c3=31, o1=1 |
| 189 | PS Fireworks | 2D | Yes | Launches | Explosion Size | Fuse | Blur | Gravity | Cylinder | Ground | Fast | Hide | Show | 2D PS; default pal=11, ix=50, c1=40, c2=0, c3=12 |
| 190 | PS Vortex | 2D | Yes | Rotation Speed | Particle Speed | Arms | Flip | Nozzle | Smear | Direction | Random Flip | Hide | Show | 2D PS; default pal=27, c1=200, c2=0, c3=0 |
| 191 | PS Fuzzy Noise | 2D | Yes | Speed | Particles | Bounce | Friction | Scale | Cylinder | Smear | Collide | Hide | Show | 2D PS; default pal=64, sx=50, ix=200, c1=130, c2=30, c3=5, o3=1 |
| 192 | PS Ballpit | 2D | Yes | Speed | Intensity | Size | Hardness | Saturation | Cylinder | Walls | Ground | Hide | Show | 2D PS; default pal=11, sx=100, ix=220, c1=70, c2=180, c3=31, o3=1 |
| 193 | PS Box | 2D | Yes | Speed | Particles | Tilt | Hardness | Size | Random | Washing Machine | Sloshing | Hide | Show | 2D PS; default pal=53, ix=50, c3=1, o1=1 |
| 194 | PS Attractor | 2D | Yes | Mass | Particles | Size | Collide | Friction | AgeColor | Move | Swallow | Hide | Show | 2D PS; default pal=9, sx=100, ix=82, c1=2, c2=0 |
| 195 | PS Impact | 2D | Yes | Launches | Intensity | Force | Hardness | Blur | Cylinder | Walls | Collide | Hide | Show | 2D PS; default pal=0, sx=32, ix=85, c1=70, c2=130, c3=0, o3=1 |
| 196 | PS Waterfall | 2D | Yes | Speed | Intensity | Variation | Collide | Position | Cylinder | Walls | Ground | Hide | Show | 2D PS; default pal=9, sx=15, ix=200, c1=32, c2=160, o3=1 |
| 197 | PS Spray | 2D Vol | Yes | Speed | Intensity | Left/Right | Up/Down | Angle | Gravity | Cylinder/Square | Collide | Hide | Show | 2D volume reactive PS; default pal=0, sx=150, ix=150, c1=220, c2=30, c3=21 |
| 198 | PS GEQ 2D | 2D Freq | Yes | Speed | Intensity | Diverge | Bounce | Gravity | Cylinder | Walls | Floor | Hide | Show | 2D frequency reactive PS; default pal=0, sx=155, ix=200, c1=0 |
| 199 | PS GEQ Nova | 2D Freq | Yes | Speed | Intensity | Rotation Speed | Color Change | Nozzle | | Direction | | Hide | Show | 2D frequency reactive PS; default pal=13, ix=180, c1=0, c2=0, c3=8 |
| 200 | PS Ghost Rider | 2D | Yes | Speed | Spiral | Blur | Color Cycle | Spread | AgeColor | Walls | | Hide | Show | 2D PS; default pal=1, sx=70, ix=0, c1=220, c2=30, c3=21, o1=1 |
| 201 | PS Blobs | 2D Vol | Yes | Speed | Blobs | Size | Life | Blur | Wobble | Collide | Pulsate | Hide | Show | 2D volume reactive PS; default sx=30, ix=64, c1=200, c2=130, c3=0, o3=1 |
| 202 | PS DripDrop | 1D | Yes | Speed | Intensity | Splash | Blur | Gravity | Rain | PushSplash | Smooth | Show | Hide | 1D PS; default pal=0, sx=150, ix=25, c1=220, c2=30, c3=21 |
| 203 | PS Pinball | 1D | Yes | Speed | Intensity | Size | Blur | Gravity | Collide | Rolling | Position Color | Show | Hide | 1D PS; default pal=0, ix=220, c2=0, c3=8, o1=1 |
| 204 | PS Dancing Shadows | 1D | Yes | Speed | Intensity | Blur | Color Cycle | | Smear | Position Color | Smooth | Show | Hide | 1D PS; default sx=100, ix=180, c1=0, c2=0 |
| 205 | PS Fireworks 1D | 1D | Yes | Gravity | Explosion | Firing side | Blur | Color | Colorful | Trail | Smooth | Show | Hide | 1D PS; default c2=30, o1=1 |
| 206 | PS Sparkler | 1D | Yes | Move | Intensity | Saturation | Blur | Sparklers | Slide | Bounce | Large | Show | Hide | 1D PS; default pal=0, sx=255, c1=0, c2=0, c3=6 |
| 207 | PS Hourglass | 1D | Yes | Interval | Intensity | Color | Blur | Gravity | Colorflip | Start | Fast Reset | Show | Hide | 1D PS; default pal=34, sx=5, ix=200, c1=140, c2=80, c3=4, o1=1, o2=1, o3=1 |
| 208 | PS Spray 1D | 1D | Yes | Speed(+/-) | Intensity | Position | Blur | Gravity(+/-) | AgeColor | Bounce | Position Color | Show | Hide | 1D PS; default sx=200, ix=220, c1=0, c2=0 |
| 209 | PS 1D Balance | 1D | Yes | Speed | Intensity | Hardness | Blur | Tilt | Position Color | Wrap | Random | Show | Hide | 1D PS; default pal=18, c2=0, c3=4, o1=1 |
| 210 | PS Chase | 1D | Yes | Speed | Density | Size | Hue | Blur | Playful | | Position Color | Show | Hide | 1D PS; default pal=11, sx=50, c2=5, c3=0 |
| 211 | PS Starburst | 1D | Yes | Chance | Fragments | Size | Blur | Cooling | Gravity | Colorful | Push | Show | Hide | 1D PS; default pal=52, sx=150, ix=150, c1=120, c2=0, c3=21 |
| 212 | PS GEQ 1D | 1D Freq | Yes | Speed | Intensity | Size | Blur | | | | | Show | Hide | 1D frequency reactive PS; default pal=0, sx=50, ix=200, c1=0, c2=0, c3=0, o1=1, o2=1 |
| 213 | PS Fire 1D | 1D | Yes | Speed | Intensity | Cooling | Blur | | | | | Show | Hide | 1D PS; default pal=35, sx=100, ix=50, c1=80, c2=100, c3=28, o1=1, o2=1 |
| 214 | PS Sonic Stream | 1D Freq | Yes | Speed | Intensity | Color | Blur | Bin | Mod | Filter | Push | Show | Hide | 1D frequency reactive PS; default c3=0, o2=1 |
| 215 | PS Sonic Boom | 1D Freq | Yes | Speed | Intensity | Color | Position | Bin | Mod | Filter | Blur | Show | Hide | 1D frequency reactive PS; default c2=63, c3=0, o2=1 |
| 216 | PS Springy | 1D Freq | Yes | Stiffness | Damping | Density | Hue | Mode | Smear | XL | AR | Show | Hide | 1D frequency reactive PS; default pal=54, c2=0, c3=23 |
| 217 | PS Galaxy | 2D | Yes | Speed | Intensity | Size | | Color | | Starfield | Trace | Hide | Show | 2D PS; default pal=59, sx=80, c1=1, c3=4 |

## Summary Statistics

- **Total effect slots:** 218 (IDs 0-217)
- **Active effects:** 213
- **Reserved/removed slots:** 5 (IDs 53, 142, 169, 170, 171)
- **1D effects:** ~100+ (including 1D-only, 1D+2D, 1D volume, 1D frequency)
- **2D-only effects:** ~60+
- **Audio reactive effects:** ~40+ (volume and frequency reactive)
- **Particle System (PS) effects:** IDs 187-217

## Notes

- Effects marked "Uniform" (`01` flag) set all pixels to the same color/state -- they look the same regardless of strip length.
- Audio reactive effects (Vol/Freq types) require a microphone or line-in configured in WLED.
- Particle System (PS) effects use a physics-based particle engine and may be more CPU-intensive.
- Default parameter values (listed in Notes column) are applied automatically when the effect is first selected.
- The `m12` default controls 1D-to-2D expansion mode; `si` controls sound input selection.
