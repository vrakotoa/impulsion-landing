# vero-rakoto.com — Site vitrine

Site Astro du programme Impulsion, un mastermind pour solopreneures.

## Structure

```
src/
├── components/     # Sections de la page (Header, Hero, FAQ, Footer...)
├── layouts/        # Layout principal (BaseLayout)
├── pages/          # Routes du site (index.astro)
├── styles/         # CSS global avec variables de design system
public/             # Assets statiques
```

## Commandes

| Commande | Action |
|----------|--------|
| `npm install` | Installer les dépendances |
| `npm run dev` | Lancer le serveur local (port 4321) |
| `npm run build` | Build production dans `dist/` |
| `npm run preview` | Prévisualiser le build local |

## Déploiement — Cloudflare Pages

### 1. Créer le repo GitHub

```bash
# Depuis le dossier du projet
git init
git add .
git commit -m "Initial commit"
# Créer un repo vierge sur github.com (sans README, sans .gitignore, sans licence)
git remote add origin git@github.com:VERO-RAKOTO/vero-rakoto.com-site.git
git branch -M main
git push -u origin main
```

### 2. Connecter Cloudflare Pages

1. Aller sur https://dash.cloudflare.com
2. Menu > Workers & Pages
3. Cliquer **Create application** > **Pages**
4. **Connect to Git**
5. Autoriser l'accès au repo `VERO-RAKOTO/vero-rakoto.com-site`
6. Configurer :

   | Champ | Valeur |
   |-------|--------|
   | Framework preset | `Astro` |
   | Build command | `npm run build` |
   | Build output directory | `dist` |
   | Root directory | (laisser vide) |
   | Node.js version | `20` |

7. Cliquer **Save and Deploy**

### 3. Déploiements automatiques

- Chaque push sur `main` déclenche un build et déploiement automatique
- Les preview deployments sont activés automatiquement pour les PRs

## Design System

Voir `DESIGN-SYSTEM.md` pour la palette, la typographie, les composants et les règles de création de pages.
