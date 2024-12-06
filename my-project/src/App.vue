<template>
  <div class="app-container">

    <main class="content-container">
      <div class="section left-section">
        <WaterDrop
          class="Poumons Humain precise-poumon"
          :class="{ 'active-drop': isActive('Poumons') }"
          @click="handleClick('Poumons', 'Humain')"
          size="50px"
          :color="isActive('Poumons') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Circulation Humain precise-circulation"
          :class="{ 'active-drop': isActive('Circulation') }"
          @click="handleClick('Circulation', 'Humain')"
          size="50px"
          :color="isActive('Circulation') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Ecosysteme Humain precise-ecosysteme buzzer"
          :class="{ 'active-drop': isActive('Ecosysteme') }"
          @click="handleClick('Ecosysteme', 'Humain')"
          size="50px"
          :color="isActive('Ecosysteme') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Memoire Humain precise-memoire"
          :class="{ 'active-drop': isActive('Memoire') }"
          @click="handleClick('Memoire', 'Humain')"
          size="50px"
          :color="isActive('Memoire') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Profondeur Humain precise-profondeur"
          :class="{ 'active-drop': isActive('Profondeur') }"
          @click="handleClick('Profondeur', 'Humain')"
          size="50px"
          :color="isActive('Profondeur') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Cycle Humain"
          :class="{ 'active-drop': isActive('Cycle') }"
          @click="handleClick('Cycle', 'Humain')"
          size="50px"
          :color="isActive('Cycle') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
      </div>

      <div class="card-section">
        <div
          v-if="visibleCards.PoumonsHumain"
          class="card human-card fade-in"
        >
          <TextCard
            title="Poumons Humains"
            content="Les poumons humains transfèrent l'oxygène dans le sang et éliminent le dioxyde de carbone."
            source="https://cancer.ca/fr/cancer-information/cancer-types/lung/what-is-lung-cancer"
          />
        </div>
        <div
          v-if="visibleCards.PoumonsOcean"
          class="card ocean-card fade-in"
        >
          <TextCard
            title="Poumons Océans"
            content="Les principales fonctions des poumons sont de transférer dans le sang l'oxygène présent dans l'air et d'évacuer dans l'air le dioxyde de carbone présent dans le sang."
            source="https://www.portfrejus.fr/poumon-bleu-de-la-planete/"
          />
        </div>
        <div
          v-if="visibleCards.CirculationHumain"
          class="card human-card fade-in"
        >
          <TextCard
            title="Appareil circulatoire humain"
            content="Les rôles du système circulatoire sont les suivants. Transporter les gaz respiratoires, les nutriments et les déchets. Participer aux échanges gazeux, aux échanges de nutriments et de déchets entre les cellules et le sang."
            source="https://www.alloprof.qc.ca/fr/eleves/bv/sciences/le-systeme-circulatoire-et-son-anatomie"
          />
        </div>
        <div
          v-if="visibleCards.CirculationOcean"
          class="card ocean-card fade-in"
        >
          <TextCard
            title="Circulation océanique"
            content="Les courants marins régulent la chaleur des différents continents ainsi que l’humidité de l’air."
            source="https://www.oceanclock.com/fr/blog/13-les-secrets-des-courants-marins"
          />
        </div>

        <div v-if="visibleCards.EcosystemeHumain" class="card human-card fade-in">
          <TextCard
            title="Microbiome humain"
            content="Le microbiome humain abrite des milliards de micro-organismes dans le tube digestif, sur la peau, et dans d'autres parties du corps, jouant un rôle crucial pour la santé."
            source="https://www.inrae.fr/alimentation-sante-globale/microbiote_intestinal"
          />
        </div>
        <div v-if="visibleCards.EcosystemeOcean" class="card ocean-card fade-in">
          <TextCard
            title="Ecosystème Marin"
            content="L'océan est un écosystème complexe et varié, abritant une diversité impressionnante d'espèces, des microorganismes aux grandes créatures marines."
            source="https://planet-vie.ens.fr/thematiques/ecologie/biodiversite/la-biodiversite-dans-l-ocean"
          />
        </div>

        <div v-if="visibleCards.MemoireHumain" class="card human-card fade-in">
          <TextCard
            title="Mémoire humaine"
            content="Le cerveau humain stocke des souvenirs et contrôle des comportements à travers des connexions neurologiques."
            source="https://www.science-et-vie.com/cerveau-et-intelligence/souvenirs-cerveau-memoire-cellules-engrammes-neurones-119783.html"
          />
        </div>
        <div v-if="visibleCards.MemoireOcean" class="card ocean-card fade-in">
          <TextCard
            title="Mémoire de l'Océan"
            content="Les sédiments marins et les formations géologiques enregistrent l’histoire de la Terre, y compris les changements climatiques et les activités tectoniques."
            source="https://www.futura-sciences.com/planete/questions-reponses/geologie-retrace-t-on-histoire-tectonique-grace-sediments-15518/"
          />
        </div>

        <div v-if="visibleCards.ProfondeurHumain" class="card human-card fade-in">
          <TextCard
            title="Profondeur humaine"
            content="Tout comme l’océan, l’être humain possède des couches visibles et invisibles. En surface, il ou elle peut paraître calme ou agité, mais en profondeur se trouvent des sentiments et des pensées souvent inaccessibles à première vue."
            source="Nous mêmes"
          />
        </div>
        <div v-if="visibleCards.ProfondeurOcean" class="card ocean-card fade-in">
          <TextCard
            title="Profondeur de l'Océan"
            content="Les abysses de l’océan rappellent les mystères de l’âme humaine : des zones inexplorées, où résident à la fois des richesses insoupçonnées et des monstres cachés (peurs, traumatismes, désirs profonds)."
            source="Nous mêmes"
          />
        </div>

        <div v-if="visibleCards.CycleHumain" class="card human-card fade-in">
          <TextCard
            title="Cycle Femme"
            content="La phase folliculaire marque la préparation de l'ovule et la régénération de l'endomètre. Lors de l’ovulation, la fertilité atteint son apogée. La phase lutéale prépare le corps à une grossesse ou un nouveau cycle. Pendant les règles, l’utérus se purifie pour un nouveau départ."
            source="https://mmelovary.com/fr-at/blogs/sante-feminine/pollution-ocean-menstruations"
          />
        </div>
        <div v-if="visibleCards.CycleOcean" class="card ocean-card fade-in">
          <TextCard
            title="Cycles Océans"
            content="À marée montante, l'énergie croît. À marée haute, elle atteint son pic. En reflux, elle diminue pour préparer la prochaine marée. À marée basse, l’océan se renouvelle avant un nouveau cycle."
            source="https://mmelovary.com/fr-at/blogs/sante-feminine/pollution-ocean-menstruations"
          />
        </div>
        <div class="audio-card-section">
          <audio controls>
            <source src="/audio/PODCAST-AUDIO-Flo.m4a" type="audio/mpeg" />
            <p>
              Votre navigateur ne prend pas en charge l'audio HTML5. Voici un
              <a href="PODCAST-AUDIO-Flo.m4a">lien vers le fichier audio</a> à la place.
            </p>
          </audio>
        </div>
      </div>

      <div class="section right-section">
        <WaterDrop
          class="Poumons Ocean"
          :class="{ 'active-drop': isActive('Poumons') }"
          @click="handleClick('Poumons', 'Ocean')"
          size="50px"
          :color="isActive('Poumons') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Circulation Ocean"
          :class="{ 'active-drop': isActive('Circulation') }"
          @click="handleClick('Circulation', 'Ocean')"
          size="50px"
          :color="isActive('Circulation') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Ecosysteme Ocean"
          :class="{ 'active-drop': isActive('Ecosysteme') }"
          @click="handleClick('Ecosysteme', 'Ocean')"
          size="50px"
          :color="isActive('Ecosysteme') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Memoire Ocean"
          :class="{ 'active-drop': isActive('Memoire') }"
          @click="handleClick('Memoire', 'Ocean')"
          size="50px"
          :color="isActive('Memoire') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Profondeur Ocean"
          :class="{ 'active-drop': isActive('Profondeur') }"
          @click="handleClick('Profondeur', 'Ocean')"
          size="50px"
          :color="isActive('Profondeur') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Cycle Ocean"
          :class="{ 'active-drop': isActive('Cycle') }"
          @click="handleClick('Cycle', 'Ocean')"
          size="50px"
          :color="isActive('Cycle') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
      </div>
      
    </main>
  </div>
