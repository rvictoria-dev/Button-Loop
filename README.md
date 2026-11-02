# Button Loop

### ₊⊹ About

An animated button with a bold, minimalist look: a black pill-shaped button with white uppercase text.
When you hover over it, the text gradually disappears and a looping text strip takes its place, displaying the word across the button.
Everything works with pure HTML and CSS, without the use of JavaScript.
It’s a small project designed to explore keyframes, hover states, and smooth transitions.

https://github.com/user-attachments/assets/3240a06c-e925-47b3-8238-566727209600

---

### ★ Features

- Bold black button in a pill shape, with white uppercase text
- When the cursor hovers over it, the label gradually fades away and a scrolling text version gradually appears
- The text scrolls continuously from left to right in a continuous loop
- The animation is displayed only while the cursor is over the button and pauses when it moves away
- Smooth opacity transition between the normal state and the animated state
- Rounded corners with `overflow: hidden`, so that the scrolling text is cropped by the pill shape

---

### .ᐟ.ᐟ How It Works

1. **Two layers:** The button has two `span` elements with the same word. The `.text` is the fixed text, positioned on top with `position: absolute`. The `.marquee` remains in the normal page flow, which also defines the button’s width.
2. **Hidden by default:** the `.marquee` starts with `opacity: 0` and `animation-play-state: paused`, so the button looks like a simple black pill.
3. **Hover:** on `:hover`, the `.marquee` appears (`opacity: 1`), the `.text` disappears (`opacity: 0`), and the animation changes to `running`. Both transitions use a `0.2s` duration.
4. **Motion:** The `keyframes` for the `marquee` move the text using `translateX` from `--start` (`0em`) to `--end` (`5em`) in 1 second, with `linear` timing and `infinite` looping.
5. **Continuous loop:** The `text-shadow` draws copies of the word every `--spacing` (`5em`). When the text reaches `5em`, the copy that was at `-5em` is exactly where the original started, so the restart isn’t visible.
6. **Crop:** The button’s `overflow: hidden` and `border-radius: 99rem` crop the text that extends beyond the pill’s edges.
7. **Adjustments:** To change the effect, edit the CSS variables. `--spacing` and `--end` must always have the same value for the loop to remain continuous.

---

### ⚙️ Tech Stack

- **HTML5**
- **CSS3**

---

### 🖿 Project structure

```
button-loop/
├── index.html
├── Styles.css
└── README.md
```

---

### 📖 What i learned

- **HTML:** Overlap two `span` elements inside a `button`, one for the static text and one for the animated text
- **CSS:** `@keyframes` with `translateX` to move the text in a continuous loop
- **CSS:** Use `text-shadow` to repeat the text on both sides and ensure the loop is seamless
- **CSS:** custom properties (`--spacing`, `--start`, `--end`) to control the animation
- **CSS:** `animation-play-state` changing from `paused` to `running` on `:hover`
- **CSS:** `overflow: hidden` and `border-radius` to crop the moving text within the pill
- **CSS:** `opacity` transitions to smoothly switch between static and animated text
