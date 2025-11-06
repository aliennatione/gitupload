# Guida Completa

## Panoramica

**git-upload-anything** è uno strumento CLI che ti permette di caricare facilmente file e cartelle su GitHub, GitLab e Forgejo. Può essere utilizzato per creare nuovi repository o aggiornare quelli esistenti.

## Comandi e Opzioni

### --source
Specifica il percorso del file o della cartella da caricare.

```bash
--source ./path/to/folder
--source ./myarchive.zip
````

### --repo

Specifica il nome del repository da creare o aggiornare.

```bash
--repo MyRepo
```

### --platform

Specifica la piattaforma Git: `github`, `gitlab`, `forgejo`.

```bash
--platform github
```

### --private

Rendi il repository privato.

```bash
--private
```

### --force-update

Forza l'aggiornamento del repository esistente.

```bash
--force-update
```

### Esempi di utilizzo

1. **Creazione di un nuovo repository su GitHub**:

   ```bash
   git-upload-anything --source ./myapp.zip --repo MyRepo --platform github --private
   ```

2. **Aggiornamento di un repository esistente su GitLab**:

   ```bash
   git-upload-anything --source ./myapp.zip --repo MyRepo --platform gitlab --force-update
   ```

## Contributi

Le modifiche e i miglioramenti sono benvenuti. Apri una **pull request** per contribuire.

````