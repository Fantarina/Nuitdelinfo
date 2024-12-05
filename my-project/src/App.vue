<template>
  <div class="app-container">
    <header class="header">
      <h1>SheSea</h1>
    </header>

    <main class="main-content">
      <div class="section left-section">
        <CirclePoint size="50px" color="var(--color-blue-light)" @click="handleCircleClick" />
        <CirclePoint size="30px" color="var(--color-blue-soft-turquoise)" borderColor="var(--color-blue-night)" @click="handleCircleClick" />
        <CirclePoint
          size="40px"
          color="var(--color-blue-night)"
          @click="handleCircleClick"
        >
        </CirclePoint>
      
        <!-- Exemple d'utilisation des gouttes SVG -->
        <WaterDrop size="50px" color="var(--color-blue-light)" />
        <WaterDrop size="80px" color="var(--color-blue-deep)" />
        <WaterDrop size="100px" color="var(--color-blue-night)" />
  
      </div>
      <div id="Poumonshomme" class="Poumons">

      </div>
      <div id="Poumonsoceans" class="Poumons">
        <TextCard
          title="Poumons Océans"
          content="Ils servent de système respiratoire de la Terre, produisant de l’oxygène pour la vie et absorbant le dioxyde de carbone et les déchets. Les océans stockent et absorbent le dioxyde de carbone mondial, tandis que le phytoplancton marin génère l’oxygène nécessaire à la survie."
        />
      </div>
      <div id="CirculationHumain" class="Circulation">
        <TextCard
          title="Appareil circulatoire humain"
          content="Les rôles du système circulatoire sont les suivants. Transporter les gaz respiratoires, les nutriments et les déchets. Participer aux échanges gazeux, aux échanges de nutriments et de déchets entre les cellules et le sang."
        />
      </div>
      <div id="CirculationOcean" class="Circulation">
        <TextCard
          title="Circulation océanique"
          content="Les courants marins régulent la chaleur des différents continents ainsi que l’humidité de l’air. La Terre n’étant pas ensoleillée de manière égale, les courants vont redistribuer les énergies solaires des zones chaudes aux zones froides. Par exemple, le courant marin le plus connu, le Gulf Stream, transporte la chaleur des tropiques pour réchauffer l’Europe."
        />
      </div>
      <div id="RegThermHomme" class="Regulation">
        <TextCard
          title="Régulation thermique chez l'homme"
          content="Le corps maintient une température constante grâce à des mécanismes comme la transpiration ou les frissons."
        />
      </div>
      <div id="RegThermHomme" class="Regulation">
        <TextCard
          title="Régulation thermique chez l'homme"
          content="Le corps maintient une température constante grâce à des mécanismes comme la transpiration ou les frissons."
        />
      </div>
      <div id="RegThermOcean" class="Regulation">
        <TextCard
          title="Régulation thermique par l'océan"
          content="L'océan agit comme un régulateur thermique global, absorbant et redistribuant la chaleur solaire pour stabiliser les températures planétaires."
        />
      </div>
      <div id="EcoHomme" class="Ecosysteme">
        <TextCard
          title="Microbiome humain"
          content="Le microbiome humain abrite des milliards de micro-organismes dans le tube digestif, sur la peau, et dans d'autres parties du corps, jouant un rôle crucial pour la santé."
        />
      </div>
      <div id="EcoOcean" class="Ecosysteme">
        <TextCard
          title="Ecosysteme Marin"
          content="L'océan est un écosystème complexe et varié, abritant une diversité impressionnante d'espèces, des microorganismes aux grandes créatures marines."
        />
      </div>
      <div id="MemoireHumain" class="Memoire">
        <TextCard
          title="Mémoire humaine"
          content="Le cerveau humain stocke des souvenirs et contrôle des comportements à travers des connexions neurologiques."
        />
      </div>
      <div id="MemoireOcean" class="Memoire">
        <TextCard
          title="Mémoire de l'Océan"
          content="Les sédiments marins et les formations géologiques enregistrent l’histoire de la Terre, y compris les changements climatiques et les activités tectoniques."
/>
        />
      </div>
    </main>
  </div>
</template>

<style>
:root {
  --color-blue-deep: #013A63;
  --color-blue-night: #014F86;
  --color-blue-light: #56B4D3;
  --color-blue-soft-turquoise: #88E0EF;
  --color-white-off: #F2F2F2;
}
</style>

<script>
import TextCard from "./components/TextCard.vue";
import CirclePoint from "./components/CirclePoint.vue";
import WaterDrop from "./components/WaterDrop.vue";

export default {
  components: {
    TextCard,
    CirclePoint,
    WaterDrop,
  },
  methods: {
    handleCircleClick() {
      alert("Cercle cliqué !");
    },
  },
};
</script>
