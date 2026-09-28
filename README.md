# Elisabeth Anthony Pet Sitting — one-page site

A plain static site. No build step, no dependencies, no framework. Three files
and a folder of images.

```
index.html      the whole page
styles.css      all the styling
favicon.svg     the little teal paw in the browser tab
robots.txt      tells search engines they may index the site
sitemap.xml     helps Google find the page
images/         hero photo, the daily-update gallery, social share card
```

---

## 1. Put it on GitHub

1. Go to <https://github.com/new>.
2. Repository name: `elisabeth-pet-sitting`. Set it to **Public** (Vercel's free
   tier works with private repos too, public is simpler).
3. Do **not** tick "Add a README" — this folder already has one.
4. Create the repository. On the next screen click **uploading an existing file**.
5. Drag in everything from this folder, **including the `images` folder**.
6. Click **Commit changes**.

## 2. Deploy on Vercel

1. Go to <https://vercel.com> and sign in with the same GitHub account.
2. **Add New → Project**, then **Import** `elisabeth-pet-sitting`.
3. Framework Preset: **Other**. Leave build command and output directory empty.
4. Click **Deploy**.

About a minute later the site is live at something like
`elisabeth-pet-sitting.vercel.app`.

## 3. Custom domain (optional, about $12–15 a year)

Buy a domain anywhere (Namecheap, Cloudflare, Google Domains). Something like
`elisabethpetsitting.com`. In Vercel: **Project → Settings → Domains → Add**,
then follow the DNS instructions it gives you.

Once the domain is live, open `index.html`, `robots.txt` and `sitemap.xml` and
replace every `REPLACE-WITH-YOUR-DOMAIN` with the real domain. There are six
of them. Commit the change and Vercel redeploys on its own.

---

## Adding the meet-and-greet booking calendar

The site currently shows call and email buttons in the meet-and-greet section.
To replace them with a real booking calendar:

1. Elisabeth opens Google Calendar on a computer.
2. **Create → Appointment schedule**. Name it "Meet and greet", set the length
   to 30 minutes, and set the hours she's willing to do them.
3. Under **Booked appointment settings**, turn on the questions she wants asked
   (pet's name, address, dates of travel).
4. Save, then click **Share** → copy the **booking page link**, or use
   **</> Embed** to copy the iframe code.
5. In `index.html`, find the two lines that say `booking:start` and
   `booking:end`. Replace everything between them with the embed code.

If she'd rather not embed it, replace the two buttons with a single link:

```html
<div class="actions actions-center">
  <a class="btn btn-solid" href="PASTE-BOOKING-LINK-HERE">Pick a time</a>
</div>
```

---

## Adding or swapping photos

1. Resize the photo to about **900 pixels wide** before adding it. Phone photos
   are 4000px wide and will make the page slow.
2. Drop it in the `images` folder.
3. In `index.html`, find the comment that says "To add more photos" and copy one
   of the `<figure>` blocks below it. Change the file name, the `width` and
   `height` numbers to match the new photo, and write a short `alt` description
   of what's in it.

The gallery reflows on its own — two, six or twelve photos all lay out fine.

To change the main photo at the top, replace `images/hero-1600.jpg` and
`images/hero-900.jpg` (and the matching `.webp` files) keeping the same names.

---

## Changing text or the phone number

Everything is in `index.html` in plain English. The phone number appears in five
places: the header button, the hero button, the text-message button, the footer
and the bottom bar on phones. It's also in the structured data block at the very
bottom of the file, which is what Google reads. Change all of them.

---

## Notes

- Photos load in modern WebP format with a JPEG fallback, so the page stays fast
  on a phone over cell data.
- The teal bar at the bottom of a phone screen is a fixed call/text bar. Most
  visitors will be on a phone and want to call, so it stays on screen.
- The page carries `ProfessionalService` structured data with the service area,
  which is what Google Search and Maps read. Worth also claiming a free Google
  Business Profile — for a local service business that drives more calls than
  the website itself will.
