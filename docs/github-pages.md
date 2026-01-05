# Publication GitHub Pages

Ce dépôt publie l’UI via GitHub Pages en servant `docs/index.html` (et `docs/images/...`).

## Pré-requis
- Auth GitHub CLI (`gh auth status`)
- Accès au repo (`xbasset/scroll-to-learn`)

## Workflow (mise à jour)
1) Générer les fichiers Pages
```bash
mkdir -p docs/images
rm -rf docs/images/text-1
cp src/ui/text-1-scroll.html docs/index.html
cp -R src/ui/images/text-1 docs/images/
```

2) Commit + push
```bash
git add docs/index.html docs/images
git commit -m "feat: update github pages site"
git push
```

3) Vérifier l’état du build
```bash
gh api repos/xbasset/scroll-to-learn/pages
```

## Initialisation (une seule fois)
Si Pages n’est pas encore activé :
```bash
gh api -X POST repos/xbasset/scroll-to-learn/pages -f "source[branch]=main" -f "source[path]=/docs"
```

## URL
Le site est servi à :
```
http://xbasset.com/scroll-to-learn/
```
