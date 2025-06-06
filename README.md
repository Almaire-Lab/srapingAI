# srapingAI
Scraping d'un site incluant des publication scientifique AI.

Merci pour le partage du code ! Voici un `README.md` bien rédigé, structuré et adapté **à ton script spécifique**, en décrivant clairement les fonctionnalités réelles et les objectifs du projet :

---

# AI Evolution Tracker – Scraping ArXiv for AI Publications

## Objectif

Ce projet Python permet de **scraper automatiquement les publications liées à l’intelligence artificielle sur le site [arXiv.org](https://arxiv.org/)** afin de :

* Quantifier le **nombre d’articles publiés** sur une période donnée,
* Suivre l’**évolution temporelle de la recherche en IA**,
* Générer une **base de données prête à l’analyse** (dates, titres, liens),
* Fournir un **outil de veille et d’analyse** sur l’essor de l’intelligence artificielle.

---

## Fonctionnalités principales

*  **Scraping avancé de ArXiv** basé sur des paramètres de recherche précis (`terms`, `date_range`, pagination…).
*  **Analyse mensuelle automatique** : segmentation par mois entre deux années données.
*  **Extraction structurée** des titres, dates et liens des articles.
*  **Conversion des dates en timestamp** pour faciliter l’analyse temporelle.
*  **Sauvegarde au format JSON** des résultats pour réutilisation dans des analyses ou visualisations.

---

## Technologies utilisées

* [`requests`](https://docs.python-requests.org/en/master/) – pour faire les requêtes HTTP
* [`BeautifulSoup`](https://www.crummy.com/software/BeautifulSoup/) – pour parser le HTML
* `datetime`, `time` – pour la gestion de dates et pauses entre requêtes
* `json` – pour sauvegarder les données extraites

---

## Exemple d’utilisation

```python
# Lancer une analyse de 2020 à 2024
main(2020, 2024)
```

Le script effectuera une recherche mensuelle de janvier 2020 à décembre 2024, paginera les résultats (limités à 10 000 max), extraira les informations pertinentes, puis les enregistrera dans `ARXIV_DATA.json`.

---

## Structure du code

```bash
ai-evolution-scraper/
├── scraper.py         # Contient l'ensemble du script
├── ARXIV_DATA.json    # Fichier généré avec les données extraites
```

Fonctions principales :

* `get_page_content(...)` : construit et exécute les requêtes de recherche sur ArXiv
* `get_total_results(...)` : extrait le nombre total d’articles disponibles
* `extract_article_info(...)` : récupère titre, lien, date (convertie en timestamp)
* `fetch_articles_for_period(...)` : gère la pagination et l’agrégation des résultats
* `search_by_monthly_segments(...)` : automatise la recherche par mois
* `main(...)` : lance le processus global

---

## Prérequis

* Python 3.7+
* Installer les dépendances :

```bash
pip install requests beautifulsoup4
```

---

## Exemples d’utilisation dans un projet

* **Études académiques** sur la croissance de la recherche IA
* **Data visualisation** de tendances mensuelles
* **Veille technologique** sur les publications scientifiques
* **Corpus de données** pour NLP ou analyse sémantique

---

## Améliorations possibles

* Ajout d’analyses statistiques automatiques (ex. : volume mensuel)
* Extension à d'autres mots-clés ou domaines de recherche
* Déploiement en tâche planifiée (cron job)
* Export CSV pour traitement avec Excel ou outils BI

---

