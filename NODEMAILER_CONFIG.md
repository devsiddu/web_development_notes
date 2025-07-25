To use nodemailer for sending emails, follow the steps below:
## nodemailer.js
#### Paste this code in nodemailer.js and change your nodemailer configuration

```javascript
import nodemailer from "nodemailer";
// Create a transporter for SMTP
const transporter = nodemailer.createTransport({
  host: "smtp.example.com", // Replace with your SMTP host
  port: 587,
  auth: {
    user: process.env.SMTP_USER, //replace with your SMTP user
    pass: process.env.SMTP_PASS, //replace with your SMTP password
  },
});

export default transporter;
```
## Usage
```
await transporter.sendMail({
      from: {
        name: "name of your website",
        address: process.env.SENDER_EMAIL, // replace with your sender email
      },
      to: "recipient@example.com", // replace with the recipient email
      subject: "Subject of the email",
      html: `
        <h1>Hello,</h1>
        <p>This is a test email sent using Nodemailer.</p>
      `,
    });
```
After that, you can use this transporter in your application to send emails as needed.