</template>

<script>
import WaterDrop from "./components/WaterDrop.vue";
import TextCard from "./components/TextCard.vue";

export default {
  components: {
    WaterDrop,
    TextCard,
  },
  data() {
    return {
      visibleCards: {
        PoumonsHumain: false,
        PoumonsOcean: false,
        CirculationHumain: false,
        CirculationOcean: false,
      },
      activeDrop: null,
    };
  },
  methods: {
    handleClick(category, type) {
      const humanKey = `${category}Humain`;
      const oceanKey = `${category}Ocean`;

      Object.keys(this.visibleCards).forEach((key) => {
        this.visibleCards[key] = false;
      });

      this.activeDrop = category;

      if (type === "Humain") {
        this.visibleCards[humanKey] = true;
        this.visibleCards[oceanKey] = true;
      } else if (type === "Ocean") {
        this.visibleCards[oceanKey] = true;
        this.visibleCards[humanKey] = true;
      }
    },
    isActive(category) {
      return this.activeDrop === category;
    },
  },
};
</script>

<style>
:root {
  --color-blue-deep: #56B4D3;
  --color-blue-light: #080E1E;
}

.app-container {
  font-family: "Roboto", sans-serif;
  display: flex;
  flex-direction: column;
  height: 100vh;
}

body{
  margin: 0px;
  padding: 0px;
}

