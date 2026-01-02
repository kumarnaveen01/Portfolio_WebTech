# Contact Form Setup Instructions

Your portfolio now has a fully functional contact form! Follow these steps to receive messages from visitors.

## 🚀 Quick Setup Guide (5 minutes)

### Step 1: Create a Free EmailJS Account

1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Click **"Sign Up"** (it's completely free)
3. Sign up with your email or Google account

### Step 2: Add an Email Service

1. Once logged in, go to **"Email Services"** in the dashboard
2. Click **"Add New Service"**
3. Choose your email provider (Gmail, Outlook, Yahoo, etc.)
4. Connect your email account
5. **Copy your Service ID** (e.g., `service_abc123`)

### Step 3: Create an Email Template

1. Go to **"Email Templates"** in the dashboard
2. Click **"Create New Template"**
3. Use this template structure:

**Template Name:** `portfolio_contact`

**Template Content:**
```
Subject: New Portfolio Contact from {{from_name}}

From: {{from_name}}
Email: {{from_email}}

Message:
{{message}}
```

4. **Copy your Template ID** (e.g., `template_xyz789`)
5. Click **"Save"**

### Step 4: Get Your Public Key

1. Go to **"Account"** → **"General"**
2. Find **"Public Key"** section
3. **Copy your Public Key** (e.g., `abcdef123456789`)

### Step 5: Update Your Website Code

Open `index.html` and find these three lines (around line 305-320):

```javascript
emailjs.init('YOUR_PUBLIC_KEY');  // Line ~307
```

```javascript
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)  // Line ~330
```

**Replace with your actual IDs:**

```javascript
emailjs.init('abcdef123456789');  // Your Public Key
```

```javascript
emailjs.send('service_abc123', 'template_xyz789', templateParams)  // Your Service ID and Template ID
```

### Step 6: Test Your Form

1. Open your `index.html` in a browser
2. Scroll to the contact form
3. Fill in all fields
4. Click "Send Message"
5. Check your email inbox!

---

## 🎯 What You Should See

**When form is submitted:**
- Button shows "Sending..." with a spinner
- Success message appears: "Your message has been sent successfully!"
- Form fields are cleared
- Message disappears after 5 seconds

**You will receive an email with:**
- Sender's name
- Sender's email address
- The message they wrote

---

## 📧 Example Configuration

Here's what your code should look like after setup:

```javascript
// Initialize EmailJS
(function() {
  emailjs.init('Kx7Jm9n4P2Qr5tUv');  // Your Public Key
})();

// Send email
emailjs.send('service_gmail_123', 'template_contact_456', templateParams)
```

---

## ⚙️ Customization Options

### Change the "To Name" in Emails

In `index.html`, find this line:
```javascript
to_name: 'Naveen Kumar' // Your name
```

Change it to your preferred name.

### Modify Email Template

You can customize the email template in EmailJS dashboard:
- Add HTML formatting
- Include company/website branding
- Add automatic reply messages

### Form Validation

The form already includes:
- Required field validation
- Email format validation
- Prevents empty submissions

---

## 🔒 Security & Privacy

✅ **Secure:** EmailJS uses secure connections (HTTPS)  
✅ **No Backend Required:** Everything runs in the browser  
✅ **Free Tier:** 200 emails/month included  
✅ **No API Keys Exposed:** Public key is safe to expose  
✅ **Spam Protection:** EmailJS includes rate limiting  

---

## 📊 Free Tier Limits

- **200 emails per month**
- **50KB per email**
- Perfect for personal portfolios!

If you need more, upgrade to their paid plan.

---

## 🐛 Troubleshooting

### Form doesn't send messages

1. **Check Console for Errors:**
   - Right-click → Inspect → Console tab
   - Look for error messages

2. **Verify Your IDs:**
   - Public Key is correct
   - Service ID is correct
   - Template ID is correct

3. **Check EmailJS Dashboard:**
   - Service is connected and active
   - Template is saved and published

### Emails not arriving

1. **Check Spam Folder**
2. **Verify Email Service Connection:** Go to EmailJS → Email Services → Test Connection
3. **Check Monthly Limit:** EmailJS Dashboard shows usage

### Button stays in "Sending..." state

- Check your internet connection
- Verify EmailJS CDN is loading (check Console)
- Make sure Public Key is initialized

---

## 💡 Alternative Services

If you prefer other solutions:

### 1. **Formspree** (formspree.io)
- Simple form endpoint
- 50 submissions/month free

### 2. **Web3Forms** (web3forms.com)
- 250 submissions/month free
- No registration required

### 3. **Netlify Forms** (if hosted on Netlify)
- 100 submissions/month free
- Built-in spam filtering

---

## 📝 Support

- **EmailJS Documentation:** [docs.emailjs.com](https://www.emailjs.com/docs/)
- **EmailJS Support:** support@emailjs.com

---

## ✅ Setup Checklist

- [ ] Created EmailJS account
- [ ] Added email service
- [ ] Created email template
- [ ] Copied Public Key
- [ ] Copied Service ID
- [ ] Copied Template ID
- [ ] Updated `index.html` with all three IDs
- [ ] Tested form submission
- [ ] Received test email

---

**🎉 Once complete, your contact form will be fully functional!**

Visitors can send you messages directly from your portfolio, and you'll receive them in your inbox.
