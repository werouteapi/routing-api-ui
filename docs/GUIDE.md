# Developer UI - Usage Guide

## Overview

The Routing API UI is an interactive web interface for testing and integrating with the Routing API.

## Features

### 1. Payment Routing Simulator

Test the routing algorithm with different payment scenarios:

- **Amount**: Enter payment amount in cents
- **Currency**: Choose from 150+ currencies
- **Destination**: Select destination country
- **Payment Method**: Choose card, bank transfer, or digital wallet

Click **"Route Payment"** to see the recommended provider and alternatives.

### 2. Compliance Check Tool

Verify sanctions and compliance status:

- Enter customer name
- Select country
- Check against OFAC, EU, UN lists
- View risk assessment

### 3. Transaction Builder

Build complete payment requests:

- Set all parameters
- Copy as cURL command
- Copy as JavaScript/Python code
- Export as Postman collection

### 4. Response Inspector

View detailed API responses:

- See raw JSON
- View formatted response
- Copy entire response
- Export for debugging

### 5. Webhook Tester

Test webhook configuration:

- Set webhook URL
- Send test events
- View delivery attempts
- Verify signature

## Getting Started

### 1. Sign Up

Visit https://dashboard.webundle.org and create an account.

### 2. Get API Key

1. Go to **Settings → API Keys**
2. Click **Create New Key**
3. Copy your test key (starts with `sk_test_`)

### 3. Add API Key to UI

1. Open the Developer UI
2. Click **Settings** (gear icon)
3. Paste your API key
4. Click **Save**

### 4. Start Testing

1. Go to **Payment Routing** tab
2. Enter test payment details
3. Click **Route Payment**
4. See the recommendation

## Use Cases

### Test Payment Routing

```
Amount: 10000 ($100.00)
Currency: USD
Destination: US
Method: card
→ Result: stripe (recommended), $2.50 fee
```

### Check Customer Compliance

```
Name: John Doe
Country: US
→ Result: Not sanctioned, 99% confidence
```

### Generate Code Snippet

1. Build a request in **Transaction Builder**
2. Select your language (JavaScript, Python, Go, etc)
3. Click **Copy Code**
4. Paste into your project

### Test Webhooks

1. Use **Webhook Tester**
2. Enter your webhook URL
3. Click **Send Test Event**
4. Check your server logs

## Tips & Tricks

### Tip 1: Use Sandbox First

Always test with `sk_test_*` keys before going live.

### Tip 2: Test Multiple Scenarios

Try different countries, amounts, and payment methods to understand routing.

### Tip 3: Monitor Fees

Check estimated fees for different providers.

### Tip 4: Copy Code Snippets

Use the code generator to quickly integrate into your app.

### Tip 5: Save Requests

Bookmark complex requests for reuse.

## Keyboard Shortcuts

- `Cmd/Ctrl + K`: Quick search
- `Cmd/Ctrl + /`: Help
- `Cmd/Ctrl + S`: Save request
- `Cmd/Ctrl + L`: Copy link

## Export Options

### Export as cURL

```bash
curl -X POST https://api.webundle.org/payments/route \
  -H "Authorization: Bearer sk_test_abc123" \
  -d '{...}'
```

### Export as Code

JavaScript, Python, Go, Java, Ruby, PHP, etc.

### Export as Postman

Import directly into Postman for testing.

### Export as OpenAPI

Use in your API documentation.

## Troubleshooting

### "Invalid API Key"

Make sure you're using a test key starting with `sk_test_`.

### "Rate Limited"

You've exceeded rate limits. Wait a few minutes and retry.

### "Sandbox Mode Only"

Test keys (`sk_test_*`) only work with sandbox API.

### "Webhook Not Received"

1. Check webhook URL is publicly accessible
2. Verify firewall allows inbound traffic
3. Check server logs for errors
4. Use test webhook to verify

## Support

- Email: support@webundle.org
- Docs: https://docs.webundle.org
- Issues: https://github.com/werouteapi/routing-api-ui/issues

## Next Steps

1. [Read API Reference](https://docs.webundle.org/api-reference)
2. [Download SDK](https://github.com/werouteapi)
3. [Import Postman Collection](https://github.com/werouteapi/routing-api-postman)
4. [View Examples](https://github.com/werouteapi/routing-api-examples)
