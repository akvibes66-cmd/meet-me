# Meetme by PELQ — Global Skills Marketplace

A lightweight, single-file web application for trading creative, technical, and academic skills globally. Users can list services, search listings, and connect directly with creators via WhatsApp with zero platform fees.

---

## Features

* **Direct Creator Connections:** Contact service providers directly via WhatsApp[cite: 1].
* **Live Search & Category Filtering:** Search listings dynamically by keyword or filter by categories like Photo & Video, Code & Web, Tutoring & Notes, and Design & Branding[cite: 1].
* **Supabase Integration:**
  * **Passwordless Authentication:** Sign-in via Magic Link OTP[cite: 1].
  * **Database & Storage:** Real-time data fetching, listing management, and image file uploads stored via Supabase Storage buckets[cite: 1].
* **Responsive UI:** Built with custom CSS variables, CSS grid/flexbox layouts, and Google Fonts (Fraunces & DM Sans)[cite: 1].

---

## Prerequisites

Before running the application, ensure you have set up:

1. A **Supabase** account and project[cite: 1].
2. A public Supabase Storage bucket named `skill-images` for handling listing image uploads[cite: 1].
3. A PostgreSQL Database table named `skills` with the following columns:
   * `id` (uuid, primary key)
   * `created_at` (timestamp with time zone)
   * `user_id` (uuid)
   * `name` (text)
   * `meta` (text)
   * `category` (text)
   * `title` (text)
   * `description` (text)
   * `price` (text)
   * `phone` (text)
   * `image_url` (text, nullable)
4. An RPC stored procedure named `get_skill_phone` accepting `skill_id` to securely fetch contact details[cite: 1].

---

## Configuration

1. Rename `gemini-code-1787241092155.html` to `index.html` in your project root[cite: 1].
2. Open `index.html` and replace the placeholder credentials with your actual Supabase project keys[cite: 1]:

```javascript
const SUPABASE_URL = 'YOUR_SUPABASE_URL';
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY';
```[cite: 1]

---

## Local Development & Deployment

This project uses static CDN client scripts, so no build tools (`npm` or `yarn`) are required[cite: 1].

### Running Locally
Open `index.html` directly in your browser, or start a local static server:

```bash
# Using Python
python3 -m http.server 8000

# Using Node.js
npx serve .
