# Options: Weather API
- Status: chosen (ADR-0002)
- Related FR: FR-8

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes / source |
|---|---|---|---|---|---|---|---|
| Open-Meteo | 4 | 4 | 5 | 5 | 4 | 22 | Free for dev; commercial ~$29/mo Standard (verify) ([pricing](https://open-meteo.com/en/pricing)) |
| OpenWeather | 4 | 4 | 3 | 5 | 4 | 20 | |
| Tomorrow.io | 4 | 3 | 2 | 4 | 4 | 17 | |
| PMD | 3 | 5 | 5 | 2 | 2 | 17 | No easy API |

## Recommendation
Open-Meteo (commercial plan at launch). Free tier is non-commercial only.
