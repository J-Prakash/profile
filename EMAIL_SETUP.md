# Email Setup Guide for Contact Form

## Setting up EmailJS for Email Notifications

EmailJS is a simple and reliable service that sends emails directly from your website without a server.

### 1. Create an EmailJS Account
1. Go to [https://www.emailjs.com](https://www.emailjs.com)
2. Sign up for a free account
3. Verify your email address

### 2. Add Email Service
1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose "Gmail" (or your preferred email provider)
4. Connect your email account (iamprakash524@gmail.com)
5. Copy the Service ID (e.g., "service_abc123")

### 3. Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template:

**Subject:** New Contact Form Message from {{from_name}}

**Body:**
```
Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio website contact form.
```

4. Save the template and copy the Template ID (e.g., "template_xyz789")

### 4. Get Your Public Key
1. Go to "Account" → "API Keys"
2. Copy your Public Key

### 5. Update the JavaScript
In `script.js`, replace the placeholder values:

```javascript
// Replace YOUR_EMAILJS_PUBLIC_KEY with your actual public key
emailjs.init("YOUR_EMAILJS_PUBLIC_KEY");

// Replace YOUR_SERVICE_ID with your service ID
// Replace YOUR_TEMPLATE_ID with your template ID
const response = await emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams);
```

**Example:**
```javascript
emailjs.init("user_abc123def456");

const response = await emailjs.send('service_abc123', 'template_xyz789', templateParams);
```

### 6. Test the Form
1. Open your website
2. Fill out the contact form
3. Submit the form
4. Check your email (iamprakash524@gmail.com) for the message
5. You should see the beautiful thank you modal popup

## Features Included
- ✅ **Beautiful Modal Popup**: "Thank you for reaching out! I will contact you soon."
- ✅ **Real Email Delivery**: Messages sent directly to your inbox
- ✅ **Form Validation**: Client-side validation with helpful messages
- ✅ **Loading States**: Spinner animation during submission
- ✅ **Success/Error Handling**: Proper error messages if something goes wrong
- ✅ **Contact Details**: Modal shows your email and phone for alternative contact

## Troubleshooting
- **Emails not sending**: Check your EmailJS service connection
- **Modal not showing**: Check browser console for JavaScript errors
- **Form not working**: Verify all EmailJS IDs are correct
- **Spam issues**: Check your spam folder

## Alternative Setup (No Email Service)
If you don't want to set up EmailJS right now, the form will still show the thank you modal. You can:

1. **Use the form as-is**: It will show the modal but won't send emails
2. **Add EmailJS later**: Follow the setup guide above when ready
3. **Use other services**: Formspree, Netlify Forms, or Google Forms

## Security Notes
- EmailJS handles email delivery securely
- No sensitive data is stored on your website
- All communication is encrypted
- You can disable the service anytime from EmailJS dashboard

## Cost
- **Free Plan**: 200 emails per month
- **Paid Plans**: Start at $15/month for more emails
- **Perfect for portfolios**: Free plan is usually sufficient 