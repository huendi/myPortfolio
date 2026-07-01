# EmailJS Setup Instructions

## Step 1: Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

## Step 2: Create Email Service
1. After logging in, click on "Email Services" in the dashboard
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Connect your email account and grant permissions
5. Note down your **Service ID** (it will look like: `service_7v00mi8`)

## Step 3: Create Email Template
1. Click on "Email Templates" in the dashboard
2. Click "Create New Template"
3. Fill in the template details:
   - **Template Name**: Contact Form Message
   - **Subject**: {{subject}}
   - **Content**:
     ```
     You have received a new message from your portfolio website:
     
     From: {{from_email}}
     Subject: {{subject}}
     
     Message:
     {{message}}
     
     ---
     Sent via Portfolio Contact Form
     ```
4. Click "Save"
5. Note down your **Template ID** (it will look like: `template_mrsqgu8`)

## Step 4: Get Your Public Key
1. Click on "Account" in the dashboard
2. Go to "API Keys" section
3. Copy your **Public Key** (it will look like: `3Jov_xfKsuUR0hFET`)

## Step 5: Update Your Code
Replace the placeholder values in your `index.html` file:

```javascript
// Find this line in your script
emailjs.init("YOUR_PUBLIC_KEY");

// Replace with your actual public key
emailjs.init("3Jov_xfKsuUR0hFET");

// Find this line
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', formData)

// Replace with your actual service and template IDs
emailjs.send('service_7v00mi8', 'template_mrsqgu8', formData)
```

## Step 6: Test Your Form
1. Open your portfolio website
2. Go to the Contact section
3. Fill out the form with test information
4. Click "Send"
5. Check your email inbox for the message

## Important Notes
- EmailJS free tier allows 200 emails per month
- The service is secure - your email address is never exposed in the frontend code
- Make sure to test thoroughly before deploying
- If you don't receive emails, check your spam folder

## Troubleshooting
If emails aren't sending:
1. Check browser console for error messages
2. Verify all IDs are correctly copied
3. Ensure your EmailJS service is properly connected
4. Check that you haven't exceeded the free tier limit

For more help, visit [EmailJS Documentation](https://www.emailjs.com/docs/)
