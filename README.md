# ⚽ WC 2026 Event Data

Match-level event data for every FIFA World Cup 2026 fixture

**Built by [Noah Bair](https://www.linkedin.com/in/noah-bair/)**

---

## Coverage

| Group | Match | Date | Status |
|-------|-------|------|--------|
| A | Mexico vs South Africa | Jun 11 | ✅ |
| A | South Korea vs Czechia | Jun 11 | ✅ |
| B | Canada vs Bosnia and Herzegovina | Jun 12 | ✅ |
| B | Qatar vs Switzerland | Jun 13 | ✅ |
| C | Brazil vs Morocco | Jun 13 | ✅ |
| D | USA vs Paraguay | Jun 13 | ✅ |
| C | Haiti vs Scotland | Jun 14 | ✅ |
| D | Australia vs Türkiye | Jun 14 | ✅ |
| E | Germany vs Curaçao | Jun 14 | ✅ |
| F | Netherlands vs Japan | Jun 14 | ✅ |
| E | Ivory Coast vs Ecuador | Jun 15 | ✅ |
| G | Belgium vs Egypt | Jun 15 | ✅ |
| H | Spain vs Cape Verde | Jun 15 | ✅ |
| H | Saudi Arabia vs Uruguay | Jun 15 | ✅ |
| F | Sweden vs Tunisia | Jun 15 | ✅ |
| G | Iran vs New Zealand | Jun 16 | ✅ |
| I | France vs Senegal | Jun 16 | ✅ |
| I | Iraq vs Norway | Jun 16 | ✅ |
| J | Argentina vs Algeria | Jun 16 | ✅ |
| J | Austria vs Jordan | Jun 17 | ✅ |
| K | Portugal vs DR Congo | Jun 17 | ✅ |
| L | England vs Croatia | Jun 17 | ✅ |
| L | Ghana vs Panama | Jun 17 | ✅ |
| K | Uzbekistan vs Colombia | Jun 17 | ✅ |
| A | Czechia vs South Africa | Jun 18 | ✅ |
| B | Switzerland vs Bosnia and Herzegovina | Jun 18 | ✅ |
| B | Canada vs Qatar | Jun 18 | ✅ |
| A | Mexico vs South Korea | Jun 18 | ✅ |
| D | USA vs Australia | Jun 19 | ✅ |
| C | Scotland vs Morocco | Jun 19 | ✅ |
| C | Brazil vs Haiti | Jun 19 | ✅ |
| D | Türkiye vs Paraguay | Jun 19 | ✅ |
| F | Netherlands vs Sweden | Jun 20 | ✅ |
| E | Germany vs Ivory Coast | Jun 20 | ✅ |
| E | Ecuador vs Curaçao | Jun 20 | ✅ |
| F | Tunisia vs Japan | Jun 21 | ✅ |
| H | Spain vs Saudi Arabia | Jun 21 | ✅ |
| G | Belgium vs Iran | Jun 21 | ✅ |
| H | Uruguay vs Cape Verde | Jun 21 | ✅ |
| G | New Zealand vs Egypt | Jun 21 | ✅ |
| J | Argentina vs Austria | Jun 22 | ✅ |
| I | France vs Iraq | Jun 22 | ✅ |
| I | Norway vs Senegal | Jun 22 | ✅ |
| J | Jordan vs Algeria | Jun 22 | ✅ |
| K | Portugal vs Uzbekistan | Jun 23 | ✅ |
| L | England vs Ghana | Jun 23 | ✅ |
| L | Panama vs Croatia | Jun 23 | ✅ |
| K | Colombia vs DR Congo | Jun 23 | ✅ |
| B | Switzerland vs Canada | Jun 24 | ✅ |
| B | Bosnia and Herzegovina vs Qatar | Jun 24 | ✅ |
| C | Scotland vs Brazil | Jun 24 | ✅ |
| C | Morocco vs Haiti | Jun 24 | ✅ |
| A | Czechia vs Mexico | Jun 24 | ✅ |
| A | South Africa vs South Korea | Jun 24 | ✅ |
| E | Curaçao vs Ivory Coast | Jun 25 | ✅ |
| E | Ecuador vs Germany | Jun 25 | ✅ |
| F | Japan vs Sweden | Jun 25 | ✅ |
| F | Tunisia vs Netherlands | Jun 25 | ✅ |
| D | Türkiye vs USA | Jun 25 | ✅ |
| D | Paraguay vs Australia | Jun 25 | ✅ |
| I | Norway vs France | Jun 26 | ✅ |
| I | Senegal vs Iraq | Jun 26 | ✅ |
| H | Cape Verde vs Saudi Arabia | Jun 26 | ✅ |
| H | Uruguay vs Spain | Jun 26 | ✅ |
| G | Egypt vs Iran | Jun 26 | ✅ |
| G | New Zealand vs Belgium | Jun 26 | ✅ |
| L | Panama vs England | Jun 27 | ✅ |
| L | Croatia vs Ghana | Jun 27 | ✅ |
| K | Colombia vs Portugal | Jun 27 | ✅ |
| K | DR Congo vs Uzbekistan | Jun 27 | ✅ |
| J | Algeria vs Austria | Jun 27 | ✅ |
| J | Jordan vs Argentina | Jun 27 | ✅ |

Round of 32 data processing IN PROGRESS

Colombia vs Ghana | Jul 3 | ✅ |

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

Please credit WhoScored as the data source and Noah Bair for collection and curation.
