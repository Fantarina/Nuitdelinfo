<template>
    <div class="text-card">
      <p class="text-card-content">{{ content }}</p>
      <p class="text-card-source"> <a href="#"> {{ source }} </a> </p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
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
    border-radius: 12px;
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
  
  .text-card-content {
    font-size: 1rem;
    line-height: 1.6;
    color: var(--color-blue-deep);
  }
  </style>
  