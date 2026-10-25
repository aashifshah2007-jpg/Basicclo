# BASEIC store: Netlify + Google Sheet

## 1. Put the site on Netlify
Go to app.netlify.com, choose "Add new site", then "Deploy manually", and drag this whole folder in (unzipped). You get a live link in about a minute.

## 2. Connect the Google Sheet (orders, emails, dashboard)
1. Create a new Google Sheet. Open Extensions > Apps Script and paste in `apps-script/Code.gs`.
2. Pick `setup` in the function menu and press Run. Accept the permissions. It creates the Orders, Items, Dashboard and Settings tabs.
3. Deploy > New deployment > Web app. Execute as "Me", access "Anyone". Copy the Web app URL.
4. In `index.html`, find `const CFG=` and fill in `SCRIPT_URL` (the URL), `KEY` (same as Settings!B2 in the sheet), `WA` (shop WhatsApp, like 97798XXXXXXXX), `EMAIL` and `SHEET_URL` (the sheet's link). Upload the folder to Netlify again.

## 3. Everyday use
- Order alerts go to the emails in the sheet's Settings tab, cell B1. Edit it any time, or use the BASEIC menu > Add an alert email.
- BASEIC menu > Share this sheet with... gives other people access to the orders and the Dashboard tab.
- Check the money in the wallet or bank, then set the order's Status (Orders tab, column Q) to Verified or Not verified. You also get an email when a status changes.
- Payment QR: replace `img/qr.jpg` with the shop's real merchant QR (same file name) and redeploy.
- Products, prices and descriptions are in the `P` list and `D` text inside `index.html`.

Screenshots are saved in a Google Drive folder, with a link in the sheet. A screenshot is not proof of payment, so always verify the transaction.
