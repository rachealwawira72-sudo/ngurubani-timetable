# Ngurubani Timetable: put it online and make an APK

This folder is a complete app. It works on any web host, installs from Chrome, and runs offline after the first visit.

Files: `index.html` (the app), `manifest.webmanifest`, `sw.js` (offline), and four icon files. Keep them together in one folder.

## Step 1. Put it online (pick one)

**Netlify Drop (easiest, no account needed to try)**
1. Unzip this package.
2. Open https://app.netlify.com/drop in a browser.
3. Drag the unzipped folder onto the page.
4. You get a link like `https://something.netlify.app`. Open it on your phone to check.

**GitHub Pages**
1. Create a GitHub account and a new public repository.
2. Upload all the files to it.
3. In the repository go to Settings, then Pages, choose the main branch and the root folder, and save.
4. Your link is `https://YOUR-NAME.github.io/REPOSITORY-NAME/`.

**Cloudflare Pages** works the same way: create a project, upload the folder, get a link.

## Step 2. Install it on a phone without an APK

Open the link in Chrome on Android, tap the three-dot menu, then **Install app** (or **Add to Home screen**). On iPhone use Safari, tap Share, then **Add to Home Screen**. The app then opens full screen and works without internet.

## Step 3. Make the APK

1. Go to https://www.pwabuilder.com
2. Paste your hosted link and tap **Start**.
3. When it reports on the app, choose **Package for stores**, then **Android**.
4. Download the package. It contains an `.apk` you can share directly (for example on WhatsApp) and an `.aab` file for the Play Store.
5. Keep the signing key file that comes with the package somewhere safe. You need it to publish updates.

Phones will ask to allow installing from unknown sources the first time you install an APK shared outside the Play Store. Publishing on the Play Store needs a Google Play developer account, which has a one-time fee.

PWABuilder's screens change from time to time. If a button is named differently, look for the Android packaging option.

## Loading your real teachers and lessons

In the app open the **Lessons** tab and use **Import from Excel**.

1. Make a sheet with one row for each teacher, subject and class. Columns: **Teacher** (your code, such as 5 or T5), **Subject**, **Class** (such as 7 Pink or 4W) and **Lessons** a week. You can add **Name** and **Days off** (for example Mon Fri).
2. Save it as CSV (in Excel: File, Save As, CSV), then tap **Choose CSV file**. Or copy the cells in Excel and tap **Paste from Excel**.
3. Check the summary the app shows. It lists rows it could not read and classes that would not fill their week. Tap **Import**, then generate the timetable.

The **Template** and **Current lessons** buttons give you a starting sheet. Subject short forms such as Maths, CRE, PE and PTS are understood.

## The whole-school master timetable

On the **Timetable** tab choose **School**. Every class is a row and the lesson periods run across, with junior classes and primary classes in their own groups and their own start times. Pick a day or **Week**, or highlight one teacher to see everywhere they teach. Tap a class name to open that class.

To put it on the wall, tap **Save for printing**. You get a file that opens in your browser with one page for each day. Press Ctrl+P and print on A3 landscape (or A4 landscape with Fit to page). **Save this one** gives an Excel-ready file of the whole week.

## Things to know

- All teachers, lessons and timetables are saved inside each phone's browser or app. They are not shared between phones. Use **Backup and restore** on the Generate tab to move your work to another device. The **Save** buttons on the Timetable tab download Excel-ready files to send to staff.
- Opening the app in Chrome and opening the installed APK are two separate stores. Do your setup in one place, then restore a backup in the other if needed.
- To release an update, replace the files on your host. In `sw.js`, raise the number in `ngurubani-timetable-v3` (to v4, and so on) so phones fetch the new version. Installed phones pick it up on the next open when they are online.
- The app loads its fonts from Google Fonts when online and falls back to the phone's normal fonts when offline. Nothing else is fetched.
