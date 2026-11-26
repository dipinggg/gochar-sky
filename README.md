# Gochar Sky

A live Vedic *gochar* (transit) sky that runs in your browser. It shows the real stars over any city and lays the sidereal zodiac, your house numbers, your birth planets and today's planets on top of them.

**Open it:** https://dipinggg.github.io/gochar-sky/

## What it does

- **Planets that glow.** The Sun, Moon, Mercury, Venus, Rahu and Ketu are soft painted discs (the Moon's maria, Mercury's craters, Venus's clouds), lit from the Sun's real direction so the Moon, Venus and Mercury show their true phases; Mars, Jupiter and Saturn keep simple colour discs. Every body pulses with a slow glow, and brighter planets (by their live apparent magnitude) glow bigger.
- **Real sky, live.** Over 5,000 stars, the Milky Way and the constellations, turning in real time over the place you choose.
- **Vedic overlay.** Sidereal signs (Lahiri ayanamsa) as soft bands with whole-sign house numbers from your Lagna, plus optional nakshatras and their junction stars.
- **Your chart.** Enter a name, birth date, birth time and birth place (any town worldwide). Your birth planets appear as faint discs fixed among the stars, and today's planets appear in full colour. A close contact (a planet within 3° of a birth planet) pulses.
- **House view.** A fixed frame shows three houses at a time, level and upright, with arrows to move through all twelve. A card above it gives a reading of each house built from classical rules: transits counted from the birth Moon with vedha (Phaladeepika), Ashtakavarga bindus and kakshya (Brihat Parashara Hora Shastra), dignity and planetary friendship, combustion and planetary war, the nakshatra's lord, deity and nature, Tara bala from the birth star, yogas formed by planets travelling together, aspects, the house lord's condition and the running Vimshottari dasha, summed up in a plain-language verdict. Above the house details, a "This chart right now" section gives the broad picture for the date: the running dasha and the houses its lords rule, how Saturn, Jupiter, Rahu and Ketu sit from the Moon (including Sade Sati), the strongest and most pressured houses, and the next big sign changes. Pinch out (or double-tap, or press +) to zoom into the centre house, where every degree and the nakshatras inside it are marked; on a phone, one more pinch gives a close-up where the house fills the screen. Pinch in to step back out.
- **Time travel.** Jump to any date and time and watch the sky glide there, or play time forward and backward with star trails.

## Keyboard

Like a game: hold **W A S D** (or the arrow keys) to look around and **Q / E** to zoom, with **Shift** to move faster. **1–9** jump to the Sun, Moon, Mars, Mercury, Jupiter, Venus, Saturn, Rahu and Ketu. **H** opens House view, where **A / D** step through the houses and **W / S** zoom into one house. **Space** pauses time, **[ ]** step a day (**Shift** for a year), **N** returns to now, **B** jumps to the birth moment, and **T** hides or shows the time bar. **F** opens Filters, **C** your chart, and **?** shows the full list.

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
