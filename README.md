# NumberVerifyAPI — Phone Number Lookup & Validation API (USA, Canada & Worldwide)

Fast, affordable phone number intelligence for developers. Validate any number, detect the carrier and line type, and get clean E.164 formatting from one simple API request.

**100 free credits on sign-up · No rate limits · Pay only for successful lookups**

[Website](https://numberverifyapi.com) · [Docs](https://numberverifyapi.com/docs) · [Pricing](https://numberverifyapi.com/pricing) · [Status](https://numberverifyapi.com/status)

---

## Why NumberVerifyAPI?

- **One endpoint for the whole world** — USA, Canada and every other country.
- **Carrier + line type data** — know if a number is mobile, landline, VoIP or toll-free.
- **Free misses** — unknown or invalid numbers are never charged.
- **No subscriptions** — buy credits, use them whenever you want.
- **Developer-first** — JSON responses, API key auth, clean errors, simple docs.

Perfect for signup validation, CRM cleanup, fraud screening, lead verification, SMS routing and data enrichment.

---

## Coverage

| Region | Coverage |
|---|---|
| 🇺🇸 United States | All US area codes and prefixes, carrier + line type, toll-free detection |
| 🇨🇦 Canada | Canadian area codes detected automatically (`country: CA`), carrier + line type |
| 🌍 Worldwide | 240+ countries and territories, validation, formatting and carrier where available |

---

## Features

- Phone number validation (US, Canada and worldwide)
- Carrier lookup by phone number
- Line type detection: `MOBILE`, `FIXED_LINE`, `FIXED_LINE_OR_MOBILE`, `TOLL_FREE`, `VOIP`, `GOVERNMENTAL`
- E.164, national and international formatting
- US & Canada (Dedicated)
- Toll-free and reserved detection
- Auto Country detection (returns ISO-2 country code)
- One lookup endpoint for every country
- JSON responses with clear error codes
- API key via query string, `X-API-Key` header or `Authorization: Bearer`
- Free lookups for unknown/invalid numbers
- No rate limits, no monthly quota
- 100 free credits when you sign up

---

## Base URL

```
https://numberverifyapi.com/v1
```

Get your free API key: **https://numberverifyapi.com/register**

---

## Quick start

```bash
curl "https://numberverifyapi.com/v1/lookup?number=2012046698&key=YOUR_API_KEY"
```

```bash
curl "https://numberverifyapi.com/v1/lookup?number=%2B442079460000&key=YOUR_API_KEY"
```

```bash
curl "https://numberverifyapi.com/v1/lookup?number=0798765432&country_code=CH&key=YOUR_API_KEY"
```

Or send the key as a header:

```bash
curl -H "X-API-Key: YOUR_API_KEY" \
  "https://numberverifyapi.com/v1/lookup?number=2012046698"
```

> In a URL query string `+` means a space, so encode an E.164 `+` as `%2B`.

---

## API endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` / `POST` | `/v1/lookup` | Validate a number and return carrier, line type, country and formats |
| `GET` / `POST` | `/v1/account` | Check your credit balance and usage |

### Parameters — `/v1/lookup`

| Parameter | Required | Description |
|---|---|---|
| `number` | Yes | Phone number in any format (international, national or E.164) |
| `key` | Yes* | Your API key (*or send it as a header) |

### Authentication

Pass your key in any of these ways:

```
?key=YOUR_API_KEY
X-API-Key: YOUR_API_KEY
Authorization: Bearer YOUR_API_KEY
```

---

## Example response

US number:

```json
{
  "number": "2012046698",
  "formatted": "(201) 204-6698",
  "carrier": "OMNIPOINT COMMUNICATIONS, INC.",
  "line_type": "MOBILE",
  "country": "US",
  "valid": true,
  "e164": "+12012046698"
}
```

International number:

```json
{
  "number": "41798765432",
  "formatted": "+41 79 876 54 32",
  "national": "079 876 54 32",
  "international": "+41 79 876 54 32",
  "e164": "+41798765432",
  "country": "CH",
  "country_code": 41,
  "carrier": "Swisscom",
  "line_type": "MOBILE",
  "valid": true
}
```

---

## Errors

Errors are returned as JSON:

```json
{
  "error": {
    "code": "invalid_number",
    "message": "The phone number is not valid."
  }
}
```

| Status | Meaning |
|---|---|
| `400` | Bad input / invalid number / bad country |
| `401` | Missing or invalid API key |
| `402` | Insufficient credits |
| `403` | Account suspended |
| `503` | API disabled |

---

## Pricing

- **100 free credits** when you create an account
- **No rate limits**
- **Pay as you go** — credits never expire
- **Free misses** — unknown or invalid numbers are not charged
- No subscriptions, no hidden fees

See plans: **https://numberverifyapi.com/pricing**

---

## Common use cases

- Signup and checkout phone validation
- CRM and contact database cleanup
- Lead verification and enrichment
- Fraud and risk screening
- SMS and call routing by line type
- Detecting VoIP, landline vs mobile
- Normalizing numbers to E.164
- Bulk phone number validation

---

## Contact

- Website: https://numberverifyapi.com
- Docs: https://numberverifyapi.com/docs
- Telegram: https://t.me/thepythoncode97
- Email: support@numberverifyapi.com

---

⭐ If you find this project useful, please star the repository — it helps others discover it.
