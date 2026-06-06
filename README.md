# Week 3 Example 2: Full Fighting Game

> **Note for students:** This section is included in example files only to help you study. Do not include it in your Side Quest submissions.

This example builds on Example 1 by adding health, attacking, hit detection, sound, and game states to create a complete two-player fighting game.

- **Game states** — the game is always in one of three states (`STATE_START`, `STATE_FIGHT`, `STATE_WIN`); each state controls what gets drawn and what responds to input; stored as constants to prevent typos
- **`preload()`** — loads all sounds before the sketch starts so they are ready to play immediately; sound files are loaded into an array for variety
- **Sound array** — `punchSounds` holds all 9 punch sounds; `floor(random(...))` picks a random index each time a punch lands so hits sound different
- **Health system** — each fighter has a `health` property that decreases when hit; `maxHealth` is stored separately so health bars can be drawn proportionally using `map()`
- **`startAttack()`** — called from `keyPressed()` so the punch fires once per press; sets the direction of the fist based on the opponent's position
- **`getPunchX()`** — a method that returns the fist's x position; used in `checkHits()` to test whether the punch connects with the opponent
- **`takeHit()`** — called on the fighter being hit; blocked punches deal no damage; health reaching zero triggers `endGame()`
- **Hit flash** — `hitFlash` counts down from 12 each time a fighter is hit; while it is above zero, the blob draws white instead of its normal colour
- **`hitLanded` flag** — prevents the same attack swing from registering more than one hit per punch
- **`keyPressed()` vs `keyIsDown()`** — `keyPressed()` fires once per press and is used for attacks and menu navigation; `keyIsDown()` fires every frame and is used for movement and blocking
- **Health bars with `map()`** — `map()` converts health (0 to maxHealth) to a bar width in pixels (0 to barW); the bar shrinks as health decreases
- **Start and win screens** — drawn using text and shapes in their respective game states; a semi-transparent overlay is used on the win screen

## Setup and Interaction Instructions

To run the sketch locally, open `index.html` in Google Chrome using Live Server.

Sound files must be present in `assets/sounds/` before running:

- `punch_1.wav` through `punch_9.wav`
- `win.wav`
- `background.mp3`

**Player 1 Controls:**

- Move: A / D
- Attack: F
- Block: G

**Player 2 Controls:**

- Move: Arrow Keys
- Attack: K
- Block: L

Press **ENTER** to start or rematch.

**Opening the Chrome Console**

- **Windows:** Press `F12` or `Ctrl + Shift + J`, then click the **Console** tab
- **Mac:** Press `Cmd + Option + J`

The console will show any errors in your sketch.

## Assets

| File | Source |
|------|--------|
| `assets/images/desert-background.jpg` [1] | From Stable Diffusion|
| `assets/images/starting-screen.jpeg` [2] | From Adobe Stock|



## References

[1] AI Art Image Prompt. (n.d.-a). "Desert Cartoon - Sand Background". Stable Diffusion. https://stablediffusionweb.com/image/5248412-desert-cartoon-sand-background

[2] xxstudio.(n.d.-a). "Desert landscape background with sand and mountains. Vector illustration in cartoon style". Adobe Stock. https://stock.adobe.com/Library/urn:aaid:sc:VA6C2:94f23e55-2df9-4299-a548-ea999c2a6b69?asset_id=677862389

[3] Orchestralis / Background Music For Videos. (2022)."Magical Fantasy Fairytale Background Music For Commercials, Mobile Games & Kid's Films". YouTube. https://www.youtube.com/watch?v=ZA5_C4QigNw&list=RDZA5_C4QigNw&start_radio=1

[4] Der Test. (2023)."Victory Sound Effect". YouTube. https://www.youtube.com/watch?v=teUWsONJkk8

[5] dyl0n. (2019)."Something being hit - Sound Effect". YouTube. https://www.youtube.com/watch?v=JcG_ugrzfHE

[6] Marc Jungermann. (2020)."Pixie Dust & Fairy Tales | Magical Fantasy Music 🌸 Happy Uplifting Soundtrack". YouTube. https://www.youtube.com/watch?v=CdOn2NoAw8M&list=RDCdOn2NoAw8M&start_radio=1

[7] happy ?. (2021)."Punch Sound Effect.". YouTube. https://www.youtube.com/watch?v=lwYL2vs9HL4
