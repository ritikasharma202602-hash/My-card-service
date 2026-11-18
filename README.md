# My Card Services — original enquiry portal

This is an original customer-support/enquiry website, not a bank website and not affiliated with Axis Bank or any financial institution. It deliberately does **not** collect card numbers, CVV, PINs, passwords or OTPs.

## Run on Replit
1. Create a new **Node.js** Replit project.
2. Upload/extract this project, keeping `server.js`, `package.json`, `public/` and `.env.example` at the project root.
3. In Replit **Secrets / Environment Variables**, add the values listed below.
4. Run `npm install`, then `npm start`.
5. Open `/` for the public site and `/admin` for the admin panel.

## Required environment variables
- `SESSION_SECRET`: long random secret.
- `ADMIN_USERNAME`: admin login username.
- `ADMIN_PASSWORD`: strong admin password.
- `NOTIFY_EMAIL`: already set in the project to `kaminisharma80818081@gmail.com`.
- `SMTP_USER`: Gmail account that will send notification emails.
- `SMTP_PASS`: Google **App Password** for that sending Gmail account (not your normal Gmail password).

Optional SMTP settings default to Gmail SMTP on port 465 with TLS.

## Gmail notification setup
Turn on 2-Step Verification for the sending Gmail account and create an App Password in Google Account security settings. Put that 16-character App Password in `SMTP_PASS`. Set `SMTP_USER` to that Gmail address. `NOTIFY_EMAIL` is the inbox that receives notifications. Test with a sample enquiry after deployment. If SMTP is not configured, submissions are still saved but email notifications will not be sent.

## Admin
Open `/admin` and sign in with the `ADMIN_USERNAME` and `ADMIN_PASSWORD` you configured. You can review enquiries, update their status, and delete them.

## Storage and deployment note
Enquiries are stored in `data/enquiries.json`. This is suitable for a simple demo/small deployment. For production, use a persistent database and a persistent disk; some hosting platforms erase local files on redeploy. Use HTTPS in production and set `NODE_ENV=production`.

## Privacy
Publish a privacy notice explaining what contact information you collect, why you collect it, how long you retain it, and how customers can request deletion. Only collect details needed to respond to the enquiry.
