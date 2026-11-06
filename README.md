# Happy Diwali: Festival of Lights

A full-screen, interactive Diwali celebration that runs entirely from one HTML file. It fills the screen with twinkling LED lights, hanging light strings, glowing diyas, rising sky lanterns, a slowly turning rangoli and fireworks. It is designed for desktop monitors, laptops and large office displays.

## Quick start

1. Download `index.html`.
2. Double-click it to open it in a modern browser (Chrome, Edge, Firefox or Safari).
3. Press **F** to go full screen.

You don't need a server, an internet connection, an install step or a build step. All the HTML, CSS and JavaScript are inside the one file, and it uses no external libraries or downloaded fonts.

## What you'll see

- **Twinkling lights**: 700 to 2,600 LED-style lights, depending on screen size. Some twinkle softly, some blink on and off, and large soft orbs drift slowly upward. Lights behind the greeting are dimmed so the text stays readable.
- **Hanging light strings**: three layers of strings drape across the top of the screen, with curtain-light strands down both sides. They sway gently and run through four patterns: twinkle, chase, color wave and breathe.
- **Diyas**: a row of clay diyas with flickering flames along the bottom. They light up one by one when the page opens.
- **Greeting**: "Happy Diwali" glows in letter by letter. Above it, the line alternates between Hindi (शुभ दीपावली) and Bangla (শুভ দীপাবলি) every 5 seconds. Below it are an editable message and sender line.
- **Fireworks**: five burst styles (peony, ring, golden willow, crackling chrysanthemum and double ring), each with fading trails. They launch automatically at random intervals.
- **Sky lanterns and rangoli**: lanterns rise through the scene, and a multicolored rangoli rotates faintly behind the greeting.

## Controls

### Mouse

| Action | Result |
| --- | --- |
| Click the sky | Launches a firework that bursts where you clicked |
| Click a diya | Makes its flame flare up with sparks |
| Move the mouse | Leaves a sparkler trail |

### Keyboard

| Key | Action |
| --- | --- |
| Space | Grand finale (a volley of 14 fireworks) |
| A | Turn automatic fireworks on or off |
| L | Change the light pattern: auto, twinkle, chase, color wave or breathe |
| E | Edit the message and sender line |
| H | Hide or show the greeting |
| F | Enter or exit full screen |

The same controls are available as buttons in the dock at the bottom right. In **auto** mode, the light pattern changes every 12 seconds.

## Customizing the message

1. Press **E**, or click **Edit message**.
2. Click the message or the sender line and type your text.
3. Press **Enter** or **Esc**, or click **Save message**.

Your text is saved in the browser's local storage, so it stays the same the next time you open the file in that browser on that computer. To change the main "Happy Diwali" title or the Hindi and Bangla lines, edit them directly in `index.html`. The relevant elements are `#title` and the `.hi-line` spans.

## Running on an office display

- After about 3.5 seconds without mouse or keyboard activity, the control dock and the cursor fade out, which leaves a clean screen. Move the mouse to bring them back.
- On very large or 4K screens, the rendering resolution is capped automatically so the animation stays smooth.
- If the operating system's reduced-motion setting is on, automatic fireworks start off, the animation slows down and there are fewer lanterns.
- The page plays no sound.

## Fonts

The page uses only fonts already installed on the computer, so it works offline.

| Text | Windows | macOS | Fallback |
| --- | --- | --- | --- |
| Hindi | Nirmala UI, Mangal | Kohinoor Devanagari | Noto Sans Devanagari |
| Bangla | Nirmala UI, Vrinda, Shonar Bangla | Kohinoor Bangla, Bangla MN | Noto Sans Bengali |
| Title and message | Palatino Linotype | Palatino | Georgia, serif |

If the Hindi or Bangla text shows as empty boxes, install the matching Noto Sans font for that script.

## How it's built

- **One canvas for the scene.** The sky gradient and the rangoli are drawn once into hidden canvases and copied to the screen each frame. Lights are drawn from pre-rendered glow images, which keeps thousands of lights fast.
- **A separate fireworks layer.** Fireworks and sparks are drawn on their own canvas that fades a little each frame, which creates the trails.
- **HTML for text and controls.** The greeting and the control dock are regular HTML on top of the canvas, so the text stays sharp and accessible.
- **Smooth timing.** The animation runs on `requestAnimationFrame` and is based on elapsed time, so it moves at the same speed on 60 Hz and 144 Hz displays.

## Browser support

The page works in current versions of Chrome, Edge, Firefox and Safari. Full screen and local storage depend on browser permissions. If local storage is blocked, an edited message still shows but isn't remembered after you close the page.

## Files

```
index.html   The complete experience (HTML, CSS and JavaScript in one file)
README.md    This file
```
