# GEMINI.md - Contesto del Progetto "Uccello Volante"

## 1. Panoramica del Progetto
**Nome:** Uccello Volante (o "Uccello di Fuoco" nel gioco)
**Tipo:** Gioco Mobile Ibrido (2D)
**Tecnologie:** 
- **Core:** HTML5, CSS3, JavaScript (Vanilla) - Tutto contenuto in un unico file principale.
- **Mobile Wrapper:** Capacitor (per generare l'app Android).
- **Asset:** Immagini e Audio gestiti localmente nella cartella `www`.

## 2. Utente
**Nome:** Karim
**Lingua Preferita:** Italiano
**Livello:** Base-Intermedio (Appassionato, vuole imparare a creare App).
**Obiettivo:** Creare e pubblicare il gioco su Android, imparando nel processo.

## 3. Struttura e File Chiave
Il progetto è strutturato come un'app web standard che viene "incapsulata" in un'app Android tramite Capacitor.

- **`www/index.html`**: **FILE PRINCIPALE**. Contiene Tutta la logica del gioco (JS), lo stile (CSS) e la struttura (HTML). Non ci sono file `.js` o `.css` separati per il codice sorgente.
- **`package.json`**: Gestisce le dipendenze (Capacitor) e gli script di avvio.
- **`capacitor.config.json`**: Configurazione di base di Capacitor (ID app: `com.jorge.ucellovolante`).
- **`android/`**: Cartella del progetto nativo Android (generata e gestita da Capacitor).
- **`promt.md`**: File contenente appunti, prompt precedenti e storico delle modifiche desiderate (es. fix delle bombe, livelli).

## 4. Comandi Utili (Workflow)

### Sviluppo Web (Test veloce)
Per testare il gioco nel browser:
*   Aprire il file `www/index.html` direttamente nel browser.
*   Oppure usare un server statico (se installato): `serve www` o `npx serve www`.

### Sviluppo Android (Build e Deploy)
Ogni volta che si modifica `www/index.html`, bisogna aggiornare il progetto Android:

1.  **Sincronizzare le modifiche:**
    ```bash
    npx cap sync
    ```
    *Copia i file da `www` dentro `android/`.*

2.  **Aprire Android Studio:**
    ```bash
    npx cap open android
    ```
    *Oppure usare lo script custom:* `npm run go_android`

## 5. Stato Attuale del Gioco
Il gioco è un "Endless Runner" verticale (o a scorrimento) diviso in **4 Livelli** con meccaniche diverse:
1.  **Livello 1:** Accumulare punti (3000). Schivare ostacoli.
2.  **Livello 2:** Salvare 3 pulcini portandoli ai nidi.
3.  **Livello 3:** Nutrire i pulcini raccogliendo vermi.
4.  **Livello 4:** Insegnare ai pulcini a volare (Meccaniche variate: "Collect & Guide" o "Rhythm").

### Modifiche Recenti / Problemi Aperti (da `promt.md`)
- L'utente ha segnalato di aver "perso" delle modifiche recenti relative a:
    - **Visibilità Bombe:** Renderle nere, rotonde e più visibili.
    - **Livello 4:** Varianti delle meccaniche di volo.
    - **Bug Fix:** Pulsante "Riprova".
- È presente un riferimento a un comando "resume" e a una lista di fix che l'utente vorrebbe ripristinare.

## 6. Convenzioni di Sviluppo
- **Codice:** Tutto in `www/index.html`. Usare commenti per separare CSS, HTML e JS.
- **Stile:** CSS moderno con variabili (`:root`).
- **Asset:** Immagini in `www/` o `www/immagini/`, Audio in `www/audio/`.
- **Git:** Usare messaggi di commit chiari (es. `npm run git_commit_push`).

---
*Questo file è generato automaticamente per fornire contesto all'agente AI.*
