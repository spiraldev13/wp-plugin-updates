  ## Objectif

  Permettre à WordPress de détecter et proposer les mises à jour dans le back-office, comme pour un plugin classique, sans exposer le dépôt
  source privé.
  ## Structure du dépôt
  ```text
  ├── ultimate-shanks/
  │   ├── update.json
  │   └── ultimate-shanks.zip
  │   ├── update.json
  └── plugin-3/
      ├── update.json
      └── plugin-3.zip

  ## Convention de nommage

  - 1 dossier par plugin = son slug WordPress
  - ZIP = <slug>.zip
  - Manifest = update.json

  ## Format attendu de update.json

  Exemple pour ultimate-shanks :

  {
    "name": "Ultimate Shanks",
    "slug": "ultimate-shanks",
    "plugin": "ultimate-shanks/ultimate-shanks.php",
    "version": "1.4.0",
    "tag": "v1.4.0",
    "download_url": "https://raw.githubusercontent.com/spiraldev13/wp-plugin-updates/main/ultimate-shanks/ultimate-shanks.zip",
    "details_url": "https://github.com/spiraldev13/ultimate-shanks",
    "tested": "6.7",
    "requires": "6.0",
    "requires_php": "7.4",
    "last_updated": "2026-02-08T00:00:00Z"
  }

  ## URL à utiliser côté plugin WordPress

  Pour le plugin ultimate-shanks :

  https://raw.githubusercontent.com/spiraldev13/wp-plugin-updates/main/ultimate-shanks/update.json

  ## Process de release (manuel)

  1. Générer le ZIP du plugin avec le bon dossier racine (ultimate-shanks/).
  2. Mettre à jour ultimate-shanks/update.json avec la nouvelle version.
  3. Remplacer ultimate-shanks/ultimate-shanks.zip.
  4. Commit + push sur main de ce dépôt.
  5. WordPress verra la mise à jour au prochain check.

  ## Support multi-plugins

  Ce dépôt est conçu pour héberger les mises à jour de plusieurs plugins :

  - 1 plugin = 1 dossier
  - 1 update.json + 1 ZIP par plugin
  - chaque plugin WordPress pointe vers son propre update.json

  ## Sécurité

  - Ce dépôt est public : ne jamais y stocker de secrets.
  - Publier uniquement des artefacts de release (ZIP + manifest).
  - Le code source privé reste dans son dépôt privé.
