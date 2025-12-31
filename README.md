# Exercice — Vue 3 (Events)

## Objectif

Développer une application Vue 3 affichant une liste d’événements.
L’exercice permet de pratiquer :

- Composition API
- le découpage en composants
- le routage avec Vue Router
- l’appel d’une API externe avec Axios

---

## Technologies

- Vue 3
- Vite
- Composition API
- Vue Router 4
- Axios

---

## Installation

```bash
npm install
npm run dev
```

Application disponible sur : http://localhost:5173

---

## Structure principale

```
src/
├── App.vue
├── main.js
├── router/index.js
├── components/
│   └── EventCard.vue
├── views/
│   ├── EventList.vue
│   └── AboutView.vue
└── services/
    └── EventService.js
```

---

## Fonctionnement

- `EventList.vue` affiche la liste des événements
- `EventCard.vue` affiche un événement via une `props`
- `EventService.js` récupère les données depuis une API JSON
- `router/index.js` gère la navigation (Événements / À propos)

---

## Concepts abordés

- `ref`, `onMounted`
- `defineProps`
- `v-for`
- Vue Router
- Appels API avec Axios
