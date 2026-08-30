# eif-format.org

The website for the Evidence Integrity Framework. One self-contained `index.html` with no build step, no framework, and no dependencies beyond two Google Fonts requests.

## Deploying

The site publishes to GitHub Pages automatically on push to `main` via `.github/workflows/deploy.yml`.

First-time setup:

1. **Settings → Pages → Build and deployment → Source: GitHub Actions**
2. Push to `main`. The workflow deploys the repository root.
3. **Settings → Pages → Custom domain**: enter `eif-format.org`. The `CNAME` file is already committed.
4. At the DNS registrar, point the apex domain at GitHub Pages:

   | Type | Name | Value |
   |---|---|---|
   | A | `@` | `185.199.108.153` |
   | A | `@` | `185.199.109.153` |
   | A | `@` | `185.199.110.153` |
   | A | `@` | `185.199.111.153` |
   | CNAME | `www` | `eif-format.github.io` |

5. Once DNS resolves, tick **Enforce HTTPS**.

Verify the current apex IP addresses against GitHub's documentation before configuring DNS; they change infrequently but they do change.

## Previewing locally

Windows, from this directory:

```cmd
python -m http.server 8000
start http://localhost:8000
```

## Editing

Everything is in `index.html`: styles in the `<style>` block, the tile inspector in the `<script>` block at the end.

Two things to preserve when editing:

**The limitations section stays on the front page.** It is there deliberately. Anyone evaluating a format for evidence use will find the limitations eventually, and finding them in our own documentation reads as competence rather than concealment.

**The positioning stays honest.** The site says plainly what C2PA and JPEG Trust do better. They have the ecosystem, the ISO process, and the camera hardware. Claiming otherwise would not survive contact with a technical reviewer, and would cost more credibility than it bought.

## Content

No pricing, no company branding, no regional framing. The site presents EIF as an open specification, which is what it is.
