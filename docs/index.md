# Documentazione di Git Upload Anything

Benvenuti nella documentazione ufficiale di **git-upload-anything**. Questo progetto è uno strumento CLI che consente di caricare facilmente file e cartelle su GitHub, GitLab e Forgejo.

## Funzionalità

- **Multi-piattaforma**: Supporta GitHub, GitLab, e Forgejo.
- **Gestione Account**: Possibilità di cambiare account tramite il flag `--account`.
- **Autenticazione**: Supporto per login tramite chiave SSH o token di accesso personale.
- **Supporto per ZIP**: Caricamento diretto di file ZIP.
- **Aggiornamenti Repository**: Supporta il forzamento dell'aggiornamento di repository esistenti.

## Configurazione

1. **Installazione delle dipendenze**:
   Segui le istruzioni di installazione riportate nel [README](../README.md).
   
2. **Autenticazione su GitHub**:
   ```bash
   gh auth login
````

3. **Creazione di un repository su GitHub**:

   ```bash
   git-upload-anything --source ./myapp.zip --repo MyRepo --platform github --private
   ```

4. **Aggiornamento di un repository**:

   ```bash
   git-upload-anything --source ./myapp.zip --repo MyRepo --platform github --force-update
   ```

## Supporto

Se hai domande o hai bisogno di assistenza, apri una **issue** nel repository.

````