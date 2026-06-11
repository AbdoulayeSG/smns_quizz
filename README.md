<div align="center">

<img src="img/logo2.jpeg" alt="Génie en Herbe Logo" width="160" />

# 🧠 Génie en Herbe

**Quiz interactif en temps réel pour les compétitions d'équipes**

[![HTML](https://img.shields.io/badge/HTML-Single%20File-f15a24?style=flat-square&logo=html5&logoColor=white)](.)
[![Firebase](https://img.shields.io/badge/Firebase-Realtime%20DB-FFCA28?style=flat-square&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Licence](https://img.shields.io/badge/Licence-Libre-16a34a?style=flat-square)](.)

</div>

---

## ✨ Présentation

**Génie en Herbe** est une application de quiz multi-équipes conçue pour les compétitions scolaires et universitaires. Un seul fichier HTML suffit — pas de serveur, pas d'installation.

Le meneur de jeu pilote tout depuis son écran, les équipes buzzent depuis leur téléphone, et un grand écran TV affiche les questions en temps réel via Firebase.

---

## 🚀 Fonctionnalités

| Fonctionnalité | Description |
|---|---|
| 🎮 **Multi-équipes** | Jusqu'à 8 équipes, scores en direct |
| 🔔 **Buzzers connectés** | Chaque équipe a son lien buzzer personnel |
| 📺 **Écran TV** | Affichage plein écran synchronisé via Firebase |
| 🃏 **Révélation différée** | Compte à rebours configurable avant l'apparition de la carte |
| 🟩 **Réponse visible** | Rectangle vert qui s'affiche sur commande |
| ⠿ **Tri manuel** | Glisser-déposer les questions et catégories dans l'admin |
| ⏱️ **Minuteur** | Chrono par équipe avec sons (vrai / faux / time.mp3) |
| 🖼️ **Questions image** | Mode "C'est qui / C'est quoi ?" avec upload d'image |
| 📥 **Import / Export** | Banque de questions en JSON |
| 🔄 **Nouvelle session** | Chaque nouvelle partie génère une session Firebase fraîche |

---

## 🗂️ Structure du projet

```
genie-en-herbe/
├── index.html          # Application complète (fichier unique)
├── img/
│   ├── logo.jpeg       # Logo navbar
│   ├── logo2.jpeg      # Logo hero
│   └── back.jpeg       # Image de fond setup
└── sounds/
    ├── buzzeur.mp3     # Son du buzzer
    ├── vrai.mp3        # Bonne réponse
    ├── faux.mp3        # Mauvaise réponse
    ├── time.mp3        # Minuteur en boucle
    └── win.mp3         # Victoire
```

---

## ⚙️ Installation

**Aucune installation requise.** Il suffit d'ouvrir `index.html` depuis un serveur local ou un hébergement statique (Netlify, GitHub Pages, etc.).

> ⚠️ Le fichier doit être servi en **HTTPS** pour que le presse-papiers et Firebase fonctionnent correctement. En local, utilise un serveur (ex. `npx serve .` ou l'extension Live Server de VS Code).

---

## 🎯 Guide d'utilisation

### 1 — Préparer les questions

1. Ouvre l'application et clique sur **⚙ Admin** depuis l'écran de jeu
2. Crée tes questions (Standard, Indice, Image, Explication)
3. **Glisse-dépose** les questions ou catégories pour changer leur ordre
4. Exporte la banque en JSON pour la réutiliser plus tard

### 2 — Lancer une partie

1. Clique sur **Lancer** en page d'accueil
2. Ajoute les équipes (2 à 8)
3. Clique sur **Démarrer la partie**

### 3 — Connecter les appareils

| Appareil | Comment |
|---|---|
| 📺 Grand écran TV | Clic sur **📺 Partager l'écran TV** → ouvre le lien sur la TV |
| 📱 Buzzer équipe | Clic sur **🔔 Copier lien Buzzer** → envoie le lien à chaque équipe |

### 4 — Jouer

- **Flèches** ← → pour naviguer entre les questions
- **Révéler réponse** pour afficher la réponse (rectangle vert)
- Clique sur une équipe pour lancer son minuteur
- **R** = révéler / **F** = plein écran (raccourcis clavier)

---

## ⚙️ Paramètres Admin

| Réglage | Description |
|---|---|
| ⏱️ **Durée minuteur** | De 5 à 120 secondes par question |
| 🃏 **Délai révélation** | Secondes avant l'apparition de la carte (0 = instantané) |
| 📊 **Scores** | Ajustement manuel + / − par équipe |

---

## 🧩 Types de questions

- **Standard** — Question + réponse + points
- **Indice** — Jusqu'à 5 indices progressifs (points dégressifs 50→10)
- **C'est qui / C'est quoi ?** — Upload d'une image à identifier
- **Explication (Q0)** — Texte d'introduction pour une catégorie, sans réponse

---

## 🔥 Firebase

L'application utilise **Firebase Realtime Database** pour synchroniser en temps réel :

- L'état de la question affichée sur l'écran TV
- Les buzzers des équipes
- Les sons (buzzer, vrai, faux, minuteur, victoire)
- Le vainqueur en fin de partie

La configuration Firebase est embarquée dans `index.html`. Pour utiliser ta propre base, remplace le bloc `initializeApp({...})` avec les paramètres de ton projet Firebase.

---

## 🏆 Fin de partie

- Clique sur **Fin de partie** → podium animé avec confettis
- L'écran TV affiche un compte à rebours puis le nom du vainqueur
- **Nouvelle partie** génère une nouvelle session Firebase et repart de zéro

---

<div align="center">

Fait par Markus</> & Portgas👻 pour les compétitions de quiz — **Génie en Herbe**

</div>
