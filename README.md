# ⚽ WC 2026 Event Data

Match-level event data for every FIFA World Cup 2026 fixture, collected from WhoScored with permission.

**Built by [Noah Bair](https://github.com/nlbair) · [Syracuse Football Analytics Club](https://twitter.com/SyracuseFAC)**

---

## Coverage

| Group | Match | Date | Status |
|-------|-------|------|--------|
| A | Mexico vs South Africa | 2026-06-11 | ✅ |
| A | South Korea vs Czechia | 2026-06-12 | ✅ |
| A | Mexico vs Czechia | 2026-06-15 | ⬜ |
| A | South Africa vs South Korea | 2026-06-15 | ⬜ |
| A | South Korea vs Mexico | 2026-06-19 | ⬜ |
| A | Czechia vs South Africa | 2026-06-19 | ⬜ |
| B | Canada vs Bosnia and Herzegovina | 2026-06-12 | ✅ |
| B | Qatar vs Switzerland | 2026-06-12 | ⬜ |
| B | Canada vs Switzerland | 2026-06-16 | ⬜ |
| B | Bosnia and Herzegovina vs Qatar | 2026-06-16 | ⬜ |
| B | Switzerland vs Bosnia and Herzegovina | 2026-06-20 | ⬜ |
| B | Qatar vs Canada | 2026-06-20 | ⬜ |
| C | Brazil vs Morocco | 2026-06-12 | ⬜ |
| C | Haiti vs Scotland | 2026-06-12 | ⬜ |
| C | Brazil vs Scotland | 2026-06-16 | ⬜ |
| C | Morocco vs Haiti | 2026-06-16 | ⬜ |
| C | Scotland vs Morocco | 2026-06-20 | ⬜ |
| C | Haiti vs Brazil | 2026-06-20 | ⬜ |
| D | USA vs Paraguay | 2026-06-13 | ⬜ |
| D | Australia vs Türkiye | 2026-06-13 | ⬜ |
| D | USA vs Türkiye | 2026-06-17 | ⬜ |
| D | Paraguay vs Australia | 2026-06-17 | ⬜ |
| D | Türkiye vs Paraguay | 2026-06-21 | ⬜ |
| D | Australia vs USA | 2026-06-21 | ⬜ |
| E | Germany vs Curaçao | 2026-06-13 | ⬜ |
| E | Ivory Coast vs Ecuador | 2026-06-13 | ⬜ |
| E | Germany vs Ecuador | 2026-06-17 | ⬜ |
| E | Curaçao vs Ivory Coast | 2026-06-17 | ⬜ |
| E | Ecuador vs Curaçao | 2026-06-21 | ⬜ |
| E | Ivory Coast vs Germany | 2026-06-21 | ⬜ |
| F | Netherlands vs Japan | 2026-06-13 | ⬜ |
| F | Sweden vs Tunisia | 2026-06-13 | ⬜ |
| F | Netherlands vs Tunisia | 2026-06-17 | ⬜ |
| F | Japan vs Sweden | 2026-06-17 | ⬜ |
| F | Tunisia vs Japan | 2026-06-21 | ⬜ |
| F | Sweden vs Netherlands | 2026-06-21 | ⬜ |
| G | Belgium vs Egypt | 2026-06-14 | ⬜ |
| G | Iran vs New Zealand | 2026-06-14 | ⬜ |
| G | Belgium vs New Zealand | 2026-06-18 | ⬜ |
| G | Egypt vs Iran | 2026-06-18 | ⬜ |
| G | Iran vs Belgium | 2026-06-22 | ⬜ |
| G | New Zealand vs Egypt | 2026-06-22 | ⬜ |
| H | Spain vs Cape Verde | 2026-06-14 | ⬜ |
| H | Saudi Arabia vs Uruguay | 2026-06-14 | ⬜ |
| H | Spain vs Uruguay | 2026-06-18 | ⬜ |
| H | Cape Verde vs Saudi Arabia | 2026-06-18 | ⬜ |
| H | Uruguay vs Cape Verde | 2026-06-22 | ⬜ |
| H | Saudi Arabia vs Spain | 2026-06-22 | ⬜ |
| I | France vs Senegal | 2026-06-14 | ⬜ |
| I | Iraq vs Norway | 2026-06-14 | ⬜ |
| I | France vs Norway | 2026-06-18 | ⬜ |
| I | Senegal vs Iraq | 2026-06-18 | ⬜ |
| I | Norway vs Senegal | 2026-06-22 | ⬜ |
| I | Iraq vs France | 2026-06-22 | ⬜ |
| J | Argentina vs Algeria | 2026-06-15 | ⬜ |
| J | Austria vs Jordan | 2026-06-15 | ⬜ |
| J | Argentina vs Jordan | 2026-06-19 | ⬜ |
| J | Algeria vs Austria | 2026-06-19 | ⬜ |
| J | Jordan vs Algeria | 2026-06-23 | ⬜ |
| J | Austria vs Argentina | 2026-06-23 | ⬜ |
| K | Portugal vs DR Congo | 2026-06-15 | ⬜ |
| K | Uzbekistan vs Colombia | 2026-06-15 | ⬜ |
| K | Portugal vs Colombia | 2026-06-19 | ⬜ |
| K | DR Congo vs Uzbekistan | 2026-06-19 | ⬜ |
| K | Colombia vs DR Congo | 2026-06-23 | ⬜ |
| K | Uzbekistan vs Portugal | 2026-06-23 | ⬜ |
| L | England vs Croatia | 2026-06-15 | ⬜ |
| L | Ghana vs Panama | 2026-06-15 | ⬜ |
| L | England vs Panama | 2026-06-19 | ⬜ |
| L | Croatia vs Ghana | 2026-06-19 | ⬜ |
| L | Panama vs Croatia | 2026-06-23 | ⬜ |
| L | Ghana vs England | 2026-06-23 | ⬜ |

*Round of 32, quarterfinals, semifinals, and final will be added as fixtures are confirmed.*

---

## File Naming

```
wc2026_{home_team}_vs_{away_team}_{date}_events.csv
```

Team names are lowercased with spaces replaced by underscores. Date is YYYY-MM-DD.

Example: `wc2026_canada_vs_bosnia_and_herzegovina_2026-06-12_events.csv`

---

## Repo Structure

```
wc2026-events/
├── data/
│   ├── raw/              # match event CSVs, one per match
│   └── metadata/
│       └── team_meta.csv # all 48 nations — names, colors, flag codes
├── docs/
│   └── data_dictionary.md
├── notebooks/
│   ├── postmatch_graphic.ipynb
│   └── player_spotlight.ipynb
├── model/
│   └── xg_sal313_lr.pkl
├── requirements.txt
├── CHANGELOG.md
└── .gitignore
```

---

## Data Source

Event data collected from [WhoScored](https://www.whoscored.com) with permission. Please credit WhoScored as the data source and Noah Bair / Syracuse FAC for collection and curation.
