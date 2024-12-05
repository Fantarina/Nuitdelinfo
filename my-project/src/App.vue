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
        <WaterDrop class="Profondeur" @click="toggleCards('Prodondeur')" size="50px" color="var(--color-blue-deep)" />
      </div>

      <!-- Cartes associées aux gouttes -->
      <div v-if="visibleCards['Poumons']" id="Poumonsoceans" class="Poumons">
        <TextCard
          title="Poumons Océans"
          content="Les principales fonctions des poumons sont de transférer dans le sang l'oxygène présent dans l'air et d'évacuer dans l'air le dioxyde de carbone présent dans le sang"
          source="https://www.portfrejus.fr/poumon-bleu-de-la-planete/"
        />
      </div>

      <div v-if="visibleCards['Poumons']" id="Poumonhumains" class="Poumons">
        <TextCard
          title="Poumons Océans"
          content="Les principales fonctions des poumons sont de transférer dans le sang l'oxygène présent dans l'air et d'évacuer dans l'air le dioxyde de carbone présent dans le sang"
          source="https://cancer.ca/fr/cancer-information/cancer-types/lung/what-is-lung-cancer."
        />
      </div>

      <div v-if="visibleCards['Circulation']" id="CirculationHumain" class="Circulation">
        <TextCard
          title="Appareil circulatoire humain"
          content="Les rôles du système circulatoire sont les suivants. Transporter les gaz respiratoires, les nutriments et les déchets. Participer aux échanges gazeux, aux échanges de nutriments et de déchets entre les cellules et le sang."
          source="https://www.alloprof.qc.ca/fr/eleves/bv/sciences/le-systeme-circulatoire-et-son-anatomie"
        />
      </div>
      <div v-if="visibleCards['Circulation']" id="CirculationOcean" class="Circulation">
        <TextCard
          title="Circulation océanique"
          content="Les courants marins régulent la chaleur des différents continents ainsi que l’humidité de l’air."
          source="https://www.oceanclock.com/fr/blog/13-les-secrets-des-courants-marins"
        />
      </div>

      <div v-if="visibleCards['Regulation']" id="RegThermHomme" class="Regulation">
        <TextCard
          title="Régulation thermique chez l'homme"
          content="Le corps maintient une température constante grâce à des mécanismes comme la transpiration ou les frissons."
          source="https://www.sciencesetavenir.fr/sante/comment-fonctionne-la-thermoregulation-chez-l-etre-humain_165495"
        />
      </div>
      <div v-if="visibleCards['Regulation']" id="RegThermOcean" class="Regulation">
        <TextCard
          title="Régulation thermique par l'océan"
          content="L'océan agit comme un régulateur thermique global, absorbant et redistribuant la chaleur solaire pour stabiliser les températures planétaires."
          source="https://www.afd.fr/fr/actualites/locean-regulateur-du-climat-et-foyer-de-la-biodiversite"
        />
      </div>

      <div v-if="visibleCards['Ecosysteme']" id="EcoHomme" class="Ecosysteme">
        <TextCard
          title="Microbiome humain"
          content="Le microbiome humain abrite des milliards de micro-organismes dans le tube digestif, sur la peau, et dans d'autres parties du corps, jouant un rôle crucial pour la santé."
          source="https://www.inrae.fr/alimentation-sante-globale/microbiote_intestinal"
        />
      </div>
      <div v-if="visibleCards['Ecosysteme']" id="EcoOcean" class="Ecosysteme">
        <TextCard
          title="Ecosystème Marin"
          content="L'océan est un écosystème complexe et varié, abritant une diversité impressionnante d'espèces, des microorganismes aux grandes créatures marines."
          source="https://planet-vie.ens.fr/thematiques/ecologie/biodiversite/la-biodiversite-dans-l-ocean"
        />
      </div>

      <div v-if="visibleCards['Memoire']" id="MemoireHumain" class="Memoire">
        <TextCard
          title="Mémoire humaine"
          content="Le cerveau humain stocke des souvenirs et contrôle des comportements à travers des connexions neurologiques."
          source="https://www.science-et-vie.com/cerveau-et-intelligence/souvenirs-cerveau-memoire-cellules-engrammes-neurones-119783.html"
        />
      </div>
      <div v-if="visibleCards['Memoire']" id="MemoireOcean" class="Memoire">
        <TextCard
          title="Mémoire de l'Océan"
          content="Les sédiments marins et les formations géologiques enregistrent l’histoire de la Terre, y compris les changements climatiques et les activités tectoniques."
          source="https://www.futura-sciences.com/planete/questions-reponses/geologie-retrace-t-on-histoire-tectonique-grace-sediments-15518/"
        />
      </div>
      <div v-if="visibleCards['Profondeur']" id="ProfondeurHumain" class="Profondeur">
        <TextCard
          title="Profondeur humaine"
          content="Tout comme l’océan, l’être humain possède des couches visibles et invisibles. En surface, il ou elle peut paraître calme ou agité, mais en profondeur se trouvent des sentiments et des pensées souvent inaccessibles à première vue."
          source="Nous mêmes"
        />
      </div>
      <div v-if="visibleCards['Profondeur']" id="ProfondeurOcean" class="Profondeur">
        <TextCard
          title="Profondeur de l'Océan"
          content="Les abysses de l’océan rappellent les mystères de l’âme humaine : des zones inexplorées, où résident à la fois des richesses insoupçonnées et des monstres cachés (peurs, traumatismes, désirs profonds)."
          source="Nous mêmes"
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
      // Réinitialiser toutes les cartes visibles
      Object.keys(this.visibleCards).forEach(key => {
        this.visibleCards[key] = false;
      });

      // Activer uniquement la carte associée à la classe cliquée
      this.visibleCards[className] = true;
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
