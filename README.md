# git-upload-anything

Uno strumento CLI robusto e versatile per caricare e gestire facilmente file e cartelle su diverse piattaforme Git.

## Descrizione

`git-upload-anything` è uno strumento da riga di comando (CLI) progettato per semplificare il processo di caricamento di file o intere cartelle su piattaforme di hosting Git come GitHub, GitLab e Forgejo. Il progetto è un repository completo che include non solo il codice dello script principale, ma anche una documentazione dettagliata e una configurazione di GitHub Actions per pubblicare automaticamente la documentazione su GitHub Pages. Il codice è ben organizzato, pronto all'uso e mira a fornire un'esperienza utente efficiente e automatizzata per sviluppatori e utenti.

## Funzionalità Principali

*   **Multi-piattaforma**: Supporta il caricamento su GitHub, GitLab e Forgejo.
*   **Gestione Account**: Possibilità di gestire e cambiare account (es. GitHub) tramite un'opzione dedicata.
*   **Autenticazione Flessibile**: Supporta l'autenticazione tramite strumenti CLI (GitHub CLI, GitLab CLI) e token di accesso personale (Forgejo).
*   **Caricamento Flessibile**: Permette il caricamento diretto di singole cartelle o file ZIP.
*   **Creazione e Aggiornamento Repository**: Capacità di creare nuovi repository pubblici o privati, e di aggiornare repository esistenti con l'opzione di forzare l'aggiornamento.
*   **Gestione Automatica Dipendenze**: Rileva e installa automaticamente le dipendenze necessarie (`git`, `curl`, `unzip`, `gh`, `glab`, `sudo`) su vari sistemi operativi (Termux, Debian/Ubuntu, Arch, Fedora, macOS).
*   **Automazione CLI**: Offre flag da riga di comando per un'automazione completa delle operazioni di caricamento.
*   **Inizializzazione Git Automatica**: Inizializza automaticamente un repository Git locale se non presente e crea un commit iniziale.
*   **Pulizia Opzionale**: Possibilità di rimuovere file temporanei dopo il caricamento per mantenere pulito l'ambiente di lavoro.
*   **Logging Chiaro**: Fornisce un feedback chiaro e dettagliato sulle operazioni in corso.

## Tecnologie Utilizzate

*   **Script Core**: `Bash`
*   **Strumenti di Base**: `git`, `curl`, `unzip`, `sudo`
*   **CLI per Piattaforme Git**: `gh` (GitHub CLI), `glab` (GitLab CLI)
*   **Piattaforme Supportate**: GitHub, GitLab, Forgejo
*   **Documentazione**: `MkDocs`, `Material for MkDocs` (tema), `Python`
*   **Integrazione Continua/Deployment**: `GitHub Actions` (per la pubblicazione della documentazione su GitHub Pages)

## Struttura del Progetto

Il repository è strutturato per una chiara organizzazione del codice, della documentazione e della configurazione CI/CD:

```
git-upload-anything/
│
├── .github/
│   ├── workflows/
│   │   └── gh-pages.yml         # GitHub Actions workflow per pubblicare su GitHub Pages
│
├── docs/
│   ├── index.md                 # Pagina principale della documentazione
│   └── guide.md                 # Guida dettagliata all'uso e alle opzioni avanzate
│
├── src/                         # Contiene il codice sorgente dello script
│   └── git-upload-anything      # Lo script Bash principale del progetto
│
├── .gitignore                   # Definisce i file e le cartelle da ignorare da Git
├── LICENSE                      # Il file della licenza del progetto
├── README.md                    # Questo file README
└── setup.sh                     # Script di setup per facilitare l'installazione del progetto (contenuto non specificato)
```

## Installazione e Utilizzo

### Prerequisiti

Assicurati di avere installati sulla tua macchina i seguenti strumenti: `git`, `curl`, `unzip`, `gh` (GitHub CLI), `glab` (GitLab CLI) e `sudo`. Lo script tenterà di installare le dipendenze mancanti.

### Installazione

1.  **Clona il repository**:
    ```bash
    git clone https://github.com/yourusername/git-upload-anything.git
    cd git-upload-anything
    ```
2.  **Rendi lo script eseguibile**:
    ```bash
    chmod +x src/git-upload-anything
    ```
    Puoi anche spostare lo script in una directory inclusa nel tuo `PATH` (es. `/usr/local/bin`) per renderlo accessibile globalmente:
    ```bash
    sudo mv src/git-upload-anything /usr/local/bin/
    ```
    _Nota_: Un file `setup.sh` è presente nella struttura del progetto per facilitare l'installazione, ma i suoi passaggi specifici non sono stati forniti. I passaggi manuali sopra sono un'alternativa valida.

### Autenticazione

Prima di caricare, assicurati di essere autenticato sulle piattaforme desiderate:

*   **GitHub**: Autenticati tramite GitHub CLI:
    ```bash
    gh auth login
    ```
*   **GitLab**: Autenticati tramite GitLab CLI:
    ```bash
    glab auth login
    ```
*   **Forgejo**: Usa un token di accesso personale. Assicurati che la variabile d'ambiente `$FORGEJO_TOKEN` sia impostata con il tuo token.

### Esempi di Utilizzo

Lo script `git-upload-anything` accetta diverse opzioni per personalizzare il caricamento.

*   **Caricare un file ZIP su un nuovo repository privato su GitHub**:
    ```bash
    git-upload-anything --source ./myapp.zip --repo MyRepo --platform github --private
    ```
*   **Caricare una cartella su un repository esistente su GitLab, forzando l'aggiornamento**:
    ```bash
    git-upload-anything --source ./myproject-folder --repo ExistingProject --platform gitlab --force-update
    ```
*   **Caricare su Forgejo con un account specifico e pulire i file temporanei**:
    ```bash
    git-upload-anything --source ./data.zip --repo DataBackup --platform forgejo --account myforgejouser --cleanup
    ```
*   **Mostrare l'aiuto per tutte le opzioni**:
    ```bash
    git-upload-anything --help
    ```

Per una guida più dettagliata su tutte le opzioni e gli scenari d'uso, consulta la [documentazione completa](docs/guide.md).

## Contribuire

Siamo entusiasti di accogliere contributi per migliorare `git-upload-anything`! Se desideri contribuire, ecco come puoi fare:

*   **Segnalare Bug o Richiedere Funzionalità**: Apri una [issue](https://github.com/yourusername/git-upload-anything/issues) nel repository per segnalare bug, suggerire nuove funzionalità o porre domande.
*   **Proporre Modifiche**: Le modifiche e i miglioramenti sono sempre benvenuti. Apri una [pull request](https://github.com/yourusername/git-upload-anything/pulls) con le tue modifiche.

## Licenza

Questo progetto è distribuito sotto la licenza MIT. Per maggiori dettagli, consulta il file [LICENSE](LICENSE) nella root del repository.
