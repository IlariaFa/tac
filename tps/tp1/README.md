# TP1 - Web Scraping et APIs

## s3 - Scraping

**Objectif :**  
Télécharger automatiquement les 51 fichiers PDF listés sur le site de CAMille (https://max.de.wilde.web.ulb.be/camille/).

**Fonctionnement :**  
- Le script utilise la bibliothèque `requests` pour accéder à la page web contenant les liens PDF.
- Il utilise `BeautifulSoup` pour analyser le HTML et identifier tous les liens vers des fichiers `.pdf`.
- Il reconstitue les URL complètes et les télécharge automatiquement dans un dossier local (ex. `pdf/`).
- Le certificat SSL du site étant non reconnu, le paramètre `verify=False` est utilisé dans `requests.get(...)`.

## s2 - API

**Objectif :**  
Utiliser une API libre (https://byabbe.se/on-this-day) pour enrichir l’information des fichiers PDF téléchargés.

**Fonctionnement :**  
- Le script parcourt les fichiers PDF téléchargés dans le dossier `pdf/`.
- Il extrait automatiquement la date depuis le nom du fichier (ex : `KB_JB92_1860-02-09_01-00003.pdf` → `1860-02-09`).
- Il interroge l’API **"On This Day"** en utilisant la date (mois/jour) pour obtenir des événements historiques survenus ce jour-là.
- Il affiche les 3 premiers événements retournés par l’API.

---

## Remarque

Aucune extraction du contenu textuel des PDF n’était demandée dans ce TP. Le script de scraping ne lit pas les fichiers PDF, il se limite à leur **téléchargement** depuis le site.

