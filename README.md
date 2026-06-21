# anna-sito

Sito statico di supporto per l'app iOS **Anna**, un'app di respirazione guidata per i momenti di forte stress. Tutti i contenuti dell'utente (frasi, promemoria, foto, sessioni) restano in locale sul dispositivo tramite SwiftData — nessun account, nessun server, nessun tracciamento.

Il sito serve in primo luogo a soddisfare i requisiti della App Review di Apple (Support URL e Privacy Policy URL), oltre a presentare l'app.

Nessuna dipendenza, nessuna build: solo HTML/CSS/JS statico. Unica risorsa esterna sono i font Google (Fraunces + Inter).

## Struttura
```
index.html      → home / presentazione (hero, 3 feature, disclaimer)
privacy.html    → informativa sulla privacy
support.html    → contatto supporto + FAQ
css/style.css   → stili (palette salvia/lavanda, layout responsive)
js/breathe.js   → cue testuale "Inspira/Espira" sincronizzato col cerchio
```

## Dettagli

- **Lingua**: italiano (`lang="it"`).
- **Home**: cerchio che pulsa con animazione `breathe` (ciclo 10s); `breathe.js` alterna il testo "Inspira" (4s) / "Espira" (6s). Tre feature: *Respiro guidato*, *Le tue cose*, *Senza fretta*. Disclaimer: Anna non è un dispositivo medico.
- **Privacy / Supporto**: contatto via `g_scappaticci@icloud.com` (in chiaro su entrambe le pagine). Titolare: Giuseppe Scappaticci.
- **Accessibilità**: rispetta `prefers-reduced-motion` (disattiva animazione e scroll fluido; il cue resta "Respira con calma"), `aria-label` sulle nav, focus-visible su link e bottoni, colori testo AA-safe.
- **Responsive**: griglia feature a 1 colonna e header/footer in colonna sotto i 720px.

## Pubblicare su GitHub Pages

1. Crea un repo (es. `anna-sito`) e fai push di questi file nella **root** del branch `main`:
   ```bash
   cd anna-sito
   git init
   git add .
   git commit -m "Sito Anna: home, privacy, supporto"
   git branch -M main
   git remote add origin https://github.com/TUOUSER/anna-sito.git
   git push -u origin main
   ```
2. Su GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, cartella `/ (root)`. Salva.
3. Dopo qualche minuto il sito sarà live su:
   `https://TUOUSER.github.io/anna-sito/`

## URL da inserire in App Store Connect

- **Privacy Policy URL**: `https://TUOUSER.github.io/anna-sito/privacy.html`
- **Support URL**: `https://TUOUSER.github.io/anna-sito/support.html`
- **Marketing URL** (opzionale): `https://TUOUSER.github.io/anna-sito/`

## Prima di pubblicare
- Verifica che `g_scappaticci@icloud.com` sia l'indirizzo che vuoi rendere pubblico (compare in chiaro sia su Privacy che su Supporto).
- Se in futuro l'app introduce HealthKit, sincronizzazione cloud o terze parti, **aggiorna `privacy.html`** di conseguenza — è un documento che deve restare vero, non solo presente.
- Apri `index.html` localmente nel browser per un'anteprima veloce prima del push.
