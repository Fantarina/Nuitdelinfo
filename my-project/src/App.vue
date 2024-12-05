<template>
  <div class="app-container">
    <header class="header">
      <h1>SheSea</h1>
    </header>

    <main class="content-container">
      <!-- Gouttes humaines à gauche -->
      <div class="section left-section">
        <WaterDrop class="Poumons Humain" @click="toggleCards('Poumons')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Circulation Humain" @click="toggleCards('Circulation')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Regulation Humain" @click="toggleCards('Regulation')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Ecosysteme Humain" @click="toggleCards('Ecosysteme')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Memoire Humain" @click="toggleCards('Memoire')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Profondeur Humain" @click="toggleCards('Profondeur')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Cycle" @click="toggleCards('Cycle')" size="50px" color="var(--color-blue-light)" />
      </div>

      <!-- Cartes au centre -->
      <div class="card-section">
        <div v-if="visibleCards['Poumons']" id="PoumonsOcéans" class="Poumons">
          <TextCard
            title="Poumons Océans"
            content="Les principales fonctions des poumons sont de transférer dans le sang l'oxygène présent dans l'air et d'évacuer dans l'air le dioxyde de carbone présent dans le sang."
            source="https://www.portfrejus.fr/poumon-bleu-de-la-planete/"
          />
        </div>
        <div v-if="visibleCards['Poumons']" id="PoumonsHumain" class="Poumons">
          <TextCard
            title="Poumons Humains"
            content="Les poumons humains transfèrent l'oxygène dans le sang et éliminent le dioxyde de carbone."
            source="https://cancer.ca/fr/cancer-information/cancer-types/lung/what-is-lung-cancer"
          />
        </div>


        <div v-if="visibleCards['Circulation']" id="CirculationOcean" class="Circulation">
          <TextCard
            title="Circulation océanique"
            content="Les courants marins régulent la chaleur des différents continents ainsi que l’humidité de l’air."
            source="https://www.oceanclock.com/fr/blog/13-les-secrets-des-courants-marins"
          />
        </div>
        <div v-if="visibleCards['Circulation']" id="CirculationHumain" class="Circulation">
          <TextCard
            title="Appareil circulatoire humain"
            content="Les rôles du système circulatoire sont les suivants. Transporter les gaz respiratoires, les nutriments et les déchets. Participer aux échanges gazeux, aux échanges de nutriments et de déchets entre les cellules et le sang."
            source="https://www.alloprof.qc.ca/fr/eleves/bv/sciences/le-systeme-circulatoire-et-son-anatomie"
          />
        </div>


        <div v-if="visibleCards['Regulation']" id="RegThermOcean" class="Regulation">
          <TextCard
            title="Régulation thermique par l'océan"
            content="L'océan agit comme un régulateur thermique global, absorbant et redistribuant la chaleur solaire pour stabiliser les températures planétaires."
            source="https://www.afd.fr/fr/actualites/locean-regulateur-du-climat-et-foyer-de-la-biodiversite"
          />
        </div>
        <div v-if="visibleCards['Regulation']" id="RegThermHomme" class="Regulation">
          <TextCard
            title="Régulation thermique chez l'homme"
            content="Le corps maintient une température constante grâce à des mécanismes comme la transpiration ou les frissons."
            source="https://www.sciencesetavenir.fr/sante/comment-fonctionne-la-thermoregulation-chez-l-etre-humain_165495"
          />
        </div>


        <div v-if="visibleCards['Ecosysteme']" id="EcoOcean" class="Ecosysteme">
          <TextCard
            title="Ecosystème Marin"
            content="L'océan est un écosystème complexe et varié, abritant une diversité impressionnante d'espèces, des microorganismes aux grandes créatures marines."
            source="https://planet-vie.ens.fr/thematiques/ecologie/biodiversite/la-biodiversite-dans-l-ocean"
          />
        </div>
        <div v-if="visibleCards['Ecosysteme']" id="EcoHomme" class="Ecosysteme">
          <TextCard
            title="Microbiome humain"
            content="Le microbiome humain abrite des milliards de micro-organismes dans le tube digestif, sur la peau, et dans d'autres parties du corps, jouant un rôle crucial pour la santé."
            source="https://www.inrae.fr/alimentation-sante-globale/microbiote_intestinal"
          />
        </div>


        <div v-if="visibleCards['Memoire']" id="MemoireOcean" class="Memoire">
          <TextCard
            title="Mémoire de l'Océan"
            content="Les sédiments marins et les formations géologiques enregistrent l’histoire de la Terre, y compris les changements climatiques et les activités tectoniques."
            source="https://www.futura-sciences.com/planete/questions-reponses/geologie-retrace-t-on-histoire-tectonique-grace-sediments-15518/"
          />
        </div>
        <div v-if="visibleCards['Memoire']" id="MemoireHumain" class="Memoire">
          <TextCard
            title="Mémoire humaine"
            content="Le cerveau humain stocke des souvenirs et contrôle des comportements à travers des connexions neurologiques."
            source="https://www.science-et-vie.com/cerveau-et-intelligence/souvenirs-cerveau-memoire-cellules-engrammes-neurones-119783.html"
          />
        </div>


        <div v-if="visibleCards['Profondeur']" id="ProfondeurOcean" class="Profondeur">
          <TextCard
            title="Profondeur de l'Océan"
            content="Les abysses de l’océan rappellent les mystères de l’âme humaine : des zones inexplorées, où résident à la fois des richesses insoupçonnées et des monstres cachés (peurs, traumatismes, désirs profonds)."
            source="Nous mêmes"
          />
        </div>
        <div v-if="visibleCards['Profondeur']" id="ProfondeurHumain" class="Profondeur">
          <TextCard
            title="Profondeur humaine"
            content="Tout comme l’océan, l’être humain possède des couches visibles et invisibles. En surface, il ou elle peut paraître calme ou agité, mais en profondeur se trouvent des sentiments et des pensées souvent inaccessibles à première vue."
            source="Nous mêmes"
          />
        </div>

        <div v-if="visibleCards['Cycle']" id="CycleOcean" class="Cycle">
        <TextCard
          title="Cycle Océans"
          content="Lors de la phase folliculaire, qui suit la période menstruelle, les ovaires préparent un nouvel ovule et l'endomètre commence à se régénérer, ce qui symbolise la préparation et la montée en puissance vers l'ovulation \n Lors de l’ovulation, la fertilité est à son apogée. L’ovule alors libéré symbolise le pic de potentialité reproductive et d'énergie biologique. \n Dans sa phase lutéale, qui suit l’ovulation, le corps se prépare soit à soutenir une grossesse, soit à recommencer le cycle. C’est un symbole de transition et de préparation pour un nouveau début. \n Au début du cycle menstruel, la muqueuse utérine est expulsée avec l’ovule non fécondé, et l’utérus en est purifié et renouvelé pour le prochain cycle"
          source="https://mmelovary.com/fr-at/blogs/sante-feminine/pollution-ocean-menstruations"
        />
      </div>
      <div v-if="visibleCards['Cycle']" id="CycleHumain" class="Cycle">
        <TextCard
          title="Cycle Humain"
          content="À marée montante, le flux représente une période de croissance et d'accumulation d'énergie.\n À marée haute, point culminant du flux, l'eau est à son niveau le plus élevé; l’énergie est à son apogée. \n En phase de reflux, l'eau commence à diminuer en hauteur, se préparant tranquillement pour la prochaine marée.\n À marée basse, ou en basse mer, le niveau de l'eau est à son plus bas. L’océan prend comme un moment de repos et de renouveau avant le prochain flux."
          source="https://mmelovary.com/fr-at/blogs/sante-feminine/pollution-ocean-menstruations"
        />
      </div>

      </div>

      <!-- Gouttes océaniques à droite -->
      <div class="section right-section">
        <WaterDrop class="Poumons Ocean" @click="toggleCards('Poumons')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Circulation Ocean" @click="toggleCards('Circulation')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Regulation Ocean" @click="toggleCards('Regulation')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Ecosysteme Ocean" @click="toggleCards('Ecosysteme')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Memoire Ocean" @click="toggleCards('Memoire')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Profondeur Ocean" @click="toggleCards('Profondeur')" size="50px" color="var(--color-blue-light)" />
        <WaterDrop class="Cycle" @click="toggleCards('Cycle')" size="50px" color="var(--color-blue-light)" />
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
        Profondeur: false,
        Cycle: false,
      },
    };
  },
  methods: {
    toggleCards(className) {
      Object.keys(this.visibleCards).forEach(key => {
        this.visibleCards[key] = false;
      });
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
  height: 100vh;
}

.header {
  background-color: var(--color-blue-deep);
  color: var(--color-white-off);
  padding: 10px;
  text-align: center;
}

.content-container {
  display: flex;
  flex: 1;
}

.left-section,
.right-section {
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
  padding: 20px;
}

.Poumons,
.Circulation,
.Regulation,
.Ecosysteme,
.Memoire,
.Profondeur,
.Cycle {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
</style>
