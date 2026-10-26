# Muhammad Yousaf Yamin — Developer Portfolio

A developer portfolio in two versions, all single files with no build step:

| File | What it is |
| --- | --- |
| `index.html` | **3D room.** Walk around an interactive room and explore the portfolio like a mini game. |
| `portfilo.html` | **Classic site.** A modern, animated one-page portfolio with dark and light themes. |

**Live site:** https://myy475855-code.github.io/Portfilo

---

## 3D room (`index.html`)

Built with Three.js (included in the file, so it works offline).

### Controls

| Action | Desktop | Phone / tablet |
| --- | --- | --- |
| Move | `W` `A` `S` `D` or arrow keys (`Shift` to sprint) | Left on-screen stick |
| Look around | Drag the mouse (or `Q` / `Z` to turn) | Drag the right side of the screen |
| Interact | Click a glowing marker, or press `E` when near one | Tap a glowing marker |
| Jump to a spot | Keys `1`–`7`, or the bottom bar | Bottom bar |
| Guided tour | `T`, or the **Tour** button | **Tour** button in the bottom bar |
| Day / night | `N`, or the ☀️ / 🌙 button | ☀️ / 🌙 button (top right) |
| Close a panel | `Esc` or the ✕ button | ✕ button |

### What's in the room

| Spot | Opens |
| --- | --- |
| Desk monitor | Projects (featured work and the full filterable list) |
| CV on the desk | CV download |
| Bookshelf | Skills and services |
| Whiteboard | Experience and education |
| Certificate wall | Certificates, each linking to its verification page |
| Poster | About me |
| Door | Contact details and message form |

### Guide character

A low-poly version of you (hoodie with the MYY logo, headphones and glasses) walks in through the door, waves and offers a tour. On the tour he walks to each station, points at it and explains it in a speech bubble, and the camera follows him. Each stop has **Open** (shows the full panel), **Next** and **✕** (end tour) buttons. Outside the tour he wanders between stations on his own, and you can click him to start a tour. His lines are in the `SPOTS` object in `room.html`.

### Day and night

The room has a night mode (neon and dark walls) and a day mode (bright walls, sky and sun through the window). It starts by local time (day from 6:00 to 18:00), and your choice is remembered in the browser.

### Game features

- Logo loader and start screen.
- Walking guide character with a guided tour and idle wandering.
- Day / night mode.
- Collision with furniture and walls.
- Minimap showing your position and each spot.
- "Explored X / 7" progress counter, unlock messages, and confetti when you finish.
- A "Classic" button that links to `portfilo.html`.

If a browser or device can't run WebGL, the page shows a link to the classic site.

---

## Classic site (`portfilo.html`)

- Logo loader, animated particle-network background, word-by-word hero reveal and typewriter role line.
- Featured projects with a cursor spotlight, plus a collapsible list with tag filters.
- Bento-style About section, services, skills, and an experience timeline that fills as you scroll.
- Education and certifications, contact section with copy buttons and a form.
- Dark and light themes (saved in the browser), mobile menu, keyboard focus styles, and reduced-motion support.

---

## Run locally

Open either file in a modern browser, or serve the folder:

```bash
python3 -m http.server 8000
# visit http://localhost:8000/index.html  or  /portfilo.html
```

Keep all files in the same folder so the links between them work.

## Deploy on GitHub Pages

1. Put `index.html`, `portfilo.html` and this `README.md` in the root of your repository.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute or two the site is live at `https://<username>.github.io/<repository>`. The 3D room is the home page and the classic site is at `/portfilo.html`.

## Customize

Content lives in a `SITE_DATA` object inside the script of each file. `portfolio-data.json` is a copy of the same data for reference; the pages do not read it, so edit the HTML files directly (the same change is needed in each).

| Key | What it controls |
| --- | --- |
| `projects` | Project cards and lists. `featured: true` shows a project in "Selected work". |
| `services` | Service cards |
| `skills` | Skill groups and tags |
| `experience` | Timeline entries |
| `education` | Education cards |
| `certs` | Certificates and their links |

Other changes:

- **CV:** replace the `CV_BASE64` string in each file with your PDF encoded as base64: `base64 -w 0 your-cv.pdf`.
- **Colors:** edit the CSS variables at the top (`--accent`, `--accent-2`, `--bg`, and so on).
- **Typed role lines (classic site):** the `lines` array in the typewriter section.
- **Room layout (3D room):** furniture and spot positions are set in the scene code of `index.html`.

## Contact form setup

Both forms need an endpoint to deliver messages directly. Until one is set, submitting opens the visitor's email app instead.

1. Create a free form at [Formspree](https://formspree.io) (or use EmailJS).
2. In `index.html` and `portfilo.html`, replace the placeholder:
   ```js
   const FORM_ENDPOINT = "https://formspree.io/f/your-form-id";
   ```

## Tech notes

- Plain HTML, CSS and JavaScript; the classic site draws its background with Canvas, the room uses WebGL.
- Fonts (Manrope, JetBrains Mono) load from Google Fonts; pages still work with fallback fonts if offline.
- `index.html` is about 1 MB because Three.js, your logo and the CV are embedded.

## Contact

- Email: myy475855@gmail.com
- GitHub: [myy475855-code](https://github.com/myy475855-code)
- LinkedIn: [muhammad-yousaf](https://www.linkedin.com/in/muhammad-yousaf-905532391/)
- WhatsApp: [+92 326 5511189](https://wa.me/923265511189)

## License

© Muhammad Yousaf Yamin. All rights reserved. Please don't copy the content, projects or branding without permission.
