[README.md](https://github.com/user-attachments/files/31050737/README.md)
# The Metropolis — Dining Directory

A static prototype directory of F&B outlets at The Metropolis (9 & 11 North Buona Vista Drive, Singapore 138588), with search, a Halal filter, cuisine grouping, reservation call-outs, and menu links.

This is a single static HTML file — no build step, no dependencies, no backend.

## Editing the outlet data

All outlet data lives in the `outlets` array near the bottom of `index.html`, inside the `<script>` tag. Each entry looks like:

```js
{
  name: "Outlet Name",
  cuisine: "Category",
  tower: "Tower 1",
  unit: "#01-00",
  halal: false,
  reservation: true,
  phone: "+65XXXXXXXX",   // or null
  website: "https://...", // or null
  note: "Short description shown on the card."
}
```

Add, remove, or edit entries directly — the page re-renders automatically based on this array.

## Deploy to Vercel via GitHub

1. **Create a new GitHub repo**
   - Go to [github.com/new](https://github.com/new)
   - Name it e.g. `metropolis-food-directory`, keep it public or private, don't initialize with a README (we already have one)
   - Click **Create repository**

2. **Push this project to it**, from a terminal on your own machine (after downloading these files):
   ```bash
   cd metropolis-food-directory
   git init
   git add .
   git commit -m "Initial commit: Metropolis dining directory"
   git branch -M main
   git remote add origin https://github.com/<your-username>/metropolis-food-directory.git
   git push -u origin main
   ```

3. **Deploy on Vercel**
   - Go to [vercel.com/new](https://vercel.com/new)
   - Click **Import Git Repository**, select the repo you just pushed
   - Vercel will auto-detect it as a static site (no framework) — no config needed, since `index.html` sits at the project root
   - Click **Deploy**
   - You'll get a live URL like `metropolis-food-directory.vercel.app` within about a minute

4. **Future updates**: any time you edit `index.html` (e.g. adding an outlet) and push to `main`, Vercel redeploys automatically.

## Local preview

Just open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.
