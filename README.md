# TAONSA Catalog Feed

Catalog Meta Commerce Manager pour [taonsa.com](https://taonsa.com).

## Fichiers

- **facebook-feed.xml** — Catalog au format RSS 2.0 avec namespace `g:` (Meta + Google compatible)
- **facebook-feed.csv** — Meme catalog au format CSV
- **facebook-feed.tsv** — Meme catalog au format TSV (tab-separated)

Produits dans ce catalog : **88**

## URLs Meta Commerce Manager

Une fois GitHub Pages active, utilise une de ces URLs :

```
https://<TON-USER>.github.io/taonsa-catalog/facebook-feed.xml
https://<TON-USER>.github.io/taonsa-catalog/facebook-feed.csv
https://<TON-USER>.github.io/taonsa-catalog/facebook-feed.tsv
```

## Sync automatique

Le workflow `.github/workflows/sync-feed.yml` :
- Tourne **toutes les heures** (cron GitHub)
- Telecharge le dernier `facebook-feed.xml` depuis `https://taonsa.com/facebook-feed.xml`
- Push sur ce repo si changement detecte
- GitHub Pages redeploie automatiquement (~30 sec)
- Meta voit le nouveau catalog au prochain re-fetch

Pour declencher manuellement : **Actions** > **Sync catalog feed** > **Run workflow**

## Pourquoi GitHub Pages ?

Cloudflare (devant taonsa.com) challenge intermittement le bot Meta sur l'UA `facebookexternalhit`. Resultat : 1 re-fetch sur 3 echoue avec "erreur non autorisee".

GitHub Pages n'a aucun WAF/CDN devant -> Meta peut lire sans probleme. 100% reliability.

Le sync GitHub Action utilise un UA generique (`Mozilla/5.0 GitHub-Actions-Catalog-Sync`) qui n'est pas profile par Cloudflare.

---

Genere par TAONSA admin tools le 