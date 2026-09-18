JTerra Property Group enquiry portal
A single-page enquiry form. The page is hosted on GitHub Pages. Enquiries are saved as rows in a Google Sheet, which can be downloaded at any time as Excel or CSV (File > Download).
Files
`index.html`  the portal (all styling and script inside one file)
`Code.gs`     the Google Apps Script that receives enquiries and writes them to the Sheet
`logo.svg`    not included. Add the JTerra logo with this exact name and it appears automatically. For a PNG, change `src="logo.svg"` in index.html.
Setup
Create the Sheet. In Google Drive create a new Google Sheet, for example "JTerra enquiries". Use the Google account that should own the enquiry data.
Add the script. In the Sheet open Extensions > Apps Script, delete the sample code, paste in the contents of `Code.gs`, and save. Optional: set `NOTIFY_EMAIL` to get an email for each enquiry.
Deploy it. Deploy > New deployment > type "Web app". Execute as: Me. Who has access: Anyone. Authorise when asked, then copy the web app URL (it ends in `/exec`). Open `index.html`, find `var ENDPOINT = "";` and paste the URL between the quotes.
Create the repo. On github.com create a new public repository. Upload `index.html`, `README.md` and `logo.svg`. `Code.gs` does not need to be in the repo.
Turn on Pages. Settings > Pages > Source: "Deploy from a branch" > Branch: main, folder: / (root) > Save. After a minute or two the site is live at `https://<username>.github.io/<repo>/`.
Test. Send one enquiry and confirm a row appears in the Sheet.
Notes
If the script is edited later, use Deploy > Manage deployments > Edit > New version. The URL stays the same.
A custom domain such as `enquire.jterrapropertygroup.com.au` can be set under Settings > Pages > Custom domain.
Brand colours sit in the `:root` block at the top of `index.html`.
The form has a hidden honeypot field to filter basic bots. The endpoint URL is visible in the page source, as with any public form, so some spam is possible.
