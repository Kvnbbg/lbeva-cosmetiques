# L.BEVA Cosmétiques — prototype V1

Maquette statique, non contractuelle. `index.html` est autonome (HTML, CSS, JS et images WebP embarquées). Aucun service tiers, compte, dépendance npm ou serveur de paiement requis. Le dépôt doit rester privé ; ne pas publier le prototype en accès public sans validation de la cliente. Les visuels sont issus des supports communiqués ; aucune capture de conversation n'est incluse, uniquement les extraits publicitaires.

## Prévisualisation locale
Ouvrir `index.html` dans un navigateur. Pour un test à origine stable : `python3 -m http.server 8080` puis ouvrir `http://localhost:8080`. Le panier est conservé dans localStorage si disponible. Les liens externes ne sont ouverts que sur clic.

## Créer le dépôt privé sur GitHub
Depuis le dossier extrait, avec Git et GitHub CLI installés et authentifiés (`gh auth login`) :

```sh
git init -b main
git add index.html README.md
git commit -m "Initial L.BEVA storefront prototype"
gh repo create lbeva-cosmetiques --private --source=. --remote=origin --push
```

Ou créer un dépôt vide privé via https://github.com/new et importer les deux fichiers. GitHub Pages sur dépôt privé demande un plan éligible et le site n'est pas forcément privé. GitHub Pages n'est pas prévu pour exploiter une boutique en ligne. Préférer un hébergement statique autorisant l'usage commercial, avec accès protégé pour la recette client. `noindex` n'est pas un contrôle d'accès.

## Parcours de démo
- Catalogue de 9 références ; catégories Corps, Visage, Maquillage.
- Panier et quantités ; prix fictifs signalés, sous-total hors livraison.
- Retrait avec espèces à convenir ; expédition Mondial Relay ou Shop2Shop avec paiement à définir avant envoi.
- Message WhatsApp prérempli explicitement DEMO, envoi manuel. Aucun paiement ou commande confirmé.
- Stripe : bouton désactivé « bientôt ». Aucun compte ni API Stripe connecté. À terme, utiliser Stripe Checkout ou Payment Links, sans clé secrète côté client, et vérifier les commandes côté serveur avant expédition.

## Informations à valider avant production
- Nom commercial exact (L.BEVA / LBEVA), droits des images, photos individuelles, prix TTC réels, stock, tailles, teintes et variantes.
- Pays d'origine réel, fabricant/personne responsable, liste INCI exhaustive, volume, précautions et preuves des allégations. Les actifs indiqués dans la maquette proviennent des supports marketing et ne constituent pas une formule certifiée.
- Délais de préparation, zone de retrait, poids et dimensions emballés, tarifs et restrictions transporteur (notamment nature des produits), politique de paiement et remboursement. Pas de contre-remboursement en relais présumé.
- Mentions légales, CGV, confidentialité, droit de rétractation et modalités applicables. Validation de conformité cosmétique avant mise en vente.
- Validation client puis devis ; aucun tarif de prestation arrêté.

Sources de référence : https://www.economie.gouv.fr/dgccrf/les-fiches-pratiques/vente-en-ligne-de-cosmetiques-la-liste-des-ingredients-doit-etre-affichee ; https://www.mondialrelay.fr/solutions-professionnels/nos-offres-ecommercants/offre-start?tab=tarifs ; https://www.chronopost.fr/fr/livraison/nos-offres/shop2shop-chronopost ; https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits
