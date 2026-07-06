# Design System — vero-rakoto.com

## Palette

### Couleurs principales
| Token | Valeur | Usage |
|-------|--------|-------|
| `primary` | `#5F6B45` | Boutons CTA, accents sur fond clair, fonds de cartes before/after |
| `primary-dark` | `#4A5531` | Hover des éléments primary |
| `gold` | `#C6922E` | Accents secondaires, icônes check, bordures mise en avant |
| `rose-500` | `#D96C8A` | Accents tertiaires, badges, pulse dots |
| `rose-50` | `#FCEEF2` | Fond de citation, highlight section |
| `ivory` | `#F5EFE4` | Fond de sections alternatives (FAQ, témoignages) |
| `cream` | `#FDFCF8` | Fond de sous-cartes, overlay gradient |

### Neutres
| Token | Valeur |
|-------|--------|
| `stone-900` | `#111111` | Texte principal |
| `stone-800` | `#1C1917` | Sous-titres |
| `stone-600` | `#57534E` | Texte corps |
| `stone-500` | `#78716C` | Texte secondaire |
| `stone-400` | `#A8A29E` | Texte footer, placeholder |
| `stone-300` | `#D6D3D1` | Bordures light |
| `stone-200` | `#E7E5E4` | Bordures standard |
| `stone-100` | `#F5F5F4` | Bordures subtiles |
| `white` | `#FFFFFF` | Fonds de cartes, overlays |

## Typographie

### Polices
| Rôle | Police | Poids |
|------|--------|-------|
| Titres (h1-h2) | `Newsreader`, serif | 400 (normal), 500 (medium) |
| Titres section (h3+) | `Inter`, sans-serif | 400, 600, 700 |
| Corps | `Inter`, sans-serif | 400, 500 |
| Italique citation | `Newsreader`, serif | 400 italic |

### Tailles titres
| Élément | Desktop | Mobile |
|---------|---------|--------|
| h1 (hero) | `text-8xl` (5rem) | `text-5xl` |
| h2 section | `text-5xl` | `text-3xl` ou `text-4xl` |
| h3 carte | `text-xl` | `text-xl` |
| Corps hero | `text-2xl` | `text-xl` |
| Corps standard | `text-base` | `text-base` |
| Corps petit | `text-sm` | `text-sm` |

### Règles
- Titres en `tracking-tight` et `leading-none` ou `leading-tight`
- Texte corps en `leading-relaxed`
- Le hero utilise une grappe de tailles : `text-5xl md:text-7xl lg:text-8xl`
- Les boutons (CTA chiffrés) sont en `font-bold uppercase tracking-wider` ou `tracking-widest`
- Les badges sont en `text-xs font-medium uppercase tracking-wider`

## Espacements

### Grille
- Contenu max-width : `max-w-7xl` (1280px)
- Sections serrées : `max-w-5xl`, `max-w-4xl`, `max-w-3xl`
- Padding latéral sections : `px-6`
- Gaps grid : `gap-6`, `gap-8`, `gap-12`

### Padding sections
| Contexte | Y padding |
|----------|-----------|
| Section standard | `py-24` |
| Section avec bg contrastée | `py-24` |
| Hero | `pt-32 pb-20 lg:pt-40 lg:pb-32` |
| Cards | `p-8` |

## Composants

### Boutons CTA (appels à action)
```html
<a href="#" class="inline-flex px-10 py-5 text-white rounded-xl transition-all duration-300 shadow-xl hover:shadow-2xl hover:-translate-y-1 active:scale-95 items-center justify-center gap-2 group max-w-md mx-auto w-full sm:w-auto font-bold uppercase tracking-widest text-base bg-primary hover:bg-primary-dark shadow-primary/30">
  Texte du CTA
  <iconify-icon icon="solar:arrow-right-linear" class="text-xl group-hover:translate-x-0.5 transition-transform"></iconify-icon>
</a>
```

### Cartes (features, bénéfices)
```html
<div class="border p-8 rounded-2xl bg-white border-stone-200 shadow-lg">
  <h3 class="text-xl font-bold text-stone-900 mb-3">Titre</h3>
  <p class="text-sm leading-relaxed text-stone-600">Texte</p>
</div>
```

### Cartes interactives (programme)
- `hover:border-primary/30` ou `hover:border-gold/30` ou `hover:border-rose-500/30`
- Numéro dans un containeur blanc avec ombre, `group-hover:scale-105`

### Badges / tags
```html
<div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white border border-stone-200 shadow-sm">
  <span class="flex h-2 w-2 rounded-full bg-rose-500 animate-pulse"></span>
  <span class="text-xs font-medium uppercase tracking-wider text-stone-500">Texte</span>
</div>
```

### Sections alternées
- Section blanche → `bg-white`
- Section grise → `bg-stone-50`
- Section ivoire → `bg-ivory`
- Section rose subtile → `bg-rose-50/30`
- `border-y` pour séparateurs horizontaux entre sections

## Responsive

- **Breakpoints** : Tailwind defaults (`sm: 640px, md: 768px, lg: 1024px, xl: 1280px`)
- **Navigation** : links masqués en mobile (`hidden md:flex`), bouton CTA toujours visible
- **Grids** : `grid md:grid-cols-2` ou `grid md:grid-cols-3` — single column par défaut
- **Hero** : tailles titres progressives, padding adaptatif
- **Sections** : `px-6` constant partout

## Animations

| Element | Animation |
|---------|-----------|
| Dot badge | `animate-pulse` |
| Flèche CTA | `group-hover:translate-x-0.5 transition-transform` |
| Bouton CTA | `hover:-translate-y-1 active:scale-95 transition-all duration-300` |
| Numéro carte | `group-hover:scale-105 transition-transform` |
| Lecture overlay | `group-hover:scale-110 transition-transform duration-300` |
| Flèche FAQ | `group-open:rotate-180 transition-transform` |
| Bounce scroll | `animate-bounce` |
| Pricing tag | `hover:scale-105 transition-transform` |

## Créer une nouvelle page cohérente

1. Créer le fichier dans `src/pages/`
2. Utiliser `BaseLayout` comme wrapper
3. Importer les composants section existants
4. Pour une nouvelle section :
   - Copier un composant similaire
   - Respecter les variables de couleur (`bg-primary`, `text-primary`, etc.)
   - Utiliser les espacements standards (`py-24 px-6`)
   - Maintenir les gaps et padding de la grille
5. Mettre à jour la navigation si nécessaire
