Personal Website — Claude Code Context
Project overview
Static personal website built with plain HTML, CSS, and JavaScript.
Deployed to GitHub Pages at https://yourusername.github.io.
Design system
This project uses the beaucoup design system extracted by skillui.
Always read SKILL.md before writing any UI code. Then consult the references below as needed.
FileWhen to read itSKILL.mdEvery session, before touching any UIreferences/DESIGN.mdColors, typography, spacing tokensreferences/ANIMATIONS.mdAny hover, scroll, or transition effectreferences/LAYOUT.mdPage structure, grid, containersreferences/COMPONENTS.mdButtons, cards, nav, any reusable elementscreens/scroll/Study before implementing scroll behavior
Site structure
Single-page layout with four sections, in order:

Hero / about me — name, tagline, short bio, primary CTA
Projects — card grid showcasing work with title, description, tech stack, links
Work experience / CV — timeline or list of roles, downloadable PDF option
Contact — email link or form, social links (GitHub, LinkedIn, etc.)

All sections live in index.html. Styles in style.css. Any interactivity in main.js.
File structure
/
├── index.html
├── style.css
├── main.js
├── assets/
│ ├── images/
│ └── cv.pdf
├── SKILL.md
├── CLAUDE.md
└── references/
├── DESIGN.md
├── ANIMATIONS.md
├── LAYOUT.md
└── COMPONENTS.md
Coding rules

No frameworks, no build step — plain HTML/CSS/JS only
CSS custom properties for all design tokens (colors, spacing, type)
Mobile-first responsive design; test at 375px, 768px, 1280px
Semantic HTML (<section>, <nav>, <article>, <time>, etc.)
Images use loading="lazy" and always have alt text
No external JS libraries unless explicitly approved

GitHub Pages deployment

Everything must work from index.html at the repo root on the main branch
No server-side code, no build artifacts to commit
Asset paths must be relative (e.g. ./assets/images/photo.jpg, not /assets/...)
After pushing, the site is live at https://axinailedit.github.io/<repo-name>

Current status

Project scaffolded
Design tokens from SKILL.md applied to style.css
Hero section
Projects section
Work experience section
Contact section
Responsive QA
Deployed to GitHub Pages

Notes

<!-- Add decisions, known issues, or things to remember here as you build -->