.content-container {
  display: flex;
  flex: 1;
}

.section {
  width: 20%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.card-section {
  flex: 1;
  display: flex;
  justify-content:center;
  position: relative; 
  width: 100%; 
  height: 100%; 
}

.card {
  position: absolute; 
  top: 50%; 
  transform: translateY(-50%); 
  opacity: 0;
  transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
}

.fade-in {
  opacity: 1;
}

.human-card {
  animation: slide-in-left 0.8s ease-in-out;
  left: calc(50% - 450px); 
}

.ocean-card {
  animation: slide-in-right 0.8s ease-in-out;
  left: calc(50% + 250px); 
}

@keyframes slide-in-left {
  from {
    transform: translateX(-500px) translateY(0) scale(0.9);
    opacity: 0;
  }
  to {
    transform: translateX(-250px) translateY(500) scale(1); 
    opacity: 1;
  }
}


@keyframes slide-in-right {
  from {
    transform: translateX(500px) translateY(0)scale(0.9);
    opacity: 0;
  }
  to {
    transform: translateX(250px) translateY(500) scale(1); 
    opacity: 1;
  }
}

.active-drop {
  fill: var(--color-blue-deep) !important;
  transition: fill 0.3s ease;
}

@media (max-width: 1550px) {
  .card {
    position: static; 
    transform: none; 
  }

  .card-section {
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
    margin-top: 10px;
  }
}

@media (max-width: 768px) {
  .content-container {
    flex-direction: column; 
    align-items: center; 
  }

  .section {
    width: 100%; 
    margin-bottom: 15px; 
  }

  .card-section {
    flex-direction: column; 
    gap: 15px; 
    padding: 10px;
    align-items: center;
    justify-content: center;
  }

  .card {
    width: 90%;
    max-width: 350px; 
    position: static;
    transform: none; 
  }

}


@media (max-width: 480px) {
  .header {
    font-size: 16px; 
    padding: 5px; 
  }

  .card {
    width: 100%; 
    padding: 10px; 
  }
  .card-section {
    gap: 10px; 
  }
}

.section.left-section {
  background-image: url('@/assets/images/fullbody2.jpeg');
  background-size: contain; 
  background-repeat: no-repeat;
  background-position: center; 
  position: relative;
  width: 400px;
  height: 100%; 
  margin: 0 auto;
}
.section.card-section {
  background-image: url('@/assets/images/fond.jpg'); /* Image d'arrière-plan */
  background-size: cover; /* Pour couvrir toute la surface de la div */
  background-position: center; /* Centrer l'image de fond */
}
.section.right-section {
  background-image: url('@/assets/images/island.jpg'); /* Image d'arrière-plan */
  background-size: cover; /* Pour couvrir toute la surface de la div */
  background-position: center; /* Centrer l'image de fond */
}

.precise-poumon {
  position: absolute; 
  top: 30%;
  left: 43%; 
  transform: translate(-50%, -50%); 
  cursor: pointer;
}

.precise-circulation {
  position: absolute; 
  top: 35%; 
  left: 50%; 
  transform: translate(-50%, -50%); 
  cursor: pointer;
}

.precise-ecosysteme {
  position: absolute; 
  top: 40%;
  left: 58%; 
  transform: translate(-50%, -50%); 
  cursor: pointer;
}

.precise-memoire {
  position: absolute; 
  top: 5%;
  left: 56%; 
  transform: translate(-50%, -50%); 
  cursor: pointer;
}

.precise-profondeur {
  position: absolute; 
  top: 5%;
  left: 46%; 
  transform: translate(-50%, -50%); 
  cursor: pointer;
}    
.audio-card-section {
  display: flex;
  flex-direction: column-reverse;
  margin-bottom: 1em;
}
audio{
  border-radius: 10px;
  background-color: #080E1E;
}

  @keyframes zoom-effect {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.5); 
  }
  100% {
    transform: scale(1);
  }
}

.buzzer {
  animation: zoom-effect 1.5s infinite; 
  cursor: pointer; 
}
</style>
