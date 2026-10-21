# Publish a site

> **TL;DR** Awesomic can put your HTML on a **free managed site**. Custom domains need a **manual publish**.

![A page in Preview, next to the chat](../../.github/assets/screenshots/serein-preview.jpg)

## Steps

1. Open project **Settings → Publishing**. Read the **Live link** message.
2. To publish by hand: use **Publish** in an HTML preview, or **Settings → Publishing**.
3. Framework build? Ask the agent to publish the **output folder** (like `out`, `dist` or `build`). It must contain `index.html`.
4. Pick the **website**, **source HTML**, **page** and **Path** (starts with `/`, like `/verify-full`).
5. Press **Publish**. Wait for **success** before sharing.
6. Read the live-link message again.

## Live link states

- **Reserved** link: still needs a publish.
- **Ready to share**: the live page is current.
- **You have unpublished changes**: publish again.
- Awesomic **may auto-publish** `index.html` or a top-level HTML file after it is saved. Only to the free site.

## Use your own domain

- Open **Domains & Pages**. Enter a domain like `www.example.com`. Press **Add domain**.
- At your **DNS provider**, add the two records on the domain card: a **CNAME** and a **TXT**.
- On **Cloudflare**, set the CNAME to **DNS only**.
- Press **Verify**. Awesomic checks TXT, then CNAME, then issues an **HTTPS certificate**.
- Until then the domain shows **Not connected yet** and names the missing step.
- When it shows **Connected**, press **Make primary**. Then publish from **Publishing**.

## If something goes wrong

- Lists still **loading**? Wait.
- **No website yet** and **No HTML files are available for publishing yet** are different empty states.
- Website list failed? Press **Retry**.
- File, page or publish **error**? Keep your selection. Fix what the message says.
- **Publish** unavailable? Check project access, publish permission, selections and DNS.
- Verify says a **record is missing**? Compare type, name and value with the domain card.
- Some DNS providers want only the **name part**, like `www` and `_somic.www`.
- New DNS records **take time**. Press **Verify** again later.
- **Certificate being issued**? Records are fine. Verify again soon.
- **Custom domains are not available**? They cannot be connected in this environment yet.

## Good to know

- A **local preview** is not a live site.
- Adding a custom domain **turns off auto-publish** for that site.
- A **root domain** (`example.com`) needs CNAME flattening, ALIAS or ANAME. Otherwise use `www` and forward the root.
- Point only at the **CNAME target** shown. **Never** at IP addresses.
- **CAA records** can block the certificate.
- Removing a domain does **not** delete DNS records. Remove them at your provider.

---

**Next:** [Sharing and guest access](sharing-and-guest-access.md)
