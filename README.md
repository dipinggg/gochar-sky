# Gochar Sky

A live Vedic *gochar* (transit) sky that runs in your browser. It shows the real stars over any city and lays the sidereal zodiac, your house numbers, your birth planets and today's planets on top of them.

**Open it:** https://dipinggg.github.io/gochar-sky/

## What it does

- **Planets that look the part.** Soft painted versions of the real bodies: Jupiter's bands and Great Red Spot, Saturn's rings at their real tilt, Mars's polar cap, the Moon's maria. Each is lit from the Sun's real direction, so the Moon, Venus, Mercury and Mars show their true phases. Each glow follows the planet's live brightness (apparent magnitude) and breathes slowly, because planets shine steadily rather than twinkling.
- **Real sky, live.** Over 5,000 stars, the Milky Way and the constellations, turning in real time over the place you choose.
- **Vedic overlay.** Sidereal signs (Lahiri ayanamsa) as soft bands with whole-sign house numbers from your Lagna, plus optional nakshatras and their junction stars.
- **Your chart.** Enter a name, birth date, birth time and birth place (any town worldwide). Your birth planets appear as faint discs fixed among the stars, and today's planets appear in full colour. A close contact (a planet within 3° of a birth planet) pulses.
- **House view.** A fixed frame shows three houses at a time, level and upright, with arrows to move through all twelve. A card above it explains what each house signifies and what is happening in it now. Pinch out (or double-tap, or press +) to zoom into the centre house, where every degree and the nakshatras inside it are marked; pinch in to go back to three houses.
- **Time travel.** Jump to any date and time and watch the sky glide there, or play time forward and backward with star trails.

## Privacy

Birth details are saved only in your own browser (`localStorage`). They are never uploaded. When you search for a place, the place name is sent to the [Open-Meteo geocoding API](https://open-meteo.com/en/docs/geocoding-api) to find its coordinates and time zone. If that lookup is unavailable, a built-in list of cities is used instead.

## How it works

Everything is in `index.html` plus the planet library beside it, with no build step.

- Planet positions: [Astronomy Engine](https://github.com/cosinekitty/astronomy) (MIT), included as `astronomy.browser.min.js` so the site doesn't depend on an outside CDN.
- Sidereal longitudes use the Lahiri ayanamsa. Rahu and Ketu are the mean lunar nodes. Houses are whole signs from the Lagna.
- Birth times are converted to UTC with your browser's time zone database, so historical offsets and daylight saving are handled (for example, India's +6:30 wartime clock in 1942–45).
- Stars, constellation lines and the Milky Way outline come from [d3-celestial](https://github.com/ofrohn/d3-celestial) (BSD 3-Clause, Hipparcos catalogue). See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
- Place search: [Open-Meteo](https://open-meteo.com/) geocoding (data from GeoNames, CC BY 4.0).

Positions are accurate to about a tenth of a degree, which is plenty for sign, house and nakshatra work. The short house readings are general traditional meanings, not a full astrological interpretation.

## Running locally

Open `index.html` in any modern browser, or serve the folder:

```sh
python3 -m http.server 8000
```
