# Muhammad Yousaf Yamin — Portfolio

A single-file, dependency-free portfolio website for a Full Stack Developer working with Flask, Django, API integrations and Python automation.

Everything (HTML, CSS, JavaScript and content) lives in one file: `Portfilo.html`. There is no build step, no framework and no package install.

## Features

- Animated intro loader and scroll progress bar
- Dark and light theme with a toggle (the choice is remembered in the browser)
- Animated network-style canvas background and aurora glow
- Typing effect in the hero section
- Scroll-reveal animations and animated stat counters
- Sections: Projects, About, Services, Skills, Experience, Education, Certifications, Testimonials, Contact
- Contact form with success message
- Custom cursor ring on desktop (hidden on touch devices)
- Responsive layout for phones, tablets and desktops
- Respects the "reduce motion" accessibility setting
- Social link previews (Open Graph and Twitter/X cards) and a favicon

## Getting started

1. Download `Portfilo.html`.
2. Open it in any modern browser (double-click the file).

To preview it with a local server instead:

```bash
python -m http.server 8000
```

Then visit <http://localhost:8000/Portfilo.html>.

## Customizing the content

Most of the text on the site is generated from one JavaScript object named `SITE_DATA`, near the bottom of `Portfilo.html`. Edit these keys to update the page:

| Key          | What it controls                          |
| ------------ | ----------------------------------------- |
| `services`   | Service cards                             |
| `skills`     | Skill categories and items                |
| `experience` | Work experience timeline                  |
| `education`  | Education and learning path               |
| `projects`   | Project cards (set `featured` to highlight a project) |
| `certs`      | Certificates and verification links       |

The hero text, About section, and contact details are written directly in the HTML above the script.

### Theme colors

Colors are CSS variables at the top of the `<style>` block (`:root` for dark, `:root[data-theme="light"]` for light). Change `--accent` and `--accent-2` to re-color the whole site.

### Contact form

The form posts to Formspree. To receive messages:

1. Create a free form at [formspree.io](https://formspree.io).
2. In `Portfilo.html`, find `FORM_ENDPOINT` and replace `https://formspree.io/f/your-form-id` with your own endpoint.

### Link preview (Open Graph)

The `<head>` already includes the title, description, Open Graph and Twitter card tags. Once the site is hosted:

1. Create a 1200×630 PNG named `preview.png` and upload it next to the HTML file.
2. In the `<head>`, uncomment the commented block and replace `muhammadyousaf.online` with your real domain.

Social platforms need full `https://` URLs for the image and page address, so this step only works after deployment. Platforms cache previews, so use their debugger tools (for example Facebook Sharing Debugger or LinkedIn Post Inspector) to refresh.

## Deployment

Because the site is a single static file, it works on any static host. Rename `Portfilo.html` to `index.html` first so it loads at your root URL.

- **GitHub Pages:** push to a repository, then enable Pages in Settings.
- **Netlify or Vercel:** drag and drop the folder, or connect the repository.
- **Cloudflare Pages:** connect the repository, with no build command.

## Tech

- HTML5, CSS3 (custom properties, grid, flexbox)
- Vanilla JavaScript (IntersectionObserver, Canvas API)
- Google Fonts: Manrope and JetBrains Mono (loaded from the web, with system fallbacks)

## Browser support

Current versions of Chrome, Edge, Firefox and Safari.

## Contact

- GitHub: [myy475855-code](https://github.com/myy475855-code)

## License

All rights reserved unless you add a license. If you want others to reuse the code, consider adding an open-source license such as MIT.
