# Jaafar Appliances — Setup Guide
## How to get the site live + give Ali the admin panel

---

## What you're setting up

| Piece | What it does | Cost |
|---|---|---|
| **GitHub** | Stores all the website files | Free |
| **Netlify** | Hosts the website live on the internet | Free |
| **Decap CMS** | Gives Ali a login page to edit photos/text | Free |

Once this is done, Ali goes to **jaafar-appliances.com/admin**, logs in with his email, and can add/remove/edit photos and descriptions by himself — no code, no you.

---

## STEP 1 — Create a GitHub account (if you don't have one)

1. Go to **github.com**
2. Click **Sign up**
3. Use any email — remember the password

---

## STEP 2 — Upload the website files to GitHub

1. Log into GitHub
2. Click the **+** button (top right) → **New repository**
3. Name it: `jaafar-appliances`
4. Make sure it says **Public**
5. Click **Create repository**
6. On the next screen, click **uploading an existing file**
7. Drag ALL the files from the `jaafar-site` folder you downloaded into the upload area
   - The folder structure should look like:
     ```
     admin/
       index.html
       config.yml
     content/
       gallery/
       services/
       settings/
     public/
       uploads/
     build.js
     package.json
     netlify.toml
     ```
8. Click **Commit changes**

---

## STEP 3 — Create a Netlify account

1. Go to **netlify.com**
2. Click **Sign up** → choose **Sign up with GitHub** (makes it easier)
3. Authorize Netlify to access your GitHub

---

## STEP 4 — Connect your GitHub repo to Netlify

1. In Netlify, click **Add new site** → **Import an existing project**
2. Choose **GitHub**
3. Find and click **jaafar-appliances** from the list
4. Netlify will auto-detect the settings from `netlify.toml`
5. Click **Deploy site**
6. Wait 1-2 minutes — Netlify will give you a URL like `random-name-123.netlify.app`

✅ Your site is now live!

---

## STEP 5 — Connect your custom domain (jaafar-appliances.com)

1. In Netlify, go to **Domain management** → **Add custom domain**
2. Type: `jaafar-appliances.com`
3. Netlify will show you **DNS records** to add
4. Log into wherever the domain was purchased (GoDaddy, Namecheap, etc.)
5. Go to **DNS settings** for the domain
6. Delete old DNS records (the ones pointing to Webador)
7. Add the new records Netlify gives you
8. Wait up to 24 hours for the domain to switch over

---

## STEP 6 — Enable Netlify Identity (so Ali can log in)

1. In Netlify, go to **Site settings** → **Identity**
2. Click **Enable Identity**
3. Scroll down to **Registration** → set to **Invite only** (so only Ali can log in)
4. Scroll down to **Git Gateway** → click **Enable Git Gateway**

---

## STEP 7 — Invite Ali to the admin panel

1. Still in **Identity**, click **Invite users**
2. Enter Ali's email address
3. Ali will get an email — he clicks the link and sets a password
4. That's it. Ali can now log in at **jaafar-appliances.com/admin**

---

## What Ali sees in the admin panel

When Ali logs in at `/admin` he sees a simple dashboard with:

### 📸 "Our Work — Photos"
- **Add photo** — uploads from his phone or computer, writes a description, picks the appliance type and brand
- **Edit photo** — change the description or swap the image
- **Delete photo** — removes it from the site
- **Featured toggle** — makes a photo display larger in the grid

### 🔧 "Services"
- Add, edit, or remove service cards

### ⚙️ "Site Settings"
- **Contact & Business Info** — update phone number, service area
- **Reviews** — add new Google reviews, edit existing ones

After Ali saves any change, Netlify automatically rebuilds the site in about 60 seconds. The live website updates on its own.

---

## Ali's login instructions (send this to him)

```
To update your website:

1. Go to: jaafar-appliances.com/admin
2. Click "Login with Netlify Identity"
3. Enter your email and password
4. Click "Our Work — Photos" to add or remove job photos
5. Click the green "Publish" button when done
6. Your website updates automatically in about 1 minute
```

---

## Troubleshooting

**Site not building?**
- In Netlify, go to **Deploys** — click the failed deploy to see the error log

**Ali forgot his password?**
- In Netlify → Identity → find Ali's email → click **Send reset email**

**Domain not switching over?**
- DNS changes can take up to 48 hours. Check back the next day.

**Photos not showing after Ali uploads?**
- Make sure Ali clicked **Publish** (not just Save)
- Netlify takes ~60 seconds to rebuild after publishing

---

## Summary of costs

| Service | Cost |
|---|---|
| GitHub | Free forever |
| Netlify (Starter plan) | Free forever |
| Decap CMS | Free forever |
| Domain (jaafar-appliances.com) | Already paid — just point it to Netlify |

**Total ongoing cost: $0/month**