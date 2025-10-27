# Simple Passphrase Generator (Zendesk App + Demo)

A lightweight, browser-based **CSR-friendly passphrase generator** that builds NIST-compliant, human-readable login phrases for **temporary account resets**.  
Runs entirely client-side — no data is sent.

> **Pattern:** `color + object + integer`  
> **Example:** `Blue-horse-823` or `Green.cactus.4821`

---

## ✳️ Highlights

- **Readable & secure:** easy to say and type over the phone.  
- **Meets most password policies:** uppercase, lowercase, digits, punctuation.  
- **Configurable:** choose minimum length (12–20, default 15).  
- **Crypto-random:** uses Web Crypto API for secure randomness.  
- **Client-side only:** no server, no tracking, no data submission.  
- **Accessible UI:** keyboard navigation, ARIA roles, and copy feedback.  
- **100% offline:** can run from a local file or Zendesk App iframe.

---

## 🧩 Zendesk App Setup

This repository is structured as a **Zendesk App Framework (ZAF v2)** project.

### 1. Install Zendesk Apps Tools (ZAT)

You’ll need Ruby (2.7–3.x) installed.

```bash
gem install zendesk_apps_tools
```

---

### 2. Run locally (sideload)

From the project root:

```bash
zat server
```

Then in **Zendesk Support**:

1. Go to **Admin Center → Apps and integrations → Zendesk Support apps → Manage**.  
2. Enable **“Development mode.”**  
3. Open any ticket — the app appears in the **ticket sidebar**.

> The app will hot-reload when you edit files.

---

### 3. Package for upload (private install)

```bash
zat package
```

Then upload the generated `.zip` via:

**Admin Center → Apps and integrations → Zendesk Support apps → Upload private app**

---

## 🌐 Public Demo (GitHub Pages)

This same project doubles as a **public demo site** hosted via **GitHub Pages**.

### Deployment Workflow

Automatic on each push to `main` (see `.github/workflows/deploy.yml`):

- Copies `simple-passphrase-generator.html` → `index.html`
- Copies static assets (`robots.txt`, `sitemap.xml`, `favicon.png`, `og-preview.png`)
- Publishes to the `gh-pages` branch

**Pages configuration:**

```
Settings → Pages → Branch: gh-pages → /(root)
```

### Manual Trigger

You can also deploy manually in the **Actions tab** → “Deploy demo to gh-pages” → **Run workflow**,  
or locally via:

```bash
bash scripts/deploy.sh
```

---

## 🧠 Customization

You can adjust these constants inside `assets/simple-passphrase-generator.html`:

| Constant | Purpose |
|-----------|----------|
| `COLOR` | List of color words |
| `ANIMALS`, `VEGETABLES`, `MINERALS` | Word lists for objects |
| `BANNED_SUBSTRINGS`, `BANNED_NUMS` | Filters for excluded words/numbers |
| `SEPARATORS_ALLOWED` | Allowed separators (`.`, `-`) |
| `MIN_TOTAL_CHARS` | Default minimum length (13–15 recommended) |

---

## 🧰 Development Tips

| Task | Command |
|------|----------|
| Local ZAF preview | `zat server` |
| Package app | `zat package` |
| Deploy demo | `bash scripts/deploy.sh` or via GitHub Actions |
| Reinstall private app | Upload new `.zip` in Admin Center |
| Validate manifest | `zat validate` |

---

## 🏷️ License

**Creative Commons Attribution 4.0 International (CC BY 4.0)**  
© 2025 [Martin Vicknair](https://github.com/martinvicknair)

You are free to **share** and **adapt** this work, including commercial use, with attribution.

> *“Based on Simple Passphrase Generator by Martin Vicknair (CC BY 4.0)”*
