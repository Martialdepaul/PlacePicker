# PlacePicker 🌍

**PlacePicker** est une application web interactive qui vous propose des lieux à visiter en fonction de votre localisation. Ce projet a été conçu non seulement pour offrir une expérience utilisateur fluide et rapide, mais également pour explorer et mettre en pratique les **hooks de React**, notamment :

- **useEffect** 🔄 : Pour gérer les effets secondaires comme la récupération de la localisation utilisateur.
- **useRef** 🔧 : Pour manipuler directement le DOM et stocker des références.
- **useCallback** ⚡ : Pour optimiser les performances en mémorisant des fonctions.
- **useState** 💡 : Pour gérer l'état de l'application.

---

## 🚀 Fonctionnalités

- 🗺️ **Propositions de lieux** : Obtenez une liste de lieux intéressants à visiter en fonction de votre localisation.
- 📍 **Détection de localisation** : Utilise l'API de géolocalisation du navigateur pour personnaliser l'expérience.
- 📱 **Responsive Design** : Compatible avec les écrans de toutes tailles (mobile, tablette, desktop).
- ⚡ **Performances optimisées** : Conçu avec Vite et React pour un rendu rapide.

---

## 📍 Gestion de la géolocalisation

PlacePicker utilise l'API de géolocalisation du navigateur pour récupérer la position actuelle de l'utilisateur et trier les lieux disponibles par distance. Voici un aperçu de la logique derrière cette fonctionnalité :

```javascript
useEffect(() => {
  navigator.geolocation.getCurrentPosition((position) => {
    const sortedPlaces = sortPlacesByDistance(
      AVAILABLE_PLACES,
      position.coords.latitude,
      position.coords.longitude
    );
    setAvailablePlaces(sortedPlaces);
  });
}, []);
```

### **Explications** 💡:
- **`navigator.geolocation.getCurrentPosition`** 📡 : Cette méthode demande à l'utilisateur l'accès à sa localisation et renvoie les coordonnées (`latitude`, `longitude`).
- **`sortPlacesByDistance`** 🔍 : Une fonction qui trie la liste des lieux (`AVAILABLE_PLACES`) en fonction de leur distance par rapport à la position de l'utilisateur.
- **`setAvailablePlaces`** 📊 : Met à jour l'état local avec les lieux triés, permettant à l'interface utilisateur de s'adapter dynamiquement.

### **Pourquoi utiliser `useEffect` ?** 🤔  
Le hook `useEffect` permet de déclencher cette logique une seule fois après le rendu initial du composant, ce qui est idéal pour les opérations liées à la récupération de données ou aux effets secondaires.

### **Points techniques à noter** ⚙️ :
- En cas de refus de l'autorisation, il serait utile de prévoir une gestion des erreurs avec `navigator.geolocation.getCurrentPosition(successCallback, errorCallback)` 🚨.
- L'utilisation d'une fonction de tri personnalisée comme `sortPlacesByDistance` ajoute une touche professionnelle en personnalisant l'expérience utilisateur 🎯.

---

## 🛠️ Technologies utilisées 🔧

- **[React](https://reactjs.org/)** ⚛️ : Framework JavaScript pour construire l'interface utilisateur.
- **[Vite](https://vitejs.dev/)** 🚀 : Outil de développement rapide pour les projets React.
- **CSS** 🎨 : Pour le stylisme et le design.

---

## 📂 Structure du projet

```
PlacePicker/
├── public/                 # Ressources publiques
├── src/                    # Code source
│   ├── components/         # Composants React
│   ├── hooks/              # Hooks personnalisés (le cas échéant)
│   ├── assets/             # Images et ressources
│   ├── styles/             # Fichiers CSS
│   ├── App.jsx             # Composant principal
│   └── main.jsx            # Point d'entrée
├── package.json            # Dépendances et scripts
└── vite.config.js          # Configuration de Vite
```

---

## ⚙️ Installation et exécution 🖥️

1. **Cloner le projet** :

   ```bash
   git clone https://github.com/username/PlacePicker.git
   ```

2. **Accéder au dossier du projet** :

   ```bash
   cd PlacePicker
   ```

3. **Installer les dépendances** :

   ```bash
   npm install
   ```

4. **Lancer le projet** 🚀 :

   ```bash
   npm run dev
   ```

5. **Ouvrir dans le navigateur** 🌐 :  
   Une fois que le serveur est lancé, ouvrez [http://localhost:3000](http://localhost:3000) dans votre navigateur.

---

## 🔍 Apprentissage et concepts explorés 📚

Ce projet a été une opportunité pour approfondir les **hooks React** et comprendre comment les utiliser efficacement :

- **useEffect** 🔄 : Gestion des effets secondaires comme la demande de permission de géolocalisation.
- **useRef** 🔧 : Références pour manipuler certains éléments du DOM.
- **useCallback** ⚡ : Optimisation des fonctions dépendantes de props ou d'état.
- **useState** 💡 : Gestion des états dynamiques de l'application.

---

## 🎨 Aperçu 🖼️

Voici quelques captures d'écran de l'application :  
*(Ajoutez ici des images ou GIFs montrant votre application en action.)*

---

## 🔒 Permissions requises 🔐

Pour fonctionner correctement, l'application a besoin d'accéder à votre position 📍. Assurez-vous de permettre cette autorisation dans votre navigateur lorsque vous y êtes invité.

---

## 📬 Contribuer 🤝

Les contributions sont les bienvenues ! Si vous souhaitez améliorer PlacePicker, suivez ces étapes :

1. **Fork le projet** 🍴.
2. **Créer une branche pour vos modifications** :
   ```bash
   git checkout -b feature/nouvelle-fonctionnalité
   ```
3. **Faire vos changements et valider** :
   ```bash
   git commit -m "Ajout d'une nouvelle fonctionnalité"
   ```
4. **Pousser vos changements** :
   ```bash
   git push origin feature/nouvelle-fonctionnalité
   ```
5. **Ouvrir une Pull Request** 📝.

---

## 📖 Licence 📝

Ce projet est sous licence [MIT](LICENSE).

---

## 💬 Contact ✉️

Si vous avez des questions ou des suggestions, n'hésitez pas à me contacter :  
**Nom** : Martial De-Paul  
**E-mail** : [votre-email@example.com](mailto:depaulmartial4@gmail.com)  
**GitHub** : [https://github.com/username](https://github.com/Martialdepaul)
```

Cette version utilise davantage d'emojis pour rendre le `README.md` plus dynamique et visuellement attrayant ! 😊
