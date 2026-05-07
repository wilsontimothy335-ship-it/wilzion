# 🔗 Expo URL & QR Code Guide

## Get Development URL

```bash
expo url
# Outputs: exp://192.168.x.x:19000
```

## Copy URL to Clipboard

```bash
expo url | pbcopy          # macOS
expo url | xclip -selection clipboard  # Linux
```

## Open URL Directly

```bash
expo send --url "$(expo url)"
```

## View QR Code from Terminal

```bash
# Start development server
npm start

# Shows QR code in terminal automatically
# You'll see:
# ┌────────────────────────────────────────────┐
# │  QR Code appears here                      │
# ���────────────────────────────────────────────┘
```

## Quick Access Commands

| Command | Purpose |
|---------|---------|
| `npm start` | Start dev server & show QR |
| `expo url` | Get development URL |
| `expo send` | Send link to phone |
| `expo url \| pbcopy` | Copy URL to clipboard |
| `expo qr` | Show QR code in terminal |

## Connect from Expo Go App

1. **Start server:** `npm start`
2. **Open Expo Go** on your phone
3. **Tap "Scan QR Code"**
4. **Point camera** at terminal QR code
5. **Wait 5-10 seconds** for app to load

## Troubleshooting

### URL not showing?
```bash
npm start -- --clear
expo url
```

### Firewall blocking?
```bash
# Use tunnel mode instead
expo start --tunnel
```

### Want to use USB instead of WiFi?
```bash
# Android USB debugging
adb devices
expo start --localhost
```

## Environment Variables

Create `.env` file:
```
EXPO_PUBLIC_API_URL=exp://192.168.x.x:19000
EXPO_PUBLIC_ENV=development
```

Access in code:
```javascript
import { Env } from '@env';
console.log(Env.EXPO_PUBLIC_API_URL);
```

---

**Pro Tip:** Use `expo url` in scripts for CI/CD automation! 🚀
