# valentine's website 💕

a beautiful, romantic valentine's day website with coquette aesthetics, interactive parallax effects, and customizable envelope animations

## features

- 🎀 soft pink coquette floral wallpaper background
- 🖼️ parallax effects with real images (balloons, peony flower, lipstick kiss)
- ✨ interactive elements respond to mouse movement (desktop) and device tilt (mobile)
- 🔒 password protection with multiple accepted variations (case-insensitive)
- 💝 interactive "will you be my valentine?" question with playful buttons
- 💌 **customizable animated envelope** with adjustable paper size and automatic downward movement
- 💖 natural heart explosion animation
- 📱 fully responsive (works on mobile, tablet, and desktop)

## quick deploy to vercel

### easiest way - drag and drop
1. go to [vercel.com](https://vercel.com)
2. drag your project folder onto the upload area
3. click "deploy"
4. done! 🎉

### from github
1. upload all files to a new github repository
2. go to [vercel.com](https://vercel.com) and click "add new project"
3. import your repository
4. click "deploy"

### using vercel cli
```bash
npm i -g vercel
vercel
```

## file structure
```
valentine-website/
├── index.html                                                        # main file
├── vercel.json                                                      # vercel config
├── README.md                                                        # this file
├── _CITYPNG_COM_HD_Realistic_Red_Balloons_Hearts_Valentine_Love_PNG_-_1500x1500.png
├── pngtree-pink-peony-flower-isolated-png-image_12980484.png
└── pinup-style-lip-print.png
```

**important**: make sure all three PNG image files are in the same folder as index.html!

## customization

### change the password
find line ~1200 in `index.html`:
```javascript
// Multiple acceptable password variations (case-insensitive)
const correctPasswords = [
    '24july2007',
    '24jul2007',
    '24072007',
    '2472007',
    '2472550',
    '24072550'
];
```

**default passwords accepted (case-insensitive):**
- `24july2007` or `24JULY2007` or `24JuLy2007` (any case)
- `24jul2007` (abbreviated month)
- `24072007` (numeric date)
- `2472007` (without leading zero)
- `2472550` (alternative number)
- `24072550` (alternative full date)

to add or change passwords, simply edit the array:
```javascript
const correctPasswords = [
    'yourpassword1',
    'yourpassword2',
    'yourpassword3'
];
```

### personalize the love letter
find the words around lines ~1137-1149 in `index.html`:
```html
<div class="words line1">To: Mook</div>
<div class="words line2">It's been almost a year since we met,</div>
<div class="words line3">and I've loved every minute of it. Your style,</div>
<div class="words line4">your voice, the way you carry yourself...</div>
<div class="words line5">and even just your smile. EVERYTHING</div>
<div class="words line6">about you makes my heart skip a beat.</div>
<div class="words line7">I've liked you for a long time, and even</div>
<div class="words line8">though I can't be there physically right now,</div>
<div class="words line9">will you be my Valentine? I'd love to take</div>
<div class="words line10">you somewhere truly nice when I'm</div>
<div class="words line11">finally there with you. I love you ♡</div>
<div class="words line12"></div>
<div class="words line13">From: Jin</div>
```

**you have 13 lines** to write your message! 
- line1 is for "To: [name]" (top left)
- lines 2-11 are for your main message
- line12 can be left empty or used for extra text
- line13 is for "From: [name]" (bottom right)

**tips for better text layout:**
- keep lines relatively short to prevent word wrapping
- if a word breaks to the next line, shorten the sentence
- line13 (From:) is now fully visible with the increased slide distance!

### 📏 adjust paper size and slide distance

find the CSS variables at the **top of the CSS section** (around line 563):

```css
:root {
    --letter-height: 500px;              /* Total paper height */
    --letter-slide-distance: 400px;      /* How far paper slides up (default increased to 400px) */
}
```

**paper slide distance increased to 400px** (was 320px) to show more text including the "From:" line!

**envelope automatically moves down when opening** to reveal even more of the letter (60px on desktop, 40px on mobile)

**mobile automatically scales differently:**
- envelope: 220x140px (vs 280x180px desktop)
- slide distance: 250px (vs 400px desktop)
- text size: 0.75rem (vs 0.95rem desktop)
- all optimized for small screens!

**to make the paper longer:**
```css
--letter-height: 600px; /* Increase for taller paper with more text lines */
```
- increase this if you need more space for text
- paper will be taller and can hold more message lines

**to make the paper slide out further:**
```css
--letter-slide-distance: 450px; /* Larger = slides further out */
```
- larger number (e.g., 450px) = paper slides up more, more text visible
- smaller number (e.g., 350px) = paper doesn't slide as far

**example for a much longer letter:**
```css
:root {
    --letter-height: 700px;              /* Taller paper for more text */
    --letter-slide-distance: 550px;      /* Slides way up - shows more of the long paper */
}
```

### adjust text spacing on paper

find around line ~640:
```css
.words {
    position: absolute;
    left: 5%;      /* Distance from left edge */
    width: 90%;    /* Text width */
}
```

**to make text wider (closer to edges):**
```css
left: 3%;       /* Smaller left margin */
width: 94%;     /* Wider text */
```

**to make text narrower (more centered):**
```css
left: 10%;      /* Larger left margin */
width: 80%;     /* Narrower text */
```

### change the background
in the CSS (around line 19), you can change the background image:
```css
background: url('YOUR_IMAGE_URL') no-repeat center center fixed !important;
```

current background uses a coquette floral wallpaper. you can:
- upload your own image and reference the filename
- use a different url from pinterest/unsplash
- search: "pink floral wallpaper", "vintage ribbon pattern", "coquette background"

### change the gif
find the image url (around line ~1106):
```html
<img src="https://media.giphy.com/media/..." alt="cute cat">
```

get gifs from:
- [giphy](https://giphy.com)
- [tenor](https://tenor.com)

right-click → "copy image address" → paste into the `src=""` attribute

### adjust colors

main pink palette:
```css
#ffb3c1  /* soft pink - decorative hearts */
#ffc9d4  /* light pink - ribbons */
#ffe5ec  /* very light pink - accents */
#d4738d  /* accent pink - headings */
#8b5a6f  /* text brown-pink */
#ff4081  /* hot pink - yes button */
#ffc0cb  /* baby pink - no button */
```

use find & replace (ctrl+f or cmd+f) to change these throughout the file.

## how parallax works

### desktop
- move your mouse around the screen
- decorative elements (balloons, peony, lipstick, hearts, ribbons, flowers) follow your cursor at different speeds
- creates a subtle 3d depth effect

### mobile
- tilt your phone/tablet in any direction
- elements respond to device orientation using gyroscope
- give permission for motion/orientation when prompted
- tap the "start" button to enable sensors on iOS

## features explained

### parallax images
three decorative images move with your cursor or device tilt:

1. **balloons** (bottom left) - tilted 35° coming out from corner
2. **peony flower** (bottom right) - opening toward center
3. **lipstick kiss** (top right) - classic pin-up style

### password protection (NEW: multiple variations!)
- accepts **6 different password variations** (case-insensitive!)
- enter any of: 24july2007, 24jul2007, 24072007, 2472007, 2472550, or 24072550
- passwords work in ANY case (lowercase, uppercase, mixed)
- keeps your valentine's message private
- password is stored in the code (not server-side)

### interactive "no" button
- shrinks each time you hover/click it (text scales too)
- moves to a random position
- **stays on screen** with 40px safety margins (never goes off the edge)
- "yes" button grows bigger each time (text scales too)

### heart explosion
- 40 hearts burst out naturally when "yes" is clicked
- random directions (full 360°), sizes, and rotations
- vibrant red/pink colors
- organic physics animation with natural easing

### customizable love letter envelope (NEW: auto-moves down!)

**enhanced opening animation:**
- **when closed**: paper sits inside envelope
- **when opened**: 
  1. flap rotates back (goes to background)
  2. **envelope moves down 60px** (40px on mobile) to reveal more text
  3. paper slides up 400px from inside the envelope
  4. paper emerges from the pocket opening
  5. "From:" signature at bottom is now fully visible!

**seamless paper clipping:**
- the paper sits **inside the envelope** when closed (like a real letter)
- when the flap opens: you see the top edge of the paper sitting inside
- paper slides **upward from inside** the envelope
- paper emerges from the top and becomes visible above
- when closing: paper slides back down into the envelope
- **perfectly realistic** - just like pulling a letter from an envelope!

**the layering (z-index):**
- flap: rotates to background when open
- paper: slides up and down within the envelope
- pocket (envelope sides): always on top to frame the paper
- **envelope itself moves down** to show more of the emerging letter

**customize with 2 easy variables:**
- `--letter-height`: total paper height (default 500px)
- `--letter-slide-distance`: how far paper extends when opened (default 400px - increased!)

**envelope downward movement:**
- automatically moves down 60px on desktop when opened
- automatically moves down 40px on mobile when opened
- smooth transition synchronized with letter slide animation
- creates more space to show the full letter including "From:" signature

### floating hearts from envelope
- 3 hearts float up when envelope opens
- all float to roughly the same height
- gentle side-to-side swaying motion
- different sizes for visual variety

## browser compatibility

✅ chrome/edge (desktop & mobile)  
✅ safari (desktop & mobile) - requires start button for sensors  
✅ firefox (desktop & mobile)  
⚠️ internet explorer: not supported

## technologies used

- html5 & css3
- vanilla javascript (no frameworks)
- google fonts (dancing script, cormorant garamond, mrs saint delafield)
- device orientation api (for mobile tilt)
- css custom properties (variables) for easy customization
- css clip-path for smooth envelope animations
- css transforms for envelope movement animation

## troubleshooting

**q: images not showing?**  
a: make sure all three PNG files are in the SAME folder as index.html. filenames are case-sensitive!

**q: parallax not working on mobile?**  
a: tap the "start" button first (required for iOS), then allow motion/orientation access when prompted. on ios, https is required (works fine on vercel).

**q: "From: Jin" not visible at bottom?**  
a: this is now fixed! slide distance increased to 400px and envelope moves down 60px when opened.

**q: password not working?**  
a: try these variations (case doesn't matter):
- 24july2007
- 24jul2007
- 24072007
- 2472007
- 2472550
- 24072550

**q: words breaking to next line (like "style" or "now")?**  
a: shorten the sentence slightly. for example:
- instead of: "and I've loved every minute of it. Your style,"
- try: "and I've loved every minute of it. Your"
- then: "style, your voice, the way you carry yourself..."

**q: paper doesn't slide out far enough?**  
a: increase `--letter-slide-distance` (e.g., 450px instead of 400px).

**q: need longer paper for more text?**  
a: increase `--letter-height` (e.g., 600px) and increase `--letter-slide-distance` (e.g., 500px) to show the longer paper.

**q: "no" button going off screen?**  
a: this is fixed! the button calculates safe boundaries with 40px margins. if it still happens, refresh the page.

**q: envelope not opening?**  
a: make sure javascript is enabled in your browser. check the browser console (f12) for any errors.

**q: text too narrow on paper?**  
a: adjust the `.words` class: decrease `left:` value and increase `width:` value.

**q: mobile envelope looks warped or text visible through gaps?**  
a: this is now fixed! envelope is scaled to 220x140px on mobile with properly proportioned flap and pocket.

**q: mobile container too long or not centered?**  
a: this is now fixed! containers are properly centered with max-width: 400px and centered using flexbox.

**q: mobile letter slides too far up?**  
a: this is now fixed! mobile uses 250px slide distance (vs 400px desktop) and text is sized smaller (0.75rem) to fit properly.

## tips for the best experience

- deploy to vercel for free https hosting
- test on mobile to see the tilt effects
- **keep text lines short** to prevent word wrapping issues
- personalize all 13 lines of the love letter (including To: and From:)
- adjust the 2 CSS variables to get perfect paper behavior
- any of the 6 password variations will work (case doesn't matter!)
- make sure all PNG images are uploaded with correct filenames
- watch the envelope move down as the letter slides out!
- share the link with your valentine 💕

## privacy & security

this is a **client-side only** website:
- no data is stored on servers
- password is visible in the code (don't use sensitive passwords)
- everything runs in the browser
- parallax images are loaded locally from your uploaded files
- perfect for personal romantic gestures

## quick customization checklist

- [ ] change passwords in array (line ~1200) - currently accepts 6 variations
- [ ] edit 13 lines of letter text (lines ~1137-1149) - includes To:/From: and message
- [ ] adjust paper height `--letter-height` if needed (line ~563)
- [ ] adjust slide distance `--letter-slide-distance` for how far paper comes out (line ~564) - default now 400px
- [ ] shorten long sentences if words are breaking to next line
- [ ] change gif URL if desired (line ~1106)
- [ ] test envelope opening/closing animation with downward movement
- [ ] test password variations (any case works!)
- [ ] test on mobile and desktop
- [ ] deploy to vercel
- [ ] share with your valentine! 💕

## what's new in this version

✅ **slide distance increased to 400px** (was 320px) - "From:" signature now visible on desktop!  
✅ **envelope moves down** when opened (60px desktop, 40px mobile) - shows even more text!  
✅ **multiple password support** - accepts 6 different variations (case-insensitive)  
✅ **mobile optimizations** - envelope scaled to 220x140px, slide distance 250px for mobile  
✅ **mobile text sizing** - smaller fonts prevent overlaps on small screens  
✅ **mobile containers fixed** - proper centering and no more elongation  
✅ **mobile envelope proportions** - properly scaled flap and pocket for smaller screens  
✅ **smooth envelope movement** - synchronized with letter animation on all devices  

## license

free to use for personal valentine's projects! 💕

---

**made with love** ♡

*the best valentine's gift is one that comes from the heart*

**need help?** check the troubleshooting section or adjust the two CSS variables for easy customization. the envelope now automatically moves down to show your full message!