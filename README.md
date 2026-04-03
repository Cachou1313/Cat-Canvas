Pet Project
An interactive web app that demonstrates real-time text reflow around moving objects using the Pretext concept and the HTML5 Canvas API. Drag, throw, and watch your pets float around the screen while cat and dog facts reflow around them live.

Demo
Live site: cat-canvas.vercel.app

Features

Real-time text reflow around circular image shapes using ellipse math
Three draggable die-cut pet photos with white bezel and drop shadow styling
Floating physics animation with organic sine-wave drift
Elastic circle-to-circle collision detection and response
Throw mechanics — fling a pet and watch it carry momentum before easing back to float speed
Speed control dropdown with four settings including a secret fifth option
Dark charcoal UI with warm white text
Fully responsive


Concepts Applied
Pretext (Text Reflow)
Inspired by Cheng Lou's Pretext concept. For every line of text, available horizontal segments are computed based on the circular shape of each pet at that vertical position. The entire layout recalculates from scratch on every frame a pet moves.
Canvas API
All text is rendered directly onto an HTML5 canvas element using the 2D rendering context. Word widths are measured with measureText and each word is placed with fillText at precise coordinates within available segments.
Ellipse Collision Math
Each pet is modeled as a circle. The ellipse equation determines the blocked horizontal range on each line of text, with a margin added for visual breathing room between the image edge and the text.
Physics Simulation
Each pet has a base linear velocity combined with a per-pet sine wave offset, creating organic non-repeating float motion. Elastic collision detection computes the distance between each pair of pet centers, separates overlapping circles, and swaps velocity components along the collision axis.
Throw Mechanics
Mouse delta is tracked frame-by-frame while dragging. On release that velocity is applied to the pet directly. A lerp at 2.5% per frame gradually transitions the throw velocity back to the pet's original base float speed.
Layered Rendering Architecture
Text lives on a canvas element. Pet images live in a separate absolutely-positioned DOM layer above it, styled with CSS border-radius for the circular crop, a white border for the bezel, and layered box-shadows for depth. This keeps CSS styling and canvas precision fully separate.

Project Structure
Cat-Canvas/
├── index.html      # Full application, single file
├── Cachou.png      # Sphynx cat photo
├── neo.png         # Black cat photo
├── polly.png       # Mastiff photo
└── README.md

Getting Started
No build tools or dependencies required. It is a single self-contained HTML file.
Run locally
Just open index.html in any modern browser.
Deploy to Vercel

Push to GitHub
Import the repo at vercel.com/new
Leave all settings as default and click Deploy

Vercel will auto-deploy on every future push to main.

Built With

HTML5 Canvas API
Vanilla JavaScript
CSS3


Author
Reese Spaulding