# CoreChat

Plugin de gestion de chat complet pour PocketMine-MP 5

Auteur: zNsk0

## Fonctionnalites

### Commandes de moderation

- `/mute <joueur> [duree]` - Empeche un joueur de parler
  - Exemples: `/mute Player 30s`, `/mute Player 5m`, `/mute Player 1h`, `/mute Player 1d`
  - Sans duree = mute permanent
- `/unmute <joueur>` - Reactive un joueur mute
- `/clear` - Vide le chat pour tout le monde
- `/slowchat` - Active/desactive le mode lent (anti-spam)
- `/mutechat` - Verrouille/deverrouille completement le chat
- `/msg <joueur> <message>` - Envoie un message prive
- `/staffchat <message>` - Chat reserve au staff
- `/chatlogs [nombre]` - Affiche les derniers logs du chat

### Systeme anti-spam

- Detection automatique des messages repetes
- Blocage des majuscules abusives avec correction automatique
- Filtre de mots interdits configurable
- Mode lent avec delai personnalisable entre les messages

### Systeme de logs

Tous les evenements sont enregistres dans:
- Fichier texte (logs.txt)
- Base de donnees (SQLite ou MySQL)
- Webhooks Discord (optionnel)

Types de logs:
- Messages du chat
- Messages prives
- Messages staff
- Actions de moderation (mute, unmute, clear, etc.)
- Messages bloques (spam, mots interdits, majuscules)

### Systeme Anti Here
- Bloque le @here des joueurs non op.

### Webhooks Discord

Chaque type d'evenement peut avoir son propre webhook:
- chat - Messages normaux
- private-message - Messages prives
- staff-chat - Chat staff
- clear - Nettoyage du chat
- mute - Joueur mute
- unmute - Joueur unmute
- slowmode - Mode lent active/desactive
- chatlock - Chat verrouille/deverrouille
- spam - Messages bloques pour spam
- filter - Messages bloques pour mots interdits
- maj - Messages corriges pour majuscules

### Base de donnees

Support SQLite et MySQL pour la sauvegarde des logs.

Tables creees automatiquement:
- chat_logs - Historique des messages
- private_logs - Messages prives
- staff_logs - Messages staff
- action_logs - Actions de moderation
- mute_logs - Historique des mutes
- filter_logs - Messages bloques

## Permissions

### Commandes
- `corechat.mute` - Utiliser /mute
- `corechat.unmute` - Utiliser /unmute
- `corechat.clear` - Utiliser /clear
- `corechat.slowchat` - Utiliser /slowchat
- `corechat.mutechat` - Utiliser /mutechat
- `corechat.msg` - Utiliser /msg
- `corechat.staff` - Utiliser /staffchat
- `corechat.viewlogs` - Utiliser /chatlogs

### Bypass
- `corechat.bypass.mute` - Ignorer le chat verrouille
- `corechat.bypass.slowchat` - Ignorer le mode lent
- `corechat.bypass.spam` - Ignorer la detection de spam
- `corechat.bypass.maj` - Ignorer la correction des majuscules
- `corechat.bypass.filter` - Ignorer le filtre de mots interdits

## Configuration

### config.yml

```yaml
This plugin was created by Light Studio.
Do not copy, redistribute, or claim it as your own.

slowmode-delay: 3

database-type: "sqlite"

mysql-host: "localhost"
mysql-port: 3306
mysql-user: "root"
mysql-password: ""
mysql-database: "corechat"

webhooks:
  chat: ""
  private-message: ""
  staff-chat: ""
  clear: ""
  mute: ""
  unmute: ""
  slowmode: ""
  chatlock: ""
  spam: ""
  filter: ""
  maj: ""

save-logs-to-file: true

banned-words:
  - "exemple1"
  - "exemple2"
```

### Messages personnalisables

Tous les messages du plugin sont configurables dans le fichier config.yml.

## Dependances

- PocketMine-MP 5.0 ou superieur

## Support

Pour toute question ou probleme, mp sur discord znsk0.

## Licence

Tous droits reserves - zNsk0
