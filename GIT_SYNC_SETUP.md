# Git Sync Setup pour Clawdbot Memory

**Status:** Token GitHub insuffisant pour création automatique

## Ce qui est déjà fait:
- ✅ Git repo initialisé dans ~/.clawdbot
- ✅ 21 fichiers commités

## Pour finaliser (manuel):

### Option A: Utiliser un repo existant
Si tu as déjà un repo GitHub pour ta mémoire:
```bash
cd ~/.clawdbot
git remote add origin https://github.com/ton-user/ton-repo.git
git push -u origin master
```

### Option B: Créer un repo manuellement
1. Aller sur https://github.com/new
2. Nom: `clawdbot-memory` ou `isaak-clawdbot-memory`
3. Description: "Clawdbot memory files sync with Lumen"
4. Public ou Private
5. Ne pas initializer avec README (repo vide)
6. Copier les commandes showes sur GitHub

### Option C: Mettre à jour le PAT
Le PAT actuel n'a pas les permissions `repo`. Pour corriger:
1. https://github.com/settings/tokens
2. Editer le token
3. Ajouter scope `repo`
4. Regenerer si nécessaire

## Sync Automatique (après setup)

Pour sync automatique à chaque mise à jour mémoire:
```bash
# Créer un script de sync
cat > ~/.clawdbot/scripts/sync-memory.sh << 'EOF'
#!/bin/bash
cd ~/.clawdbot
git add -A
git commit -m "Auto sync: $(date)" 2>/dev/null
git push origin master 2>/dev/null
EOF
chmod +x ~/.clawdbot/scripts/sync-memory.sh
```

## Utiliser avec Lumen

1. Une fois le repo GitHub créé et sync:
2. Aller sur https://lumen.note
3. Connecter avec GitHub
4. Selectionner le repo `clawdbot-memory`
5. Maintenant tu peux browse et edit tes memoria via Lumen UI!

---

*Setup guide créé le 2026-01-31*