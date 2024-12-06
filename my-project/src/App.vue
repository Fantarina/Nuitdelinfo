<template>
  <div class="app-container">
    <header class="header">
      <h1>SheSea</h1>
    </header>

    <main class="content-container">
      <div class="section left-section">
        <WaterDrop
          class="Poumons Humain"
          :class="{ 'active-drop': isActive('Poumons') }"
          @click="handleClick('Poumons', 'Humain')"
          size="50px"
          :color="isActive('Poumons') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Circulation Humain"
          :class="{ 'active-drop': isActive('Circulation') }"
          @click="handleClick('Circulation', 'Humain')"
          size="50px"
          :color="isActive('Circulation') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
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
        setTimeout(() => {
          this.visibleCards[oceanKey] = true;
        }, 2000);
      } else if (type === "Ocean") {
        this.visibleCards[oceanKey] = true;
        setTimeout(() => {
          this.visibleCards[humanKey] = true;
        }, 2000);
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
  --color-blue-deep: #080E1E;
  --color-blue-light: #56B4D3;
}

.app-container {
  font-family: "Roboto", sans-serif;
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.header {
  background-color: var(--color-blue-deep);
  color: #fff;
  text-align: center;
  padding: 10px;
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
    transform: translateX(-500px) scale(0.9);
    opacity: 0;
  }
  to {
    transform: translateX(-250px) scale(1); 
    opacity: 1;
  }
}


@keyframes slide-in-right {
  from {
    transform: translateX(500px) scale(0.9);
    opacity: 0;
  }
  to {
    transform: translateX(250px) scale(1); 
    opacity: 1;
  }
}

.active-drop {
  fill: var(--color-blue-deep) !important;
  transition: fill 0.3s ease;
}
</style>
