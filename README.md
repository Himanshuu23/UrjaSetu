# UrjaSetu

A sustainability mobile app for image-based waste guidance, nearby collection vendors, Green Points, and solar and electricity calculators.

---

## Architecture

```text
┌─────────────────────────────────────────────────────────────┐
│                        Mobile app                           │
│  Expo • React Native • Expo Router                          │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌────────────────────────────────────────────────────────────────────┐
│                     REST API (Express, Kafka)                      │
│  Users • Vendors • Waste image • Solar • Electricity               │
└────────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                     Data and helpers                        │
│  MongoDB • Imagga image tags • geocoding                    │
└─────────────────────────────────────────────────────────────┘
```

## Features

### Home

<img src="public/homepage.png" width="280" alt="Home" />

### Waste photo upload

<img src="public/recycle.png" width="280" alt="Waste photo upload" />

### Nearest vendor

<img src="public/map.png" width="280" alt="Nearest vendor" />

### Green Points marketplace

<img src="public/marketplace.png" width="280" alt="Green Points marketplace" />

### Electricity calculator

<img src="public/calculator.png" width="280" alt="Electricity calculator" />