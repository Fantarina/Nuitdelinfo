<template>
  <div class="app-container">
    <header class="header">
      <h1>Mon Application</h1>
    </header>

    <main class="main-content">
      <div class="section left-section">
        <CirclePoint size="50px" color="var(--color-blue-light)" />
        <CirclePoint size="30px" color="var(--color-blue-soft-turquoise)" borderColor="var(--color-blue-night)" />
        <CirclePoint
          size="40px"
          color="var(--color-blue-night)"
          @click="handleCircleClick"
        >
          <!-- Contenu facultatif -->
          <span style="color: white; font-size: 12px;">A</span>
        </CirclePoint>
      </div>
      <div class="section right-section">
        <TextCard
          title="Points Ronds"
          content="Les points ronds permettent de représenter des indicateurs ou des éléments visuels interactifs."
        />
      </div>
    </main>
  </div>
</template>

<script>
import TextCard from "./components/TextCard.vue";
import CirclePoint from "./components/CirclePoint.vue";

export default {
  components: {
    TextCard,
    CirclePoint,
  },
  methods: {
    handleCircleClick() {
      alert("Cercle cliqué !");
    },
  },
};
</script>
