# CityScape Email Confirmation

Pagina de confirmare email pentru CityScape - design verde, responsive, și optimizată pentru Vercel.

## Features

✅ Design verde CityScape (brand colors: #10B981, #059669)
✅ Responsive design (mobile-first)
✅ Loading states cu animații
✅ Success/Error screens
✅ Direct backend integration
✅ Deep linking la app (cityscape://login)
✅ Fast deployment pe Vercel

## Deployment

### 1. Clone și Deploy pe Vercel

```bash
vercel --prod
```

### 2. Configurează în Supabase Email Template

Mergi la Supabase Dashboard → Authentication → Email Templates → Confirm signup

Schimbă URL-ul din:
```
{{ .ConfirmationURL }}
```

La:
```
https://cityscape-email-confirm.vercel.app?token={{ .TokenHash }}&type=email
```

(Înlocuiește cu domeniul tău din Vercel)

### 3. Set Backend URL (opțional)

Dacă backend-ul nu e la default URL, setează în Vercel Environment:

```
BACKEND_URL=https://your-backend.com
```

## Architecture

```
User Register
    ↓
Email sent (Supabase)
    ↓
User clicks link → Vercel page (/index.html)
    ↓
Page calls backend (/api/auth/confirm-email)
    ↓
Backend verifies token with Supabase
    ↓
Show Success/Error
    ↓
User opens CityScape app & logs in
```

## Colors

- Primary Green: `#10B981`
- Dark Green: `#059669`
- Light Green BG: `#f0fdf4`
- Text: `#333` (dark gray)

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Development

```bash
# Local testing
python -m http.server 8000

# Visit http://localhost:8000?token=test-token&type=email
```

## License

MIT © CityScape 2026
