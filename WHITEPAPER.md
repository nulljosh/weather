# Weather Technical Whitepaper

**v1.0.0** | September 2026

A weather page. Type a city or share your location, read the forecast.
Live at [weather.heyitsmejosh.com](https://weather.heyitsmejosh.com).

## The mechanic

Two requests to Open-Meteo, straight from the browser. The first turns a
city name into coordinates. The second takes those coordinates and returns
current conditions plus a seven-day daily forecast, in the local timezone.
Open-Meteo needs no API key, so there is no server in between.

WMO weather codes come back as integers. A small table maps them to plain
words. Temperatures arrive in Celsius and are converted on render if the
visitor picked Fahrenheit.

The last place and the unit are kept in localStorage, so a return visit
loads without asking. First visit with nothing stored asks for geolocation.

## Design

One column. The current temperature is the biggest thing on the page.
Dark by default, light on `prefers-color-scheme: light`. No icons, no
imagery; the words do the work.

## Security / Privacy

No backend, no accounts, no analytics. Coordinates go to Open-Meteo and
nowhere else. Nothing is stored beyond the browser's own localStorage.

## License

MIT 2026, Joshua Trommel
