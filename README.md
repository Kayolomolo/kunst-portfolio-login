# Inlogdienst voor kunst-portfolio

Zorgt dat je op https://kayolomolo.github.io/kunst-portfolio/ kunt inloggen met
e-mail en wachtwoord. De GitHub-sleutel blijft geheim op Vercel en komt nooit
in de browser terecht. Deze dienst mag alleen `data.json` en foto's in `images/`
aanpassen.

## Eenmalige installatie

1. **GitHub-sleutel maken:** https://github.com/settings/personal-access-tokens/new
   - Repository access: **Only select repositories** → `kunst-portfolio`
   - Permissions → **Contents**: **Read and write**
   - **Generate token** en kopieer hem (begint met `github_pat_...`)

2. **Op Vercel importeren:** https://vercel.com/new → kies `kunst-portfolio-login` → **Import**.
   Klap **Environment Variables** open en voeg toe:
   - `ADMIN_EMAIL` = het e-mailadres waarmee je wilt inloggen
   - `ADMIN_PASSWORD` = je wachtwoord (kies een sterk wachtwoord)
   - `GITHUB_TOKEN` = de sleutel van stap 1

   Klik **Deploy**.

3. Het adres moet `https://kunst-portfolio-login.vercel.app` zijn. Is het anders?
   Pas dan `LOGIN_URL` bovenaan het script in `kunst-portfolio/index.html` aan.

Wachtwoord wijzigen: pas `ADMIN_PASSWORD` aan in Vercel → Settings → Environment
Variables, en doe daarna bij Deployments **Redeploy**.
