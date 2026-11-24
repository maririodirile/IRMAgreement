# ED Agreement Signer

A static page. No build step and no server.

## Deploy on Vercel
1. Put this folder in a GitHub repository (or use the Vercel CLI: run `vercel` inside the folder).
2. In Vercel choose **Add New > Project**, import the repository, and leave every setting as default.
3. Deploy. Your link is `https://<your-project>.vercel.app/`.

## Deploy on GitHub Pages
1. Push these files to the root of a repository.
2. Go to **Settings > Pages**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
3. Your link is `https://<user>.github.io/<repo>/`.

## Create a link for each participant
Open `<your link>?admin`, fill in the college, company, registration number and owner name, then copy the link and send it to the participant. They only need to check their details, draw a signature and tap **Sign and download PDF**. The signed PDF downloads to their device.

Link parameters: `c` (umf, ewc, tnc, fb, wc), `n` company, `r` registration number, `o` owner, `e` email, `dur` duration wording.

## Optional: also send the PDF to NBI
Create a Power Automate flow with **When an HTTP request is received**, paste its URL into `const API=""` near the bottom of `index.html`, and add **Send an email (V2)** with the attachment name `pdfFileName` and content `base64ToBinary(triggerBody()?['pdfBase64'])`. Leave `API` empty to only download.
