# valentine's website 💕

a beautiful, romantic valentine's day website with coquette aesthetics, interactive parallax effects, and customizable envelope animations

## features

- 🎀 soft pink coquette floral wallpaper background
- 🖼️ parallax effects with real images (balloons, peony flower, lipstick kiss)
- ✨ interactive elements respond to mouse movement (desktop) and device tilt (mobile)
- 🔒 password protection (default: `24July2007`)
- 💝 interactive "will you be my valentine?" question with playful buttons
- 💌 **customizable animated envelope** with adjustable paper size
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
find line ~1194 in `index.html`:
```javascript
const correctPassword = '24July2007';
```
change to your desired password:
```javascript
const correctPassword = 'mypassword';
```

### personalize the love letter
find the words around lines ~1118-1130 in `index.html`:
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

edit each line with your own words.

### 📏 adjust paper size and slide distance (FULLY CONFIGURABLE!)

find the CSS variables at the **top of the CSS section** (around line 566):

```css
:root {
    --letter-height: 500px;              /* Total paper height */
    --letter-slide-distance: 320px;      /* How far it slides out */
}
```

**to make the paper longer:**
```css
--letter-height: 600px; /* Increase for taller paper with more text lines */
```
- increase this if you need more space for text
- paper will be taller and can hold more message lines

**to make the paper slide out further (more visible above envelope):**
```css
--letter-slide-distance: 400px; /* Larger = slides further out */
```
- **this controls how much paper extends above the envelope when opened**
- larger number (e.g., 400px) = paper slides up more, more text visible
- smaller number (e.g., 250px) = paper doesn't slide as far, less text visible
- **this is the main control for how far the letter comes out of the envelope!**

**paper behavior is automatic and realistic!**
- when closed: paper sits inside the envelope at the bottom (like a real letter)
- when opened: paper slides up from inside and emerges from the top
- smooth, natural animation
- no manual adjustments needed

**example for a much longer letter:**
```css
:root {
    --letter-height: 700px;              /* Taller paper for more text */
    --letter-slide-distance: 500px;      /* Slides way up - shows more of the long paper */
}
```

### adjust text spacing on paper

find around line ~614:
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
find the image url (around line ~1120):
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

### password protection
- keeps your valentine's message private
- simple password check (can be customized)
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

### customizable love letter envelope

**how the envelope works:**
- **when closed**: paper sits inside envelope, only visible through the pocket opening (between the pink sides)
- **when opened**: 
  1. flap rotates back (goes to background)
  2. paper slides up smoothly from inside the envelope
  3. paper emerges from the pocket opening area (the space between the pink sides)
  4. envelope sides always frame the paper - creating a seamless appearance

**seamless paper clipping:**
- the paper sits **inside the envelope** when closed (like a real letter in an envelope)
- when the flap opens: you can **see the top edge of the white paper sitting inside** through the envelope opening
- **then** the paper slides **upward from inside** the envelope
- the paper emerges from the top of the envelope and becomes visible above
- when closing: paper slides back down into the envelope
- **perfectly realistic** - just like opening an envelope and pulling out a letter!

**the layering (z-index):**
- flap: rotates to background when open, covers the opening when closed
- paper: slides up and down within the clipped envelope container
- pocket (envelope sides): always on top to frame the paper and maintain the envelope appearance

**customize with 3 easy variables:**
- `--letter-height`: total paper height (default 500px)
- `--letter-slide-distance`: how far paper extends when opened (default -320px)
- `--letter-visible-closed`: no longer needed - clipping is automatic!

**how the clipping works:**
- the clipping container extends from `--letter-slide-distance` above the envelope down to the envelope bottom (180px)
- default: extends from -320px to +180px (full envelope height)
- this creates a window where the paper is visible inside and above the envelope
- the paper starts at 10px from envelope top (top edge **right at the envelope opening**)
- when the flap opens: you see the paper top sitting **exactly at the opening** before it slides
- when you click "open letter": the paper slides upward by `--letter-slide-distance` using `translateY`
- the paper emerges from the top of the envelope and becomes fully visible above
- result: realistic two-step animation - first see the paper edge at the opening, then it slides out!

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

## troubleshooting

**q: images not showing?**  
a: make sure all three PNG files are in the SAME folder as index.html. filenames are case-sensitive!

**q: parallax not working on mobile?**  
a: tap the "start" button first (required for iOS), then allow motion/orientation access when prompted. on ios, https is required (works fine on vercel).

**q: paper sticking out of envelope or phasing through the bottom?**  
a: this has been fixed! the paper is now clipped to the envelope boundaries using an invisible container. the paper will only appear within the envelope area and emerge smoothly from the pocket opening.

**q: paper doesn't slide out far enough?**  
a: increase `--letter-slide-distance` to a more negative value (e.g., -400px instead of -320px).

**q: need longer paper for more text?**  
a: increase `--letter-height` (e.g., 600px or 700px) and adjust `--letter-slide-distance` accordingly (make it more negative to slide the longer paper further out).

**q: "no" button going off screen?**  
a: this is fixed! the button calculates safe boundaries with 40px margins. if it still happens, refresh the page.

**q: envelope not opening?**  
a: make sure javascript is enabled in your browser. check the browser console (f12) for any errors.

**q: text too narrow on paper?**  
a: adjust the `.words` class: decrease `left:` value and increase `width:` value.

## tips for the best experience

- deploy to vercel for free https hosting
- test on mobile to see the tilt effects
- personalize all 13 lines of the love letter (including To: and From:)
- adjust the 2 CSS variables to get perfect paper behavior
- choose a meaningful password
- make sure all PNG images are uploaded with correct filenames
- share the link with your valentine 💕

## privacy & security

this is a **client-side only** website:
- no data is stored on servers
- password is visible in the code (don't use sensitive passwords)
- everything runs in the browser
- parallax images are loaded locally from your uploaded files
- perfect for personal romantic gestures

## quick customization checklist

- [ ] change password (line ~1194) - currently set to `24July2007`
- [ ] edit 13 lines of letter text (lines ~1118-1130) - includes To:/From: and message
- [ ] adjust paper height `--letter-height` if needed (line ~567)
- [ ] **adjust slide distance `--letter-slide-distance` for how far paper comes out** (line ~568) - **MAIN CONTROL!**
- [ ] change gif URL if desired (line ~1120)
- [ ] test envelope opening/closing animation
- [ ] test on mobile and desktop
- [ ] deploy to vercel
- [ ] share with your valentine! 💕

## license

free to use for personal valentine's projects! 💕

---

**made with love** ♡

*the best valentine's gift is one that comes from the heart*

**need help?** check the troubleshooting section or adjust the two CSS variables at the top of the file for easy paper customization!