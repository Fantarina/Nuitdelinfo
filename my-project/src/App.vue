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
        <WaterDrop
          class="Regulation Humain"
          :class="{ 'active-drop': isActive('Regulation') }"
          @click="handleClick('Regulation', 'Humain')"
          size="50px"
          :color="isActive('Regulation') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Ecosysteme Humain"
          :class="{ 'active-drop': isActive('Ecosysteme') }"
          @click="handleClick('Ecosysteme', 'Humain')"
          size="50px"
          :color="isActive('Ecosysteme') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Memoire Humain"
          :class="{ 'active-drop': isActive('Memoire') }"
          @click="handleClick('Memoire', 'Humain')"
          size="50px"
          :color="isActive('Memoire') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
        />
        <WaterDrop
          class="Profondeur Humain"
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
        <div v-if="visibleCards.PoumonsHumain" class="card fade-in">
          <TextCard
            title="Poumons Humains"
            content="Les poumons humains transfèrent l'oxygène dans le sang et éliminent le dioxyde de carbone."
            source="https://cancer.ca/fr/cancer-information/cancer-types/lung/what-is-lung-cancer"
          />
        </div>
        <div v-if="visibleCards.PoumonsOcean" class="card fade-in">
          <TextCard
            title="Poumons Océans"
            content="Les principales fonctions des poumons sont de transférer dans le sang l'oxygène présent dans l'air et d'évacuer dans l'air le dioxyde de carbone présent dans le sang."
            source="https://www.portfrejus.fr/poumon-bleu-de-la-planete/"
          />
        </div>
        <div v-if="visibleCards.CirculationHumain" class="card fade-in">
          <TextCard
            title="Appareil circulatoire humain"
            content="Les rôles du système circulatoire sont les suivants. Transporter les gaz respiratoires, les nutriments et les déchets. Participer aux échanges gazeux, aux échanges de nutriments et de déchets entre les cellules et le sang."
            source="https://www.alloprof.qc.ca/fr/eleves/bv/sciences/le-systeme-circulatoire-et-son-anatomie"
          />
        </div>
        <div v-if="visibleCards.CirculationOcean" class="card fade-in">
          <TextCard
            title="Circulation océanique"
            content="Les courants marins régulent la chaleur des différents continents ainsi que l’humidité de l’air."
            source="https://www.oceanclock.com/fr/blog/13-les-secrets-des-courants-marins"
          />
        </div>
        <div v-if="visibleCards.RegulationHumain" class="card fade-in">
          <TextCard
            title="Régulation thermique chez l'homme"
            content="Le corps maintient une température constante grâce à des mécanismes comme la transpiration ou les frissons."
            source="https://www.sciencesetavenir.fr/sante/comment-fonctionne-la-thermoregulation-chez-l-etre-humain_165495"
          />
        </div>
        <div v-if="visibleCards.RegulationOcean" class="card fade-in">
          <TextCard
            title="Régulation thermique par l'océan"
            content="L'océan agit comme un régulateur thermique global, absorbant et redistribuant la chaleur solaire pour stabiliser les températures planétaires."
            source="https://www.afd.fr/fr/actualites/locean-regulateur-du-climat-et-foyer-de-la-biodiversite"
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
        <WaterDrop
          class="Regulation Ocean"
          :class="{ 'active-drop': isActive('Regulation') }"
          @click="handleClick('Regulation', 'Ocean')"
          size="50px"
          :color="isActive('Regulation') ? 'var(--color-blue-deep)' : 'var(--color-blue-light)'"
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
        RegulationHumain: false,
        RegulationOcean: false,
        EcosystemeHumain: false,
        EcosystemeOcean: false,
        MemoireHumain: false,
        MemoireOcean: false,
        ProfondeurHumain: false,
        ProfondeurOcean: false,
        CycleHumain: false,
        CycleOcean: false,
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
  justify-content: center;
  align-items: center;
}

.card {
  opacity: 0;
  transform: scale(0.95);
  transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
}

.card.fade-in {
  opacity: 1;
  transform: scale(1);
}

.active-drop {
  fill: var(--color-blue-deep) !important;
  transition: fill 0.3s ease;
}
</style>
