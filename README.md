# Malaysian Transportation Network - 2025

An interactive visualization of West Malaysia's transportation network displaying hourly ridership patterns across four major transportation services.
![Screenshot 2025-12-07 031239](https://github.com/user-attachments/assets/cb1ad755-073e-4f43-8b12-e092f4cb2f7d)

## Features

### Interactive Map
- **West Malaysia Boundary**: Contoured map showing regional outline with gradient opacity
- **Service Filtering**: Toggle between ALL services or specific transportation networks
  - Shuttle Tebrau (JB ↔ Singapore)
  - ETS Rail (Long-distance rail)
  - Komuter (Urban rail)
  - Intercity Bus
- **Zoom-Responsive**: Line thickness and contour visibility scale with zoom level

### Route Visualization
- **Curved Arc Routes**: Parabolic paths between stations with varying thickness based on ridership
- **Multi-Service Routes**: Longitudinal rainbow stripes for routes operated by multiple services
- **Frequency Indicators**: Route opacity (0.4-0.9) and thickness responsive to ridership volume

### Station Markers
- **Dynamic Sizing**: Station circle size represents total ridership
- **Click-to-Reveal**: Click any station to see:
  - Station name and state
  - Total ridership figures
  - Connected routes with destinations
  - Frequency meter (gradient bar) for each route
  - Scroll-enabled route list

### Hourly Analytics
- **Route Tooltips**: Hover over routes to display:
  - Origin → Destination
  - Total ridership count
  - Service breakdown (individual operator counts)
  - 24-hour hourly ridership histogram (0:00-23:00)
- **TOP 5 Routes**: Dashboard shows busiest routes with full rider counts

### Statistics Dashboard
- **Overall Stats**: Displays routes count, total riders, average riders per route, top route
- **Service-Specific Views**: Stats update when filtering by service
- **Dynamic Zoom**: Service filter buttons automatically zoom to network bounds

## Data Sources

CSV files aggregated by origin-destination pairs with hourly breakdown:
- `shuttle_tebrau_2025.csv` - Shuttle Tebrau ridership data
- `ets_2025.csv` - ETS Rail ridership data
- `komuter_2025.csv` - Komuter Rail ridership data
- `intercity_2025.csv` - Intercity Bus ridership data
- `my.json` - GeoJSON boundaries for West Malaysia


## File Structure

```
myopendata/
├── index.html                    # Main application
├── my.json                       # GeoJSON boundaries
├── README.md                     # This file
└── data/
    ├── shuttle_tebrau_2025.csv
    ├── ets_2025.csv
    ├── komuter_2025.csv
    ├── intercity_2025.csv
    ├── od_hourly_shuttle_tebrau.csv
    ├── od_hourly_ets.csv
    ├── od_hourly_komuter.csv
    └── od_hourly_intercity.csv
```


## Data Notes

- Ridership counts are aggregated by hour across all dates in 2025
- Routes sorted by total ridership (busiest first)
- Multi-service routes render as parallel colored stripes
- Frequency meters normalize per-station (relative to busiest route from that station)
- Hourly data spans 0:00-23:59 (24-hour format)
