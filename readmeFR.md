[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18629367.svg)](https://doi.org/10.5281/zenodo.18629367)

Languages: [English](./README.md) · [Français](./readmeFR.md) · [한국어](./readmeKR.md) · [日本語](./readmeJP.md)

# dollarization-panel-data

# Jeu de données global sur la dollarisation des dépôts (1980–2019)

## Aperçu

Jeu de données de panel sur le **taux de dollarisation des dépôts** (Dépôts en devises / Total des dépôts) couvrant **128 pays** de **1980 à 2019**, avec **2 646 observations**. Les données proviennent de publications des banques centrales, de rapports des services du FMI (IMF Staff Reports) et de CEIC.

Ce jeu de données a été construit dans le cadre du mémoire de maîtrise suivant :

> **Jang, H. (2021). "Dollarization: Trends and its Determinants." Master’s Thesis, Graduate School of Commerce, Waseda University. Advisor: Prof. Koichi Takase.**

## Citation

Si vous utilisez ce jeu de données, veuillez le citer comme suit :

```
Jang, Hyungju (2021). Dollarization: Trends and its Determinants.
Master's Thesis, Waseda University. Dataset available at: [DOI]
```

## Fichiers

| Fichier | Description |
| --- | --- |
| `dollarization_panel.csv` | Jeu de données de panel principal au format « tidy » |
| `dollarization_sources.csv` | URL des sources (banques centrales) pour chaque pays |
| `Data_dolrat_raw.xlsx` | Fichier de données brutes (raw) d’origine |

## Définitions des variables

### dollarization_panel.csv

| Variable | Description |
| --- | --- |
| `country` | Nom du pays |
| `iso3` | Code pays ISO 3166-1 alpha-3 |
| `year` | Année (1980–2019) |
| `fcd_td_ratio` | Taux de dollarisation des dépôts : dépôts en devises ÷ total des dépôts |

### dollarization_sources.csv

| Variable | Description |
| --- | --- |
| `country` | Nom du pays |
| `iso3` | Code pays ISO 3166-1 alpha-3 |
| `source_url` | URL de la banque centrale ou de la source de données |

## Méthodologie

### Définition

Le taux de dollarisation est défini comme suit :

Taux de dollarisation = Dépôts en devises (Foreign Currency Deposits, FCD) ÷ Total des dépôts (Total Deposits, TD)

En suivant Mwase et Kumah (2015), le dénominateur retenu est le total des dépôts (Total Deposits) plutôt que la monnaie au sens large (Broad Money), comme dans la convention plus ancienne de Baliño et al. (1999). Ce choix vise à mesurer plus précisément la préférence des résidents pour la détention de dépôts en devises.

Les pays où ce ratio dépasse **30 %** sont classés comme **économies fortement dollarisées (Highly Dollarized Economies, HDE)** ; ceux dont le ratio se situe entre **10–30 %** comme **économies modérément dollarisées (Moderately Dollarized Economies, MDE)**.

### Construction des données

- Sources primaires : bulletins statistiques des banques centrales, rapports annuels et bases de données
- Sources secondaires : rapports des services du FMI (IMF Staff Reports), CEIC (pour la Chine)
- Données historiques (avant 2000) pour certains pays : Baliño et al. (1999)
- Pour limiter les incohérences entre normes de diffusion, les données de chaque pays ont été obtenues, autant que possible, auprès d’une source unique et homogène.

### Couverture

- **128 pays** disposant d’au moins une observation
- Couverture temporelle variable selon les pays (voir l’annexe du mémoire)
- La plupart des pays disposent de données à partir de **2000**, certains remontant jusqu’à **1980**
- La couverture s’élargit au fil du temps : de 4 pays en 1980 à 125 pays en 2014

## Points importants

### Économies entièrement dollarisées (non incluses dans le jeu de données)

Les pays suivants ont adopté une devise étrangère comme monnaie légale et sont donc **exclus** du calcul du taux de dollarisation des dépôts, qui n’est pas applicable dans leur cas :

| Pays | Devise | Année d’adoption |
| --- | --- | --- |
| Panama | USD | 1904 |
| Équateur | USD | 2000 |
| El Salvador | USD | 2001 |
| Zimbabwe | Devises multiples | 2009 |

En outre, les pays de la zone franc CFA (UEMOA/CEMAC) et les membres de la zone euro sont traités comme des économies formellement « dollarisées » (au sens d’une monnaie étrangère ou commune). Certains pays ayant rejoint la zone euro présentent une forte baisse du ratio au moment de l’adoption de l’euro (par exemple, Estonie 2011, Lettonie 2014, Lituanie 2015).

### Effet de l’euro

Dans les pays ayant adopté l’euro, on observe une **rupture structurelle** dans le taux de dollarisation au moment de l’adoption : les dépôts libellés en euros sont reclassés comme dépôts en monnaie domestique plutôt qu’en devises. Les moyennes régionales pour l’Europe et l’Asie centrale doivent donc être interprétées à la lumière de cet effet.

### Limites connues

- Certains pays ne publient que le ratio FCD/monnaie au sens large, et non FCD/total des dépôts.
- Les ratios reportés pour le Venezuela avant 2019 peuvent ne pas refléter le niveau réel de dollarisation, en raison de doutes sur la fiabilité statistique.
- Les barrières linguistiques ont compliqué la collecte de données pour certains pays (par exemple, la Mauritanie).
- L’usage de devises étrangères sous forme de billets (dollarisation des paiements, « payment dollarization ») n’est pas capté par cet indicateur.
- Plusieurs pays à revenu élevé (Australie, France, Italie, Irlande, Portugal, Nouvelle-Zélande) ne publient pas de statistiques sur les dépôts en devises détenus par les résidents.

## Indicateurs de qualité des données

Les cas suivants nécessitent une prudence particulière dans l’interprétation :

- **Données antérieures à 1995** : disponibles pour moins de 40 pays
- **Iran** : divergences entre année fiscale et année civile dans certaines sources
- **Argentine** : les restrictions administratives sur les dépôts en devises ont affecté les ratios publiés à plusieurs périodes
- **Venezuela** : problèmes de fiabilité des données (voir la section 2.3.2 du mémoire)

## Licence

Ce jeu de données est diffusé sous licence MIT.  
Vous êtes libre de le partager et de l’adapter, à condition d’en citer correctement la source.

Le texte complet de la licence est disponible ici : [MIT License](https://opensource.org/licenses/MIT).

## Références

- Baliño, T., Bennett, A., & Borensztein, E. (1999). "Monetary Policy in Dollarized Economies." IMF Occasional Paper 171.
- Levy-Yeyati, E. (2006). "Financial Dollarization: Evaluating its Consequences." *Economic Policy*, 21(45), 61–118.
- Mwase, N. & Kumah, Y. (2015). "Revisiting the Concept of Dollarization." IMF Working Paper WP/15/12.

## Contact

Hyungju Jang — hyungju.jang@umontreal.ca  
https://github.com/hj8779