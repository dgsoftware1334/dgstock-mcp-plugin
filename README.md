# dgstock-mcp-plugin

Marketplace de plugins Claude Code pour DGSOFTWARE — contient le connecteur **DGStock** (accès lecture seule aux prospections, authentification automatique).

## Pour les utilisateurs — installer le connecteur

```shell
/plugin marketplace add dgsoftware1334/dgstock-mcp-plugin
/plugin install dgstock@dgsoftware
/reload-plugins
```

C'est tout. Aucun mot de passe ni token à saisir dans Claude — la première utilisation ouvre votre navigateur pour vous connecter une seule fois.

Voir [INSTALLATION.md](INSTALLATION.md) pour le guide complet destiné aux utilisateurs finaux.

## Pour les mainteneurs DGSOFTWARE — mettre à jour le connecteur

Le code source du serveur (TypeScript) vit dans un projet séparé : `dgstock-mcp` (développement). Ce repo ne contient que le **bundle compilé** (fichier autonome, toutes dépendances incluses).

Pour publier une nouvelle version :

1. Modifier le code source dans le projet de dev.
2. Lancer `npm run bundle` → génère `dist/dgstock-mcp.bundle.mjs`.
3. Copier ce fichier dans `dgstock-mcp/server/dgstock-mcp.bundle.mjs` de ce repo.
4. Incrémenter `version` dans `dgstock-mcp/.claude-plugin/plugin.json` (sinon les utilisateurs ne reçoivent pas la mise à jour).
5. Commit + push.

Les utilisateurs reçoivent la mise à jour automatiquement (marketplace officiel a l'auto-update activé par défaut), ou via `/plugin marketplace update dgsoftware`.

## Structure

```
dgstock-mcp-plugin/
├── .claude-plugin/
│   └── marketplace.json          # catalogue (référence le plugin ci-dessous)
├── dgstock-mcp/                  # le plugin
│   ├── .claude-plugin/
│   │   └── plugin.json           # manifest (nom, version, auteur)
│   ├── .mcp.json                 # config du serveur MCP (chemin vers le bundle)
│   └── server/
│       └── dgstock-mcp.bundle.mjs  # serveur compilé, autonome (aucune dépendance externe)
└── INSTALLATION.md                # guide utilisateur final
```
