# MiLabs

**Two-step authentication solutions for businesses** · [milabs.co.il](https://milabs.co.il)

MiLabs builds sign-in security for organizations that run on Microsoft 365, with a focus on
users that standard authenticator apps leave out: employees with basic or restricted
("kosher") phones that cannot install apps or browse the web.

## In this repository

| Folder | What it is |
|---|---|
| [`mfa-for-entra/`](mfa-for-entra/) | Architecture and security design of our SMS and voice-call MFA provider for Microsoft Entra ID (description only; the service itself is closed source). |
| [`website-tools/rtl-blog-fix/`](website-tools/rtl-blog-fix/) | Drop-in script that repairs Hebrew (RTL) blog posts on hosted site builders: lost emoji and wrong text direction. |
| [`website-tools/rtl-header-menu/`](website-tools/rtl-header-menu/) | Drop-in RTL site header for hosted site builders: logo row, menu with a dropdown, mobile burger, current-page highlight. |

## Stack we work with

Microsoft Entra ID · Microsoft Graph · Cloudflare (WAF, Workers) · AWS API Gateway (mutual TLS) ·
Node.js · managed cloud hosting

## License

The code in `website-tools/` is released under the [MIT License](LICENSE).
