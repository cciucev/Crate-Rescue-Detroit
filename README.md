# Crate Rescue: Detroit

A browser game about blind inventory in construction. Extra building materials hide in six
real Detroit construction yards. A drone scans the yards, a built-in AI dispatcher suggests
where each crate should go, and robot trucks deliver them before they are thrown away.
The city refuses trips that can't work, and the AI learns from its mistakes.

## What's in this folder

| File | What it does |
| --- | --- |
| `index.html` | The page: top bar, game board, AI dispatcher panel, and the "For grown-ups" explainer |
| `css/styles.css` | All the styling, including light and dark mode |
| `js/detroit-map.js` | The simplified Detroit street map and the shortest-route finder for trucks |
| `js/game.js` | The game: crates, drone, AI dispatcher, trucks, refusals, score |
| `favicon.svg` | The little crate icon in the browser tab |
| `og-image.png` | The preview picture that shows up when someone shares the link |

It is a static site: no server, database, build step or account is needed.

## Try it on your computer

Double-click `index.html`. It opens in your browser and plays right away. (The game's fonts
load from Google Fonts, so the lettering looks best with an internet connection.)

## Put it online (free options)

**Netlify Drop (easiest, about a minute).** Go to https://app.netlify.com/drop and drag
this whole folder onto the page. Netlify gives you a public link. Make a free account if you
want to keep the site and choose a nicer name.

**GitHub Pages.** Create a new public repository on GitHub, upload everything in this
folder (keep the `css` and `js` folders as they are), then open the repository's
Settings, find Pages, and publish from the main branch's root folder. Your site appears at
`https://<your-username>.github.io/<repository-name>/` after a minute or two.

Cloudflare Pages and Vercel work the same way: upload the folder as a static site.

**After it's online:** open `index.html`, find the line with `og:image`, and replace
`og-image.png` with the full address, for example
`https://your-site.netlify.app/og-image.png`. That makes the preview picture show up
reliably when you share the link.

## Change how it plays

The first lines of `js/game.js` hold the main numbers:

- `WEEKS` - how many weeks a season lasts (12)
- `WEEK_SEC` - seconds per week (6)
- `CAP` - crates a robot truck can carry (6)
- `TIME_KM` - kilometers of street a delivery can cover in time (7)
- `TRASH_AGE` - weeks before an unused crate is thrown out (4)
- `NEED_WEEKS` - weeks a builder waits before buying new (3)

The six sites and the warehouse are in the `PL` list just below. Each has a location, yard
size, how much extra it receives each week (`rate`), what it receives (`mix`), and how often
it needs material (`needRate`, `needMix`). All the words on the page, including the start
screen and the explainer, are in `index.html`.

## What's real

The six sites are real Detroit projects under way in 2026: the Henry Ford Hospital tower,
The Claire, Midtown West, the U-M Center for Innovation, the JW Marriott at Water Square and
AlumniFi Field. The Reuse Warehouse stands for the Architectural Salvage Warehouse of Detroit.
The road closure near AlumniFi Field is MDOT's 2026 Michigan Ave rebuild in Corktown. The
street map is a simplified trace; crate counts, the truck size, the delivery limit and the
four-week rule are simplified for play. Sources are linked in the "For grown-ups" section.
