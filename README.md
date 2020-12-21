# tranquility-levels
Levels for the discontinued game tranquility www.tqworld.com

## what game?
download: https://macintoshgarden.org/games/tranquility

# description language

## quick guide
```
I = init
W = world
M = message
E = event
T = timer
N = note
A = aggregate
G = geometry
C = color
O = oscillator
P = platform
Q = quark
# = comment
```
## detailed guide (work in progress)
Each plain text .tq level file contains a definition for 7 layouts, each containing a spinner.  
Some .tq levels masquerade as GIF files for reasons I do not yet understand.
- `A` = aggregate
   - example: `A 1`
   - this is a counter that increments before each event
   - see: E = event
- `C` = color
  - example: `C 10 0.930308 0.886546 0.479355 0.7 0.00005 0.136678 0.842395 0.479355 0.7 0.00005`
  - format (gradient): type r g b a r g b a delta
  - example: `C 0 0.0 1.85 0.4 0.2 0.0001`
  - format (solid): type r g b a delta
    - type
      - 10 = gradient
      - 0 = solid
    - r,g,b = value (0.0 to 1.0)
    - a = alpha/opacity (0.0 to 1.0)
    - delta = animates alpha
- `E` = event
  - example: `E 1 0 0 0`
  - format: ?1 ?2 ?3 ?4
    - ?1 = 
    - ?2 = 
    - ?3 = 
    - ?4 = 
- `G` = geometry
  - example: `G 8 150.0 150.0 0.0 0.0 0.0 0.0 0.0 0.0 0 1 0 0 0 0 0 0 Z0c1yu`
  - format: s d(x8) ?1(x8) id
    - type
      - 8 or 50
    - d = dimensions
      - type 8
        - d = 37.0 37.0
        - d = 150.0 150.0
        - d = 200.0 200.0
      - type 50
        - d = 50.0 50.0
    - ?1 = ?
      - 0 = solid
      - 1 = gradient
      - 2 = 
      - 3 = 
      - 4 = 
      - 5 = 
      - 6 = 
      - 7 = 
      - 8 = 
    - id = alphanuneric id
  - see: P = platform
- `I` = init
  - example: `I`
  - no arguments
- `M` = message
  - example: `M 100 2:This Daily Demo for May 10, 2011`
  - format: line color:text
    - line number
      - 0-21 = menu text
      - 100-121 = overlay text
      - 99 = comment
      - 128 = server values
    - color
      - 0 = red
      - 1 = orange
      - 2 = yellow
      - 3 = green
      - 4 = turqoise
      - 5 = cyan
      - 6 = blue
      - 7 = purple
      - 8 = magenta
      - 9 = grey
    - text
      - | = hard space
- `N` = note
  - example: `N 6 20 36:34:32:31 1 1 4`
  - format: instrument volume sequence ? tuning reverb
    - instrument
      - 0 = pad
      - 1 = bass pad
      - 2 = string
      - 3 = guitar
      - 4 = brass
      - 5 = glass
      - 6 = underwater lead
      - 7 = underwater bass
      - 8 = underwater bass
      - 9 = piano
      - 10 = piano echo
      - 11 = piano chords
      - 12 = bass chords
      - 13 = underwater bass
      - 14 = cymbal
      - 15 = cymbal
      - 16 = underwater pad
      - 17 = underwater pad echo
      - 18 = bongo
      - 19 = bass drum
      - 20 = bass echo
      - 21 = bass echo
      - 22 = synth
      - 23 = synth echo
      - 24-48 = repeat above order with effects
    - volume
      - 1 to 30
    - sequence of note values
    - ?
      - values: 0,1,2
    - tuning
    - reverb
  - #N >= #T
  - see: T = timer
- `O` = oscillator
  - example: `O 100 0.001 0.734818 257.531952`
  - format: type ?1 ?2 ?3
  - format: type ?1 ?2 ?3 ?4
    - type
      - split into digits?
      - seen values: 0, 4, 50, 52, 100, 101, 112, 351, 352
    - speed
    - ?2
    - ?3
    - ?4
- `P` = platform
  - example: `P 111 40 0 1 1 1 1 4.4 4.4 0.0 100.0 0.0 160.0 10.0 160.0 0.0 160.0 0.0 0 1.0 1.0`
  - format: type quantity ? partvisible 1 1 1 4.4 4.4 0.0 x y z 10.0 160.0 dx dy dz 0 1 1
  - see: G = geometry
- `Q` = quark
  - example: `Q 1 20 6 6 011 011 7.7 7.7 0.0 0.0 0.0 210.0 1.0 210.0 1`
  - format: 
- `T` = timer
  - example: `T 1 120 0 0 0 1.0 7.0 0 0 0`
  - format: id duration
    - type: lsb binary number
    - duration (60ths of a second)
    - ?2 = 0
    - ?3 = 0
    - ?4 = 0
    - echo?
      - valid values: 0.0, 1.0
    - reverb?
      - seen values: 1.0, 7.0
    - ?7 = 0
    - ?8 = 0
    - ?9 = 0
  - see: N = note
- `W` = world
  - example: `W 1.0 0 1.0 0.0 0.0 0.0 0.0 30.0 0.006 1.0 4000.0 5000.0 0.001 0.0 0.0 0.0 F0`
  - format: W active 0 1.0 0.0 0.0 0.0 0.0 ? ? x y z ? cdx cdy cdz fov
    - active = 1.0 animation on
    - ? = 0
    - ? = 1.0
    - ? = 0.0
    - ? = 0.0
    - ? = 0.0
    - ? = 0.0
    - ? = 20.0, 30.0
    - ? = 0.006
    - x = player x
    - y = player y
    - z = player z
    - ?
    - dx = player delta x
    - dy = player delta y
    - dz = player delta z
    - fov = field of view
- `Z` = timestamp
  - example: `Z 20110510163720+0100`
  - format: yyMMddHHmmssZZZZ
- `#` = comment
  - any line beginning with this is ignored

## example level:
- [Daily Demo (May 10, 2011)](contributions/gingerbeardman/raw.tq)

## undocumented keys in the game
- f = futurist [magic 8-ball messages] (off, on)
- h = help (same as ?)
- H = jump to max height
- m = music mode (trio, quartet, pastoral, ensemble, traditional, adaptive, mostly drums, all drums)
- R = track playback (off, on)
- r = track recording (on, off)
- t = frame rate limit (unlimited, 60fps, 30fps)
- w = waterfall mode (off, light, full)
- W = wireframe mode (off, on)
- X = G_MirrorTexture decrease
- x = G_MirrorTexture increase
- Z = PlaformOffset decrease
- z = PlaformOffset increase
- [ = maximum speed decrease
- ] = maximum speed increase
- | = show/cycle welcome message
- home = view score
- pg down = look down
- pg up = look up
- end = look straight/reset
