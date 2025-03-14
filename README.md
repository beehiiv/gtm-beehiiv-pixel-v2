# beehiiv Pixel V2 for Google Tag Manager

## Overview
The beehiiv Pixel V2 template is a custom Google Tag Manager template that enables easy integration with beehiiv's Ad Network pixel tracking. This template allows you to track various conversion events and user actions on your website.

## Prerequisites
- Google Tag Manager account
- beehiiv advertiser account

## Installation

1. Open your Google Tag Manager container
2. Go to Templates > Tag Templates
3. Click "New"
4. Click the three dots menu and select "Import"
5. Upload the template file
6. Save the template

Or find the beehiiv Pixel V2 template in the Template Gallery and add to your container.

## Create Tag

1. Open your Google Tag Manager container
2. Go to Tags
3. Click "New"
4. Click on the Pencil icon in the Tag Configuration panel
5. Select the beehiiv Pixel V2 tag under Custom
6. Enter your Advertiser ID
7. Select an Event and enter additional parameters as defined below
8. Add a tag trigger to make this tag fire.
9. Save the template

## Required Value

- **Advertiser ID**: This is your unique advertiser id from the beehiiv Ad Network. You will find this value on the Ad Network Portal.

## Supported Events

| Event Type | Description | Required Parameters | Optional Parameters |
|------------|-------------|-------------------|-------------------|
| pageview | page view event | - | - |
| conversion | Custom conversion event | currency, value_cents | num_items, predicted_ltv_cents |
| lead | Sign up completion | currency, value_cents | - |
| complete_registration | Registration form completion | currency, value_cents | - |
| purchase | Purchase or checkout completion | currency, value_cents | num_items |
| initiate_checkout | Checkout flow initiation | currency, value_cents | num_items |
| start_trial | Free trial start | currency, value_cents | predicted_ltv_cents |
| subscribe | Subscription start | currency, value_cents | - |

## Parameters

### Event Settings
- **Event Name**: Select the type of event you want to track

### Monetary Values
- **Currency**: Three-letter currency code (e.g., "usd", "eur")
- **Value**: The value in cents (e.g., $1.99 = 199)

### Additional Parameters
- **Number of Items**: Available for purchase, initiate_checkout, and conversion events
- **Predicted LTV**: Available for start_trial and conversion events (in cents)

### Content Parameters (Optional)
- Content Category
- Content IDs
- Content Name
- Content Type
- Search String
- Status

## Usage Examples

### Track a Purchase
```javascript
{
  "eventName": "purchase",
  "currency": "usd",
  "value_cents": 1999,
  "num_items": 2
}
```

### Track a Trial Start
```javascript
{
  "eventName": "start_trial",
  "currency": "usd",
  "value_cents": 0,
  "predicted_ltv_cents": 29900
}
```

### Track a Lead
```javascript
{
  "eventName": "lead",
  "currency": "usd",
  "value_cents": 1000
}
```

## Troubleshooting

1. **Advertiser ID Not Provided**
   - Ensure you have entered your Advertiser ID

2. **Invalid Event Name**
   - Check that you've selected a valid event name from the dropdown
   - Verify the event name matches the supported events list

3. **Missing Required Parameters**
   - Ensure all required parameters for your selected event are filled out
   - Check that monetary values are provided in cents

## Data Validation

The template includes built-in validation for:
- Required event name selection
- Valid currency code format (3 letters)
- Numeric values for monetary amounts and quantities
- Required parameters based on event type

## Support
For implementation support, please contact beehiiv support or consult the [beehiiv developer documentation](https://developer.beehiiv.com).
