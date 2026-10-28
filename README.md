# M Booking — frontend skeleton

Static frontend only. No build step: open `index.html`. Backend is wired by the backend team.

- `index.html` — homepage v2 (styles and scripts are inline)
- `index-v1.html` — previous homepage design, kept for reference
- `brand/m-booking-logo.svg` — logo lockup (wordmark is live Noto Sans text; outline before print)

## Search forms

Each tab is a plain `<form method="get">`. Submitting navigates to the action with the fields as query params. Swap `action` or intercept `submit` to call your API.

| Tab | Action | Fields |
|---|---|---|
| Flights | `/search/flights` | `trip` (round-trip / one-way / multi-city), `from`, `to`, `depart`, `return`, `pax` |
| Hotels | `/search/hotels` | `type` (hotels / boutique / apartments / villas / hostels), `q`, `checkin`, `checkout`, `guests` |
| Resorts | `/search/resorts` | `style` (any / beach / mountain / wellness / all-inclusive), `q`, `checkin`, `checkout`, `guests` |
| Trains | `/search/trains` | `trip` (one-way / return), `from`, `to`, `date`, `pax` |
| Attractions | `/search/attractions` | `kind` (all / tours / theme-parks / museums / shows / day-trips), `q`, `date`, `guests` |
| Packages | `/search/packages` | `nights`, `from`, `to`, `month` (YYYY-MM), `pax` |

Dates are `YYYY-MM-DD` (native date inputs). `pax` / `guests` currently send the option label text; replace with structured values or a picker once the API shape is fixed.

## Other forms and hooks

| Form | Action | Fields |
|---|---|---|
| Contact | `POST /contact` | `name`, `email` |
| Newsletter (footer) | `POST /newsletter` | `email` |

- "Most viewed" cards and filter chips, "Top destinations" rows and journal posts are static placeholders; render from the API.
- Heart buttons (`.fav`) only toggle `aria-pressed` locally; persist to the user's saved list.
- The brand-film play button (`.play`) has no video yet.

## Placeholders to replace

- Unsplash photos (hotlinked) → licensed imagery
- Deal prices in the hero, FAQ answers, "40+ countries" claim, licence number in footer
- All `href="#"` links (sign in, destinations, contact, legal pages)
