<template>
  <div class="app-container">
    <header class="header">
      <h1>SheSea</h1>
    </header>

    <main class="main-content">
      <!-- Gouttes associées à chaque classe -->
      <div class="section left-section">
        <WaterDrop class="Poumons" @click="toggleCards('Poumons')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Circulation" @click="toggleCards('Circulation')" size="50px" color="var(--color-blue-deep)" />
        <WaterDrop class="Regulation" @click="toggleCards('Regulation')" size="50px" color="var(--color-blue-soft-turquoise)" />
        <WaterDrop class="Ecosysteme" @click="toggleCards('Ecosysteme')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Memoire" @click="toggleCards('Memoire')" size="50px" color="var(--color-blue-deep)" />
      </div>

      <!-- Cartes associées aux gouttes -->
      <div v-if="visibleCards['Poumons']" id="Poumonsoceans" class="Poumons">
        <TextCard
          title="Poumons Océans"
          content="Ils servent de système respiratoire de la Terre, produisant de l’oxygène pour la vie et absorbant le dioxyde de carbone et les déchets."
          source="https://www.raceforwater.org/fr/"
        />
      </div>

      <div v-if="visibleCards['Circulation']" id="CirculationHumain" class="Circulation">
        <TextCard
          title="Appareil circulatoire humain"
          content="Les rôles du système circulatoire sont les suivants. Transporter les gaz respiratoires, les nutriments et les déchets. Participer aux échanges gazeux, aux échanges de nutriments et de déchets entre les cellules et le sang."
          source="https://www.raceforwater.org/fr/"
        />
      </div>
      <div v-if="visibleCards['Circulation']" id="CirculationOcean" class="Circulation">
        <TextCard
          title="Circulation océanique"
          content="Les courants marins régulent la chaleur des différents continents ainsi que l’humidité de l’air."
          source="https://www.raceforwater.org/fr/"
        />
      </div>

      <div v-if="visibleCards['Regulation']" id="RegThermHomme" class="Regulation">
        <TextCard
          title="Régulation thermique chez l'homme"
          content="Le corps maintient une température constante grâce à des mécanismes comme la transpiration ou les frissons."
          source="https://www.raceforwater.org/fr/"
        />
      </div>
      <div v-if="visibleCards['Regulation']" id="RegThermOcean" class="Regulation">
        <TextCard
          title="Régulation thermique par l'océan"
          content="L'océan agit comme un régulateur thermique global, absorbant et redistribuant la chaleur solaire pour stabiliser les températures planétaires."
          source="https://www.raceforwater.org/fr/"
        />
      </div>

      <div v-if="visibleCards['Ecosysteme']" id="EcoHomme" class="Ecosysteme">
        <TextCard
          title="Microbiome humain"
          content="Le microbiome humain abrite des milliards de micro-organismes dans le tube digestif, sur la peau, et dans d'autres parties du corps, jouant un rôle crucial pour la santé."
          source="https://www.raceforwater.org/fr/"
        />
      </div>
      <div v-if="visibleCards['Ecosysteme']" id="EcoOcean" class="Ecosysteme">
        <TextCard
          title="Ecosystème Marin"
          content="L'océan est un écosystème complexe et varié, abritant une diversité impressionnante d'espèces, des microorganismes aux grandes créatures marines."
          source="https://www.raceforwater.org/fr/"
        />
      </div>

      <div v-if="visibleCards['Memoire']" id="MemoireHumain" class="Memoire">
        <TextCard
          title="Mémoire humaine"
          content="Le cerveau humain stocke des souvenirs et contrôle des comportements à travers des connexions neurologiques."
          source="https://www.raceforwater.org/fr/"
        />
      </div>
      <div v-if="visibleCards['Memoire']" id="MemoireOcean" class="Memoire">
        <TextCard
          title="Mémoire de l'Océan"
          content="Les sédiments marins et les formations géologiques enregistrent l’histoire de la Terre, y compris les changements climatiques et les activités tectoniques."
          source="https://www.raceforwater.org/fr/"
        />
      </div>
    </main>
  </div>
</template>

<script>
import TextCard from "./components/TextCard.vue";
import WaterDrop from "./components/WaterDrop.vue";

export default {
  components: {
    TextCard,
    WaterDrop,
  },
  data() {
    return {
      visibleCards: {
        Poumons: false,
        Circulation: false,
        Regulation: false,
        Ecosysteme: false,
        Memoire: false,
      },
    };
  },
  methods: {
    toggleCards(className) {
      // Toggle la visibilité des cartes associées à la classe donnée
      this.visibleCards[className] = !this.visibleCards[className];
    },
  },
};
</script>

<style>
:root {
  --color-blue-deep: #080E1E;
  --color-blue-night: #014F86;
  --color-blue-light: #56B4D3;
  --color-blue-soft-turquoise: #88E0EF;
  --color-white-off: #F1F1F1;
}

.app-container {
  font-family: 'Roboto', sans-serif;
  display: flex;
  flex-direction: column;
}

.header {
  background-color: var(--color-blue-deep);
  color: var(--color-white-off);
  text-align: start;
}

.main-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  padding: 20px;
}

.Poumons,
.Circulation,
.Regulation,
.Ecosysteme,
.Memoire {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
</style>
