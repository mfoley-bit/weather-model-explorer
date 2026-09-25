# Weather Model Explorer — Static Image Version

This version intentionally abandons the custom map projection/data-grid approach.

## Architecture
The page embeds **pre-rendered PNG model graphics** from the College of DuPage NEXLAB numerical-model archive.

It supports:
- GFS
- ECMWF
- side-by-side Compare
- Northeast U.S., United States, and North America sectors
- forecast hours 0–192 in 6-hour increments
- Surface Temperature
- Total Precipitation Accumulation
- 850 mb Wind Speed
- Surface Air Pressure
- 500 mb Vorticity/Height

## Model-cycle matching
At startup, the app checks recent 6-hour model cycles and chooses the newest cycle where **both GFS and ECMWF have a Day 8 (F192) temperature image available**. That common cycle is then used for both panels.

This means Compare uses:
- the same initialization time
- the same forecast hour
- the same sector
- the same COD-rendered product type

## Source
Images are linked from:
`https://weather.cod.edu/wxdata/forecast/`

College of DuPage NEXLAB terms state that users may link to their images on their own website when credit is provided. This project credits COD in the UI and footer and only requests the currently selected image(s); it does not scrape or bulk-download their archive.

## Deployment
This is still a single static `index.html` and can be hosted on GitHub Pages or Netlify.
