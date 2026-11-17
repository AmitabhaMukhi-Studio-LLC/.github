# AmitabhaMukhi Studio LLC — Master Multi-Applet Suite
**Document Version:** `1.0.0-PROD`  
**Legal Entity:** AmitabhaMukhi Studio LLC  
**Jurisdiction:** Albuquerque, New Mexico, USA  
**Domain:** [amitabhamukhistudio.com](https://amitabhamukhistudio.com)  
**Principal & Founder:** AmitabhaMukhi Vipaseni ([ORCID: 0009-0002-7454-3895](https://orcid.org/0009-0002-7454-3895))  
**Zenodo Community Archive:** [zenodo.org/communities/amitabhamukhistudio](https://zenodo.org/communities/amitabhamukhistudio)  
**Verified GitHub:** [github.com/AmitabhaMukhi-Studio-LLC](https://github.com/AmitabhaMukhi-Studio-LLC)  
**Direct Communications:** `contact@amitabhamukhistudio.com`  

*Motto: "Artisanal Grace Meets Computational Precision"*

---

## 1. Overview & Architecture

AmitabhaMukhi Studio LLC is an independent consumer software and open scientific computing laboratory registered in Albuquerque, New Mexico. The master sandbox integrates four cohesive operational pillars accessed via the unified Master Navigation Controller:

```
┌────────────────────────────────────────────────────────────────────────┐
│ AmitabhaMukhi Studio Master Shell (App.tsx)                            │
│ Header: Corporate Seal | Studio Nav Tabs | ORCID & GitHub Badges       │
├────────────────────────────────────────────────────────────────────────┤
│ [Tab 0: Studio Portal]   │ Corporate Overview, Philosophy, Zenodo/ORCID│
│ [Tab 1: Fiber & Loop]    │ Algorithmic Knitting & Topology Studio      │
│ [Tab 2: Savor & Crucible]│ Computational Gastronomy & Thermal Kitchen  │
│ [Tab 3: Kin & Paw]       │ Chronobiological Pet Longevity & Nutrition  │
├────────────────────────────────────────────────────────────────────────┤
│ Persistent Footer: NM LLC Notice | ORCID 0009-0002-7454-3895 | Zenodo   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 2. The Studio Triad (Computational Engines)

### Pillar I: Fiber & Loop (Algorithmic Knitting & Topology Studio)
- **Topological Yarn Modeling:** Parametric formulation of loop elastica bending curves and loop-length estimation:
  $$L_{\text{loop}} = 4c + 2w + 8t$$
  Where $c$ is course spacing, $w$ is wale spacing, and $t$ is effective yarn diameter accounting for yarn crossing tension.
- **Interactive 2D Grid Canvas:** Symbol tools ($K, P, YO, K2tog, SSK, \text{Cable } 2/2 \text{ LC/RC}$) with click-and-drag cell paint, repeat tile boxing, and horizontal symmetry mirroring.
- **Bidirectional Pattern Compiler:** Translates visual 2D stitch lattices into standardized, human-readable knitting instructions with automatic alternating Right-Side (RS) and Wrong-Side (WS) directional logic.
- **Yarn Gauge & Meterage Engine:** Swatch calibration (stitches/rows per 10cm), yarn weight conversion (Lace to Super Bulky), total meterage projection, and finished garment weight estimation.
- **Vector & Archival Exports:** SVG vector chart download, JSON pattern schema, and print-ready archival cards.

### Pillar II: Savor & Crucible (Computational Gastronomy & Thermal Kitchen)
- **Bipartite Aroma Pairing Matrix:** Quantifies chemical flavor pairing affinity through Jaccard/cosine volatile aromatic compound intersections across 60+ foundational ingredients:
  $$J(A, B) = \frac{|C_A \cap C_B|}{|C_A \cup C_B|}$$
- **1D Transient Thermal Conduction Solver:** Fourier heat diffusion model across culinary substrates:
  $$\frac{\partial T}{\partial t} = \alpha \nabla^2 T$$
  Supports Slab (steak/fish), Cylinder (roast), and Sphere (boule loaf) geometries with live core-to-surface temperature gradient charts.
- **Precision Baker's Percentage & Hydration Scaler:** Dynamic stoichiometric scaling (flour $= 100\%$, hydration $50\%–100\%$, salt $1.5\%–3.0\%$, levain $10\%–35\%$) with Arrhenius temperature-compensated yeast fermentation kinetics ($Q_{10}$ rate doubling).
- **Archival Export:** Culinary recipe JSON schemas and print-ready cards.

### Pillar III: Kin & Paw (Chronobiological Pet Longevity & Nutrition)
- **Kleiber’s Allometric Energy Law:** Non-linear veterinary metabolic scaling for canine and feline biology:
  $$RER = 70 \cdot (BW_{\text{kg}})^{0.75}$$
  Multiplied by life-stage Maintenance Energy Requirement (MER) condition factors, Body Condition Score (BCS 1–9), and seasonal photoperiod ephemeris.
- **Stoichiometric Nutrient Balancer:** Real-time Dry Matter (DM) macronutrient breakdown and strict Calcium-to-Phosphorus ratio validation:
  $$\text{Target: } \frac{Ca}{P} = 1.2:1 \quad (\text{Safe: } 1.0:1 \text{ to } 1.5:1)$$
- **24-Hour Circadian Schedule & Medication Journal:** Solar-synchronized dawn, solar noon, dusk, and nocturnal windows for feeding portions, medication dose intervals, hydration targets, and 7-day symptom tracking.
- **Veterinary Clinical Export:** One-click print-ready diagnostic summary card for clinical handoff during examinations.

---

## 3. Cloudflare Configuration & Deployment Guide

This project is pre-configured and hardened for **Cloudflare Pages** and **Cloudflare Workers**.

### Configuration Files Included:
- `wrangler.toml`: Cloudflare CLI and project deployment settings.
- `public/_redirects`: Single-Page Application (SPA) edge routing fallback (`/* /index.html 200`).
- `public/_headers`: Strict HTTP security headers and edge caching directives.
- `functions/api/contact.ts`: Edge Worker function running in Cloudflare V8 isolates for secure inquiry dispatch.

### Option A: 1-Click Deployment via Cloudflare Pages Dashboard (Recommended)
1. Push this repository to GitHub under your organization (`https://github.com/AmitabhaMukhi-Studio-LLC`).
2. Log in to the [Cloudflare Dashboard](https://dash.cloudflare.com/) and navigate to **Workers & Pages** > **Create application** > **Pages** > **Connect to Git**.
3. Select your repository and configure the build settings:
   - **Framework preset:** `Vite`
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
   - **Root directory:** `/` (default)
4. Under **Environment variables**, optionally verify:
   - `NODE_VERSION`: `20`
5. Click **Save and Deploy**. Cloudflare will build the Vite assets and deploy them globally to 300+ Anycast edge data centers.

### Option B: Deployment via Cloudflare Wrangler CLI
```bash
# 1. Install Wrangler globally or use npx
npm install -g wrangler

# 2. Authenticate with your Cloudflare account
npx wrangler login

# 3. Build the production bundle
npm run build

# 4. Deploy the 'dist' directory to Cloudflare Pages
npx wrangler pages deploy dist --project-name=amitabhamukhi-studio
```

### Custom Domain Setup (`amitabhamukhistudio.com`)
1. In Cloudflare Pages, navigate to your project > **Custom domains**.
2. Click **Set up a domain** and enter `amitabhamukhistudio.com`.
3. Cloudflare will automatically configure the DNS CNAME records and issue a zero-config Universal SSL/TLS certificate.
4. Set SSL/TLS encryption mode to **Full (Strict)** under **SSL/TLS** > **Overview**.

---

## 4. Security Hardening Specifications

The website is hardened across all architectural layers:

### A. Edge HTTP Security Headers (`public/_headers` & `dist/_headers`)
- **Strict-Transport-Security (HSTS):** `max-age=31536000; includeSubDomains; preload` enforces HTTPS encryption and prevents SSL-stripping man-in-the-middle attacks.
- **X-Content-Type-Options:** `nosniff` prevents MIME type confusion and sniffing attacks.
- **X-Frame-Options:** `SAMEORIGIN` prevents clickjacking by disallowing framing outside the authorized origin.
- **Referrer-Policy:** `strict-origin-when-cross-origin` protects sensitive referral paths during outbound navigation.
- **Permissions-Policy:** Restricts invasive hardware APIs:
  `accelerometer=(), autoplay=(), camera=(), encrypted-media=(), fullscreen=(self), geolocation=(), gyroscope=(), magnetometer=(), microphone=(), midi=(), payment=(), sync-xhr=(), usb=()`
- **Content-Security-Policy (CSP):** Restricts script, style, and connect sources to `'self'`, Google Fonts (`fonts.googleapis.com`, `fonts.gstatic.com`), Zenodo (`zenodo.org`), ORCID (`orcid.org`), and GitHub (`github.com`).
- **Edge Caching Rules:**
  - `/index.html`: `public, max-age=0, must-revalidate` ensures users immediately receive fresh builds upon deployment.
  - `/assets/*`: `public, max-age=31536000, immutable` leverages Vite fingerprinting for high-speed edge caching.

### B. Application-Level Security (`src/utils/security.ts`)
- **Input Sanitization (`sanitizeInput`):** HTML character escaping (`& < > " ' /`) applied across all inquiry forms, custom feed labels, and stitch pattern imports to neutralize Cross-Site Scripting (XSS).
- **Email Syntax Validation (`isValidEmail`):** RFC 5322 regex validation preventing header injection and malformed inputs.
- **Prototype Pollution Prevention (`safeJsonParse`):** Sanitizing custom JSON uploads to strip `__proto__`, `constructor`, and `prototype` keys.
- **Rate-Limiting & Throttling (`checkRateLimit`):** Client-side session cooldown timer preventing spam loops and brute-force form flooding.

### C. Cloudflare Edge Function Hardening (`functions/api/contact.ts`)
- Runs in serverless Cloudflare Workers V8 isolates with zero server maintenance.
- Enforces strict 15KB request body payload caps to prevent memory buffer denial-of-service.
- Edge-evaluated CORS headers and preflight handling.

---

## 5. Local Development & Verification

```bash
# Clone the repository
git clone https://github.com/AmitabhaMukhi-Studio-LLC/amitabhamukhi-studio.git
cd amitabhamukhi-studio

# Install dependencies
npm install

# Start local development server (port 3000)
npm run dev

# Run static type checking and linter
npm run lint

# Compile production bundle
npm run build

# Preview production build locally
npm run preview

# Test with local Cloudflare Pages runtime emulation
npx wrangler pages dev dist
```

---

## 6. Open Science & Archival Registry

| Resource | Identifier / Link | Status |
| :--- | :--- | :--- |
| **Principal Researcher** | AmitabhaMukhi Vipaseni ([ORCID: 0009-0002-7454-3895](https://orcid.org/0009-0002-7454-3895)) | Verified Active |
| **Zenodo Open Archive** | [zenodo.org/communities/amitabhamukhistudio](https://zenodo.org/communities/amitabhamukhistudio) | Draft Community Deposit |
| **Source Code Registry** | [github.com/AmitabhaMukhi-Studio-LLC](https://github.com/AmitabhaMukhi-Studio-LLC) | Public / Apache 2.0 |
| **Official Contact** | `contact@amitabhamukhistudio.com` | Primary Inquiries Desk |
| **Location** | Albuquerque, New Mexico, USA | Registered Entity |

---

## 7. License
Copyright © 2026 AmitabhaMukhi Studio LLC.  
Licensed under the Apache License, Version 2.0 (the "License").
