# UrjaSetu

A sustainability mobile app for image-based waste guidance, nearby collection vendors, Green Points, and solar and electricity calculators.

```text
Expo app → Express REST API → MongoDB
```

The phone app already calls the hosted API, so scanning the Expo QR is enough to try it.

---

## Architecture

```text
┌─────────────────────────────────────────────────────────────┐
│                        Mobile app                           │
│  Expo • React Native • Expo Router                          │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                     REST API (Express)                      │
│  Users • Vendors • Waste image • Solar • Electricity        │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                     Data and helpers                        │
│  MongoDB • Imagga image tags • geocoding                    │
└─────────────────────────────────────────────────────────────┘
```

## Features

- User and vendor sign up and login
- Waste photo upload and disposal suggestion
- Nearest vendor on the map
- Green Points marketplace
- Solar rooftop calculator
- Electricity usage calculator

## Layout

| Folder | What it is |
|----------|----------|
| client | Expo app |
| server | Express API used on Vercel |

## API

Base URL used by the app: `https://backend-amber-nine-53.vercel.app`

| Method | Path | Purpose |
|----------|----------|----------|
| POST | /api/user/register | Create a user |
| POST | /api/user/login | Log in |
| GET | /api/user/:email | Profile and Green Points |
| POST | /api/user/increase | Add Green Points |
| POST | /api/user/deduct | Spend Green Points |
| POST | /api/vendor/register | Create a vendor |
| POST | /api/vendor/login | Vendor login |
| GET | /api/vendor/nearest-vendor | Closest vendor by coordinates |
| POST | /api/analyze/suggestion | Waste image suggestion |
| POST | /api/api/solarPotential | Solar estimate |
| POST | /api/api/electricityUsage | Electricity estimate |

## Install on a phone

Install [Expo Go](https://expo.dev/go) on the phone. The computer and the phone need the same Wi-Fi.

```bash
cd client
npm install
npx expo start
```

The terminal prints a QR code. Scan it with Expo Go on Android, or the Camera app on iOS. That opens this project in Expo Go. The QR is only valid while that terminal is running.

To show that QR on this page, screenshot it, save the image as `client/assets/images/expo-qr.png`, and add this line under this section:

```md
![Scan to open UrjaSetu in Expo Go](client/assets/images/expo-qr.png)
```

## Run the API locally

The app does not need this step. It already uses the hosted API.

```bash
cd server
npm install
```

Copy `.env.example` to `.env` and set `MONGO_URL`. Image analysis also needs `IMAGGA_API_KEY` and `IMAGGA_API_SECRET`.

```bash
npm start
```

The API listens on port 3000 unless `PORT` is set.
