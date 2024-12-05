<template>
    <div class="text-card">
      <h3 class="text-card-title">
        <span class="title-underline"></span>
        {{ title }}
      </h3>
      <p class="text-card-content">{{ content }}</p>
      <p class="text-card-source">
        <a :href="source" target="_blank" rel="noopener noreferrer" class="styled-link">
          <svg
            class="link-icon"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <path d="M12 2C12 2 4 10 4 14C4 17.866 7.13401 21 11 21C14.866 21 18 17.866 18 14C18 10 12 2 12 2Z"></path>
          </svg>
          <span>En savoir plus</span>
        </a>
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
        default: "#", // Lien par défaut si aucune source n'est passée
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
  
  /* Style du titre */
  .text-card-title {
    font-size: 1.25rem;
    font-weight: bold;
    margin-bottom: 10px;
    color: var(--color-blue-night);
    position: relative;
    padding-top: 0.5rem; 
    text-transform: uppercase;
  }
  
  .title-underline {
    position: absolute;
    top: 0;
    left: 0;
    width: 40px; 
    height: 3px; 
    background-color: var(--color-blue-light);
    border-radius: 2px; 
  }
  
  .text-card-content {
    font-size: 1rem;
    line-height: 1.6;
    color: var(--color-blue-deep);
  }
  
 
  .text-card-source {
    text-align: center;
    margin-top: 10px;
  }
  
  .styled-link {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    height: 2.2rem;
    padding: 0 1rem;
    border: 0.1rem solid var(--color-blue-light); 
    border-radius: 22px;
    color: var(--color-blue-light); 
    font-size: 0.7rem;
    font-weight: 500;
    text-transform: uppercase;
    white-space: nowrap;
    text-decoration: none;
    background-color: transparent;
    transition: transform 0.5s ease, background-color 0.25s ease, border-color 0.25s ease, color 0.25s ease;
  }
  
  .styled-link:hover {
    background-color: var(--color-blue-light);
    color: #fff; 
    border-color: var(--color-blue-light);
  }
  
  .link-icon {
    width: 1rem;
    height: 1rem;
    margin-right: 0.2rem;
    transition: color 0.25s ease;
    stroke: var(--color-blue-light);
  }
  
  .styled-link:hover .link-icon {
    stroke: #fff; /* Change la couleur de l'icône au survol */
  }
  </style>
  