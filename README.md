# SharedHealth

Plugin Paper (Minecraft Java 1.21.11) qui transforme la partie en mode **vie/faim partagées**.

## Compatibilité

- Paper 1.21.x (testé pour 1.21.11)
- Java 21

## Installation

1. Compiler le plugin (voir section Build) ou récuperer le `.jar` déjà compilé [ici](https://github.com/Shytoos/mc-sharedhealth/releases).
2. Copier le fichier `.jar` dans le dossier `plugins/` de ton serveur Paper.
3. Démarrer (ou redémarrer) le serveur.

## Utilisation (règles du mode)

Le plugin ne propose **aucune commande** : tout est automatique.

- Les PV sont partagés entre tous les joueurs connectés.
- La faim (food bar) est partagée.
- Les effets Régénération, Bonus de santé et Absorption sont synchronisés.
- La régénération est gérée pour éviter les cumuls abusifs (pas de stack multi-joueurs).
- Si un joueur meurt, tout le groupe meurt.
- À la mort partagée :
  - inventaires vidés (armure incluse),
  - coffres de l'End vidés,
  - drops de mort vidés,
  - objets au sol supprimés.
- Si un joueur était hors ligne pendant une mort partagée, à sa reconnexion il est resynchronisé au même état de progression (inventaire/coffre de l'End nettoyés).

## Build local

```bash
mvn -DskipTests clean package
```

Le jar est généré dans `target/`, par exemple :

- `sharedhealth-1.1.0.jar`

## Données persistées

Le plugin enregistre sa progression dans :

- `plugins/SharedHealth/shared-health.yml`
