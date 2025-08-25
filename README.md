# 📄 Mini-projet : Flux de facturation électronique (Python + XML)

## 🎯 Objectif
Ce projet illustre la mise en place d’un **pipeline simple de traitement de factures électroniques**.  
Il permet de :
1. **Lire** des factures XML brutes.
2. **Valider** leur conformité à un schéma XSD.
3. **Extraire** les données clés (numéro, date, client, montant, devise).
4. **Simuler** un envoi vers une plateforme externe (API mockée).
5. **Stocker** les résultats dans une base SQLite.
6. **Générer** un rapport CSV.
7. **Classer** les fichiers valides et invalides dans des répertoires distincts.

---

## 🛠️ Stack technique
- **Python 3.10+**
- **lxml** → parsing & validation XML
- **SQLite** → stockage des résultats
- **CSV** → reporting
- **Requests** → simulation d’envoi API

---

## 📂 Structure du projet
facturation_mini_projet/
│── inbox/ # Factures XML en entrée
│── processed/ # Factures valides traitées
│── invalid/ # Factures invalides + fichiers d’erreurs
│── schemas/ # Schéma XSD (invoice.xsd)
│── main.py # Script principal
│── invoices.db # Base SQLite (générée après exécution)
│── report.csv # Rapport des factures traitées
│── README.md # Documentation

---

## ▶️ Installation & Exécution
### 1. Cloner le repo
```bash
git clone https://github.com/<ton-compte>/facturation-xml-python.git
cd facturation-xml-python
pip install lxml requests
python main.py
```

---

## 📊 Résultats attendus
Après exécution :
Les fichiers valides sont déplacés dans processed/.
Les fichiers invalides vont dans invalid/ avec un fichier d’erreurs associé.
Une base SQLite invoices.db est créée avec une table invoices.
Un fichier report.csv récapitule les factures traitées (numéro, date, client, total, statut).

---

🔜 Améliorations possibles
Validation contre le schéma officiel Factur-X.
Conversion entre formats XML (UBL, CII → Factur-X).
Intégration d’un vrai appel API (authentification, retries, logs).
Migration de SQLite vers PostgreSQL.
Ajout de tests unitaires (pytest).
Journalisation en JSON pour exploitation BI/ELK.
