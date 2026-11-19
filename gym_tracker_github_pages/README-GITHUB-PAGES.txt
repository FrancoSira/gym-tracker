GYM TRACKER – PACCHETTO GITHUB PAGES

FILE
- index.html: applicazione
- config.js: URL Supabase e chiave publishable
- manifest.webmanifest: impostazioni PWA
- sw.js: service worker
- .nojekyll: evita l'elaborazione Jekyll

PUBBLICAZIONE
1. Crea un repository GitHub PUBLIC (GitHub Free richiede un repository pubblico per Pages).
2. Carica direttamente nella ROOT del repository tutti i file di questo pacchetto, inclusi i file nascosti se il browser li mostra.
3. In Settings > Pages seleziona Deploy from a branch, branch main, cartella /(root), poi Save.
4. Attendi il completamento della pubblicazione. L'indirizzo sarà https://NOMEUTENTE.github.io/NOME-REPOSITORY/.

ATTENZIONE PRIVACY
GitHub Pages è un sito pubblico. Anche se il repository fosse privato (nei piani che lo consentono), il sito Pages resta pubblico. Il programma di allenamento è incorporato nell'HTML e quindi visibile a chiunque apra il sorgente. La chiave sb_publishable è una chiave pubblica, ma le tabelle Supabase devono avere RLS correttamente configurata. Non caricare mai sb_secret o service_role.

SUPABASE
L'app usa la tabella user_workout_data con user_id (uuid), data (jsonb), updated_at (timestamptz). Prima di usare la sincronizzazione, verificare che la tabella esista, RLS sia attiva e le policy limitino ogni utente autenticato alla propria riga (user_id = auth.uid()).
