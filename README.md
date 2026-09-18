# JTerra Property Group enquiry portal

A single-page enquiry form hosted on GitHub Pages. Enquiries are saved as rows
in a Google Sheet, which can be downloaded as Excel or CSV (File > Download).

## Setup

1. In Google Drive, create a new Google Sheet, for example "JTerra enquiries".
2. In the Sheet open Extensions > Apps Script, delete the sample code, paste in
   the Code.gs script, and save.
3. Click Deploy > New deployment > Web app. Execute as: Me. Who has access:
   Anyone. Authorise, then copy the web app URL ending in /exec. In index.html
   find var ENDPOINT = ""; and paste the URL between the quotes.
4. Send one test enquiry and confirm a row appears in the Sheet.

## Notes

- Add a file named logo.svg to this repo and the logo appears automatically.
- Brand colours sit in the :root block at the top of index.html.
