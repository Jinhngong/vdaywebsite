# valentine's website 💕

a beautiful, romantic valentine's day website with coquette aesthetics and interactive parallax effects

## features

- 🎀 soft pink coquette wallpaper background
- ✨ parallax effects (mouse movement on desktop, device tilt on mobile)
- 🔒 password protection (default: `valentine2025`)
- 💝 interactive "will you be my valentine?" question
- 💌 animated envelope that opens to reveal your love letter
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
├── index.html       # main file with everything
├── vercel.json      # vercel deployment config
└── README.md        # this file
```

## customization

### change the password
find line ~942 in `index.html`:
```javascript
const correctPassword = 'valentine2025';
```
change to your desired password:
```javascript
const correctPassword = 'mypassword';
```

### personalize the love letter
find the words around line ~858 in `index.html`:
```html
<div class="words line1">to: you</div>
<div class="words line2">i still get butterflies</div>
<div class="words line3">every time i see you</div>
<div class="words line4">and i hope i always do</div>
```

make it your own! write something from the heart.

### change the background
in the CSS (around line 14), you can change the background image:
```css
background: #fef5f5 url('YOUR_IMAGE_URL') repeat;
```

current background uses a coquette floral wallpaper. you can:
- upload your own image and reference the filename
- use a different url from pinterest/unsplash
- search: "pink floral wallpaper", "vintage ribbon pattern", "coquette background"

### change the gif
find the image url (around line 846):
```html
<img src="https://media.giphy.com/media/..." alt="cute">
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
- decorative elements (hearts, ribbons, flowers) follow your cursor at different speeds
- creates a subtle 3d depth effect

### mobile
- tilt your phone/tablet
- elements respond to device orientation
- give permission for motion/orientation when prompted

## features explained

### password protection
- keeps your valentine's message private
- simple password check (can be customized)
- password is stored in the code (not server-side)

### interactive "no" button
- shrinks each time you hover/click it
- moves to a random position
- **stays on screen** (never goes off the edge)
- "yes" button grows bigger each time

### heart explosion
- 40 hearts burst out naturally when "yes" is clicked
- random directions, sizes, and rotations
- vibrant red/pink colors
- organic physics animation

### love letter envelope
- click to open the envelope
- hearts float up when opened
- click "close" to reset it
- smooth animations

## browser compatibility

✅ chrome/edge (desktop & mobile)  
✅ safari (desktop & mobile)  
✅ firefox (desktop & mobile)  
⚠️ internet explorer: not supported

## technologies used

- html5 & css3
- vanilla javascript
- google fonts (dancing script, cormorant garamond, mrs saint delafield)
- device orientation api (for mobile tilt)

## troubleshooting

**q: background image not showing?**  
a: the background uses an external url. if it's not loading, you can replace the url with a different coquette wallpaper or download and host it locally.

**q: parallax not working on mobile?**  
a: allow motion/orientation access when prompted by your browser. on ios, this may require https (works fine on vercel).

**q: "no" button going off screen?**  
a: this should be fixed! the button calculates safe boundaries. if it still happens, try refreshing the page.

**q: envelope not opening?**  
a: make sure javascript is enabled in your browser. check the browser console (f12) for any errors.

## tips for the best experience

- deploy to vercel for free https hosting
- test on mobile to see the tilt effects
- personalize the love letter message
- choose a meaningful password
- share the link with your valentine 💕

## privacy & security

this is a **client-side only** website:
- no data is stored on servers
- password is visible in the code (don't use sensitive passwords)
- everything runs in the browser
- perfect for personal romantic gestures

## license

free to use for personal valentine's projects! 💕

---

**made with love** ♡

*the best valentine's gift is one that comes from the heart*