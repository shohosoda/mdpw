[日本語](README.ja.md)
# mdpw

## How to in youtube
- [English](https://youtu.be/YkBtc0jgHjk)
- [Japanese](https://youtu.be/LU0w-Ieol3Q)

 ## Overview
 An example of how to use mdpw is as follows:
```python
import mdpw
a = ['s',['n',64,1,64,1],['n',68,1,64,1],['n',71,1,64,1],
         ['c',['n',64,1,64,1],['n',68,1,64,1],['n',71,1,64,1]],
         ['c',['s',['n',64,1,64,1],['n',68,1,64,1],['n',71,1,64,1],
              ['s',['n',68,2,64],['n',71],['n',75]]]]]
mdpw.compile(a, 120).write("hello.mid")
```

The beginning of an array must be 'n', 's', or 'c'.
An array starting with 'n' represents a note, followed by pitch, duration, velocity, and timbre. If values after duration are omitted, the values from the previous note are used. Rests are represented as notes with velocity 0.
An array starting with 's' represents playing in sequence. This array can be nested.
An array starting with 'c' represents playing simultaneously. This array can be nested too.
`mdpw.compile(a, 120)` generates a MIDI file at 120 bpm.
`write("hello.mid")` saves it to a file.

