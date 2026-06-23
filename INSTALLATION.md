# Connecter Claude à vos données DGStock

Ce guide vous permet de connecter **Claude** (Claude Code ou Cowork) à votre compte DGStock/DG-SALE, pour que Claude puisse consulter vos prospections, générer des rapports, etc. — **en lecture seule**, sans jamais accéder à vos données sensibles (mots de passe, utilisateurs, paramètres de compte).

## Prérequis

- Claude Code installé sur votre ordinateur. Si besoin : [voir la documentation d'installation](https://code.claude.com/docs/en/setup).
- Un compte DGStock actif (le même que vous utilisez sur [app.dgstock.org](https://app.dgstock.org)).

## Installation (2 commandes)

Ouvrez un terminal Claude Code et lancez :

```shell
/plugin marketplace add dgsoftware1334/dgstock-mcp-plugin
/plugin install dgstock@dgsoftware
```

Puis activez-le :

```shell
/reload-plugins
```

C'est terminé — aucune autre configuration n'est nécessaire.

## Première utilisation

La première fois que vous demandez à Claude quelque chose lié à vos prospections, **votre navigateur s'ouvrira automatiquement** sur une page de connexion DGStock. Connectez-vous avec votre email et mot de passe habituels — **directement dans cette page**, jamais dans la conversation avec Claude.

Une fois connecté, vous pouvez fermer l'onglet et revenir à Claude : la connexion est mémorisée automatiquement (renouvelée en silence pendant 30 jours — vous n'aurez pas besoin de vous reconnecter à chaque fois).

## Exemples de demandes à essayer

```text
Donne-moi un rapport des prospections de cette semaine.

Liste mes prospections en attente, avec leur état actuel.

Combien de prospections expirées ai-je actuellement ?
```

## Sécurité — ce que vous devez savoir

- **Lecture seule** : Claude ne peut ni créer, ni modifier, ni supprimer de données via ce connecteur.
- **Aucun accès aux données sensibles** : utilisateurs, mots de passe, paramètres de compte sont totalement inaccessibles par ce connecteur, par conception.
- **Votre mot de passe ne transite jamais par Claude** : il est saisi uniquement sur la page de connexion officielle DGStock, dans votre navigateur.
- **Le jeton d'accès est stocké uniquement sur votre ordinateur** (`~/.dgstock-mcp/credentials.json`), jamais partagé.

## Problèmes courants

**Le navigateur ne s'est pas ouvert automatiquement** : recopiez l'URL affichée dans le terminal et ouvrez-la manuellement.

**"Erreur 401" ou "non autorisé"** : votre session a peut-être expiré au-delà de 30 jours. Refaites une demande à Claude, le navigateur se rouvrira pour une nouvelle connexion.

**Besoin d'aide** : contactez le support DGSOFTWARE.
