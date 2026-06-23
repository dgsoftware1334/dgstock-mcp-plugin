# Connecteur DGStock

Donne à Claude un accès **lecture seule** à vos prospections DGStock/DG-SALE, avec authentification automatique (aucun mot de passe ni token à saisir dans Claude).

## Première utilisation

La première demande liée à vos prospections ouvre automatiquement votre navigateur sur la page de connexion DGStock. Connectez-vous avec votre compte habituel — directement sur cette page, jamais dans la conversation. La connexion est ensuite mémorisée et renouvelée automatiquement pendant 30 jours.

## Exemples de demandes

```text
Donne-moi un rapport des prospections de cette semaine.
Liste mes prospections en attente, avec leur état actuel.
Combien de prospections expirées ai-je actuellement ?
```

## Sécurité

- Lecture seule — aucune création, modification ou suppression possible.
- Aucun accès aux utilisateurs, mots de passe ou paramètres de compte.
- Le mot de passe ne transite jamais par Claude.
- Le jeton d'accès est stocké uniquement sur votre ordinateur (`~/.dgstock-mcp/credentials.json`).
