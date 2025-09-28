# 🚀 Your Twilio WhatsApp Setup Guide

## ✅ Your Twilio Account Details
- **Account SID**: `AC6425d40fad5531921a08f161fe7e87c3`
- **Phone Number**: `+1 832 905 1435`
- **Location**: League City, TX, US

## 🔧 Step 1: Create Environment File (2 minutes)

Create a file called `.env.local` in your project root with:

```env
TWILIO_ACCOUNT_SID=AC6425d40fad5531921a08f161fe7e87c3
TWILIO_AUTH_TOKEN=your_actual_auth_token_here
TWILIO_WHATSAPP_NUMBER=whatsapp:+14155238886
```

**Important**: Replace `your_actual_auth_token_here` with your real Auth Token from Twilio Console.

## 📱 Step 2: Set Up WhatsApp Sandbox (5 minutes)

Since your number isn't approved for WhatsApp Business API yet, use the sandbox:

1. Go to: https://console.twilio.com/us1/develop/sms/try-it-out/whatsapp-learn
2. Click "Set up WhatsApp sandbox"
3. You'll see a sandbox number like `+1 415 523 8886`
4. Send "join <sandbox-code>" to this number from your WhatsApp
5. You'll get a confirmation message

## 🧪 Step 3: Test Your Setup (3 minutes)

Run the test script:
```bash
node test-twilio.js
```

This will verify your credentials and connection.

## 🚀 Step 4: Test the Web App (5 minutes)

1. Start the server: `npm run dev`
2. Go to: http://localhost:3000/whatsapp-connect
3. Check if all configuration shows green checkmarks
4. Test by submitting a voter registration form

## 📱 Step 5: Test WhatsApp Messaging

Once sandbox is set up, test with:
```bash
curl -X POST http://localhost:3000/api/test-whatsapp \
  -H "Content-Type: application/json" \
  -d '{"phoneNumber": "your_phone_number", "message": "Test from Twilio!"}'
```

## 🔄 For Production (Later)

When ready for production:
1. Apply for WhatsApp Business API approval
2. Get your number `+1 832 905 1435` approved for WhatsApp
3. Update `.env.local`:
   ```env
   TWILIO_WHATSAPP_NUMBER=whatsapp:+18329051435
   ```

## 🆘 Troubleshooting

### "Twilio WhatsApp service not configured"
- Check your `.env.local` file exists
- Verify all three variables are set correctly
- Restart the development server

### "Message not delivered"
- Make sure you sent "join <sandbox-code>" to the sandbox number
- Check if the phone number format is correct (+91XXXXXXXXXX)
- Verify your Twilio account has sufficient balance

### "Invalid phone number"
- Use format: `+91XXXXXXXXXX` (with country code)
- Remove any spaces or special characters

## 💰 Pricing
- **Sandbox**: Free for testing
- **Production**: ~$0.005 per message
- **Your Account**: $15 free credit included

## ✅ What You'll Get
- ✅ Real WhatsApp messages sent to users
- ✅ Thank you messages when forms are submitted
- ✅ No QR codes or session management needed
- ✅ Production-ready, scalable solution

---
**Ready to test?** Follow the steps above and you'll have WhatsApp working in 15 minutes! 🎉
