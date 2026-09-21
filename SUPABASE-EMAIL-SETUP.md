# Brand Supabase authentication emails

There are two separate pieces of email branding:

1. **Subject and message:** Supabase Dashboard → Authentication → Email Templates → Confirm signup.
2. **Sender name:** Supabase Dashboard → Authentication → SMTP Settings. This requires a custom SMTP provider for production delivery.

## Confirm-signup template

Use this subject:

`Confirm your Nightly Accountability account`

Use this message:

```html
<div style="font-family:Arial,sans-serif;max-width:520px;margin:auto;padding:32px;color:#172033">
  <h1 style="font-size:24px;margin:0 0 16px">Welcome to Nightly Accountability</h1>
  <p style="line-height:1.6">Confirm your email to securely sync your habits and check-ins across your devices.</p>
  <p style="margin:28px 0">
    <a href="{{ .ConfirmationURL }}" style="display:inline-block;background:#7567e8;color:white;text-decoration:none;padding:12px 18px;border-radius:10px">Confirm my account</a>
  </p>
  <p style="color:#667085;font-size:13px;line-height:1.5">If you did not create this account, you can ignore this email.</p>
</div>
```

Use the same visual wording for the Reset password template, keeping its existing `{{ .ConfirmationURL }}` link.

## Sender name

For public users, connect an SMTP provider such as Resend, Postmark, SendGrid, Brevo, or Amazon SES. Set:

- Sender name: `Nightly Accountability`
- Sender address: an address on a domain you control, such as `hello@yourdomain.com`

Keep Supabase's default mail server only for development testing; it has recipient and rate-limit restrictions.
