<template>
    <div class="text-card">
      <h3 class="text-card-title">{{ title }}</h3>
      <p class="text-card-content">{{ content }}</p>
      <p class="text-card-source">
        <a href="{{ source }}">En savoir plus</a>
      </p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        default: "Titre par défaut", // Titre par défaut si aucun n'est passé
      },
      content: {
        type: String,
        default: "Voici un contenu de carte par défaut. Vous pouvez le personnaliser en utilisant les props.",
      },
      source: {
        type: String,
        default: "Source de l'information",
      },
    },
  };
  </script>
  
  <style>
  .text-card {
    background-color: var(--color-white-off);
    color: var(--color-blue-deep);
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    padding: 20px;
    margin: 10px 0;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    width: 250px;
  }
  
  .text-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 6px 10px rgba(0, 0, 0, 0.15);
  }
  
  .text-card-title {
    font-size: 1.25rem;
    font-weight: bold;
    margin-bottom: 10px;
    color: var(--color-blue-night);
  }
  
  .text-card-content {
    font-size: 1rem;
    line-height: 1.6;
    color: var(--color-blue-deep);
    margin-bottom: 10px;
  }
  
  .text-card-source a {
    font-size: 0.9rem;
    color: var(--color-blue-night);
    text-decoration: none;
  }
  
  .text-card-source a:hover {
    text-decoration: underline;
  }
  </style>
  