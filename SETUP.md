# Task Organizer: Setup

You set this up once. After that, the app opens from one web address on your PC and your phone, and it saves to **TaskOrganizer.json** in your own Google Drive.

To try it first, double-click `index.html` on your PC. It runs in "Local only" mode until you connect Drive.

---

## Part 1: Put the app online (GitHub Pages, free, about 5 min)

1. Sign in at github.com. Create a free account if you don't have one.
2. Click **+ → New repository**. Name it `tasks`, set it to **Public**, and click **Create repository**.
3. Click **uploading an existing file** and drag in all six files:
   `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `SETUP.md`. Click **Commit changes**.
4. Go to **Settings → Pages**. Under *Branch*, pick **main** and **/ (root)**, then click **Save**.
5. After about a minute, the page shows your address: `https://YOUR-USERNAME.github.io/tasks/`

Only the app's code is public. Your tasks are stored in your Drive, not on GitHub.

## Part 2: Let the app use your Drive (Google Cloud, about 10 min)

1. Go to **console.cloud.google.com** and sign in with the Google account whose Drive you want to use.
2. In the project picker at the top, choose **New Project**, name it `Task Organizer`, and click **Create**. Then select it.
3. **Turn on the Drive API:** go to *APIs & Services → Library*, search **Google Drive API**, and click **Enable**.
4. **Consent screen:** go to *APIs & Services → OAuth consent screen* (it may be called *Google Auth Platform → Branding*).
   - App name: `Task Organizer`. Use your email for the support and developer contact fields.
   - Audience / User type: **External**.
   - Under **Test users**, add your own Gmail address.
   - You can leave it in **Testing** mode. Only you will use it.
5. **Client ID:** go to *APIs & Services → Credentials → + Create credentials → OAuth client ID*.
   - Application type: **Web application**
   - **Authorized JavaScript origins**: add `https://YOUR-USERNAME.github.io` (no `/tasks`, no trailing slash)
   - Click **Create**, then copy the **Client ID**. It ends in `.apps.googleusercontent.com`.

## Part 3: Connect

1. Open `https://YOUR-USERNAME.github.io/tasks/` on your PC.
2. Tap **⚙**, paste the Client ID, and tap **Connect Drive**.
3. Google warns you that the app isn't verified. That's expected for a personal app. Click **Continue** and allow access.
   The app can only see files it creates. It cannot read the rest of your Drive.
4. Do the same on your phone. Paste the same Client ID and connect. It loads the tasks from Drive.

**Add it to your phone's home screen** so it works like an app:
- iPhone (Safari): Share → **Add to Home Screen**
- Android (Chrome): ⋮ menu → **Add to Home screen** / **Install app**

---

## Day-to-day

- **Sync badge** (top right):
  - *Synced*: Drive matches what's on screen.
  - *Tap to sync*: tap it once each time you open the app. Google needs a tap to sign in.
  - *Offline*: changes are kept on the device and upload when you reconnect.
- Every change saves to Drive about a second after you stop typing.
- When you switch devices, the app pulls the latest copy from Drive. If both devices changed it, the app asks which version to keep.
- **⚙ → Export backup** downloads a copy of all your tasks.

## How it works (matches your outline)

| Your outline | In the app |
|---|---|
| Focus tab with tasks from other tabs, movable | Tab 1, can't be deleted. Tasks show which tab they came from, and **↩ Back** returns them there. |
| Tabs 2–3 user-defined, right-click to edit/delete | Right-click on the PC, **long-press** on the phone → Rename / Delete |
| Add new tab | **+ Add tab** at the bottom of the tab list |
| Button top-left to add a Task box | **+ Task**. New tasks appear at the top. |
| Task holds 200 characters, note or journal | Multi-line box with a 200-character limit and a counter |
| Task movable | Drag the **⠿** handle to reorder, or drop it onto a tab on the left to move it there |
| Auto-date | The date and time are stamped when the task is created |
| **+** square adds an indented Step box (100 characters) | Pressing Enter in a step adds the next step |
| Collapse all steps with one button | **Collapse/Expand** at the top does the whole page. The **▾ n** on each task does just that task. |
| Send task and its steps to Focus | **➜ Focus** on each task |
| Checkbox to mark a task cleared | ☐ to the left of each task and step: checked items are struck through and stay put. **Clean up (n)** at the top deletes the checked tasks on that page. |
| Star Wars look | Black starfield with aqua gothic lettering |
