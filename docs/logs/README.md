# Logs du site

Ce dossier garde les traces utiles du site `vero-rakoto.com`, séparées du Second Cerveau.

## Organisation

- `global.md` : conventions transversales au site, identité publique, infrastructure générale.
- `pages/` : logs par page ou parcours du site.
- `categories/` : logs par sujet transversal quand l'information concerne plusieurs pages.

## Quand loguer

Loguer ici uniquement les décisions utiles à retrouver plus tard : choix d'outil, intégration externe, convention éditoriale du site, comportement d'une page, dépendance technique.

Ne pas loguer ici les détails déjà suffisamment tracés par Git, sauf s'ils expliquent une décision durable.

## Où ranger

- Une modification liée à une URL précise va dans `pages/[slug].md`.
- Une convention globale, un choix d'infrastructure ou une règle d'identité publique va dans `global.md`.
- Un sujet qui traverse plusieurs pages va dans `categories/[sujet].md`.

## Exemples de catégories

- `categories/video.md` : hébergement vidéo, player, thumbnails, règles autoplay.
- `categories/seo.md` : titres, descriptions, indexation, schema.
- `categories/design.md` : conventions visuelles, composants, responsive.
- `categories/contenu.md` : ton éditorial, formulations récurrentes, noms publics.

## Règle avec le Second Cerveau

Le Second Cerveau reste réservé aux décisions business, stratégie, identité personnelle ou organisation globale.

Le site garde ses propres logs opérationnels dans ce dossier.
