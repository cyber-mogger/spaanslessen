Spaans Roermond site — Netlify deployment

1) Zet deze map in GitHub

cd "c:\Users\LPadr\Documents\jetson nano AI project\spaansroermond-site"
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin <GIT_URL>
git push -u origin main

2) Voeg de site toe aan Netlify
- Ga naar https://app.netlify.com
- Log in of maak een account aan
- Klik op "Add new site" → "Import from Git"
- Koppel je GitHub-account en kies de repository met de site
- Stel de build settings in:
  Build command: (leeg)
  Publish directory: .
- Klik op "Deploy site"

3) Koppel je TransIP-domein
- Ga naar je site in Netlify
- Site settings → Domain management → Add custom domain
- Voeg je domein toe, bijvoorbeeld spaansroermond.nl
- Kies voor DNS beheren bij TransIP (geen Netlify DNS nodig)

4) Voeg DNS-records toe bij TransIP
- Log in bij TransIP
- Selecteer je domein → DNS
- Voeg de volgende records toe:
  A record: Host @, Waarde 75.2.60.5
  A record: Host @, Waarde 99.83.190.102
  CNAME record: Host www, Waarde <jouw-site>.netlify.app

5) Laat Zoho Mail bestaan
- Bewaar je Zoho MX- en SPF/TXT-records
- Voeg alleen de Netlify webrecords toe

6) Controleer HTTPS
- Netlify controleert de DNS-status
- Wanneer alles goed is, staat HTTPS aan

Extra tip
- Je logo kleuren #A72C2C en #2D3E96 komen terug in knoppen, koppen en accentblokken. Je site heeft nu een moderne, speelse Spaanse stijl die goed past bij jouw branding.