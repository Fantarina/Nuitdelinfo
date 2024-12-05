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
      <div class="section right-section">
        <TextCard
          source="Points Ronds"
          content="Les points ronds permettent de représenter des indicateurs ou des éléments visuels interactifs."
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
