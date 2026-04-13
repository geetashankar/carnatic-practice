# Svara — Carnatic Practice Companion

A browser-based practice tool for Carnatic music students. Built for my own 
students to reinforce foundational ear training between lessons — no app 
install, no account, just open and practice.

**[Try it live →](https://geetashankar.github.io/carnatic-practice)**

---

## Features

**Shruti & Tanpura**  
Persistent drone synthesized with inharmonic string partials, jawari buzz 
(bandpass-filtered noise for the bridge rattle), and sympathetic shimmer via 
detuned octave oscillators. All 12 chromatic shruti supported. Retunes live 
without restarting.

**Varisai Drills**  
Metronome with Adi tala beat visualization, animated note highlighting, and 
a practice timer. Includes Sarali, Janta (1–3), Dhatu (1–2), and Alankaram 
exercises across 4 ragas: Mayamalavagowla, Kharaharapriya, Shankarabharanam, 
Kalyani.

**Swarasthanam** — Pitch identification game  
5 levels from glow-guided (tap the lit button) to multi-note sequence 
identification. Progressive unlock system: clear a level N times to unlock 
the next.

**Guess the Ragam** — Raga identification game  
Hear a note sequence and identify the raga. Levels range from guided 
reveal (learn mode) to multi-select (multiple valid ragas per sequence).

**Swaram Shadowing** — Timed response drill  
Note plays, timer bar counts down — tap the correct swaram before time runs 
out. 5 difficulty tiers with progressive unlock, lives system, and speed bonus 
scoring.

---

## Tech

Pure HTML/CSS/JS — zero dependencies, zero build step.  
All audio synthesized in real time via the **Web Audio API**:
- `OscillatorNode` stacks with per-harmonic inharmonicity (cents sharpening 
  to simulate string stiffness)
- Looping `AudioBufferSourceNode` through a `BiquadFilterNode` for jawari buzz
- `DynamicsCompressorNode` as a soft limiter on the master output
- Glide retuning via `linearRampToValueAtTime` on pitch change

Hosted on GitHub Pages. State (progress, unlocks, high scores) stored in 
`localStorage`.

---

## Why I built it

I teach Carnatic music, and the hardest part of early training is developing 
sruti shuddham — accurate pitch recognition against a drone. Most practice 
apps are either too passive (just play audio) or require expensive hardware. 
I wanted something my students could open on any device mid-practice, with a 
real tanpura drone and structured ear training games that get harder as they 
improve.
