# CurAuto

Web app per prenotazioni online CurAuto — lavaggio, detailing e pulizia interni auto.

## Stack
- Frontend statico HTML/CSS/JavaScript, pubblicabile con GitHub Pages.
- Supabase per servizi, orari, giorni di chiusura, prenotazioni e autenticazione amministrativa.
- Le disponibilità vengono lette tramite `get_available_slots`; le prenotazioni sono confermate tramite `create_appointment`, che ricontrolla lo slot lato database per prevenire doppie prenotazioni.

## Pubblicazione
1. Apri **Settings → Pages** nel repository GitHub.
2. In **Build and deployment**, seleziona **Deploy from a branch**.
3. Scegli branch `main` e cartella `/ (root)`, poi salva.
4. Attendi il completamento del deployment in **Actions**.

## Prima del lancio pubblico
- Inserire numero WhatsApp e recapiti ufficiali in `site_settings`.
- Verificare orari, durate e servizi nel database.
- Creare l'utente Supabase Auth amministratore e inserire il suo UUID in `admin_profiles`.
- Pubblicare un'informativa privacy completa e configurare le modalità di gestione delle richieste di cancellazione.
- Eseguire test reali di prenotazione e sovrapposizione degli slot.
- Configurare eventuali notifiche di conferma al cliente (email/WhatsApp); al momento la conferma è mostrata nella web app.

## Dati pubblici
Il frontend usa esclusivamente la chiave publishable di Supabase. Non inserire mai service-role keys, password o altri segreti nel repository.
