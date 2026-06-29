# 🏛️ Portail Unifié de Numérisation de l'État Civil National - INFOTEAM

Ce dépôt contient le code source complet de la plateforme unifiée de numérisation, d'indexation et d'injection sécurisée des registres d'état civil, développée dans le cadre de la modernisation des services de l'état civil national.

---

## 🚀 Fonctionnalités Majeures

1. **Workflow Unifié en 7 Étapes** : Intégration complète de bout en bout (Acquisition zénithale, Contrôle Qualité Image, Indexation des registres, OCR Intelligent bilingue, Double Saisie Aveugle, Arbitrage de divergences, Clôture et Scellement Cryptographique).
2. **Double Saisie Aveugle (Double Entry)** : Algorithme de comparaison bilingue en temps réel (Arabe / Français) empêchant toute divergence d'écriture de l'acte d'état civil de s'insérer en base de données.
3. **Console d'Arbitrage Intelligente** : Interface de confrontation permettant au superviseur de résoudre les anomalies d'indexation et les incohérences de caractères.
4. **Injection Transactionnelle (Bulk Insert)** : Module d'importation et d'injection en lot de fichiers JSON structurés dans la base PostgreSQL sous protection de transactions ACID (`BEGIN ... COMMIT`).
5. **Sécurité & Traçabilité (RBAC & JWT)** : Contrôle d'accès basé sur les rôles de l'atelier de numérisation avec traçabilité complète de chaque action enregistrée dans le journal d'audit de la base de données.

---

## 🛠️ Architecture Technique

- **Frontend** : React 19, Tailwind CSS v4, Motion (Framer Motion) pour les transitions animées de workflow.
- **Backend (API / Serveur)** : Node.js, Express, PostgreSQL, Drizzle ORM.
- **Bibliothèques annexes** : Lucide-react (icônes), JSZip (gestion des exports d'archives d'actes).

---

## 📦 Installation et Lancement Local

### Prérequis
- **Node.js** (version 18 ou supérieure recommandée)
- **PostgreSQL** (configuré et actif)

### Étape 1 : Cloner le dépôt et installer les dépendances
```bash
git clone https://github.com/votre-compte/portail-num-etat-civil.git
cd portail-num-etat-civil
npm install
```

### Étape 2 : Configurer les variables d'environnement
Créez un fichier `.env` à la racine du projet :
```env
GEMINI_API_KEY="VOTRE_CLE_API_POUR_OCR_IA"
APP_URL="http://localhost:3000"
```

### Étape 3 : Initialiser la table de la base de données
Exécutez le script SQL d'initialisation de la table `civil_records` dans votre instance PostgreSQL locale (voir le script SQL de structure fourni dans le module d'injection).

### Étape 4 : Lancer l'application en mode développement
```bash
npm run dev
```
L'application sera accessible localement sur `http://localhost:3000`.

---

## 📝 Licence
Ce projet a été développé en exclusivité pour la société **INFOTEAM** dans le cadre du projet de numérisation nationale des registres civils d'état civil. Tous droits réservés.
