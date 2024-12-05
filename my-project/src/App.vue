<template>
  <div class="app-container">
    <!-- En-tête -->
    <header class="header">
      <h1>Mon Application</h1>
    </header>

    <!-- Contenu principal -->
    <main class="main-content">
      <!-- Section gauche -->
      <div class="section left-section">
        <HexSection title="Section Gauche" :items="leftItems" />
      </div>

      <!-- Section droite -->
      <div class="section right-section">
        <HexSection title="Section Droite" :items="rightItems" />
      </div>
    </main>
  </div>
</template>

<script>
import HexSection from './components/HexSection.vue';

export default {
  components: {
    HexSection,
  },
  data() {
    return {
      leftItems: [
        { id: 1, text: 'Élément 1' },
        { id: 2, text: 'Élément 2' },
      ],
      rightItems: [
        { id: 3, text: 'Élément 3' },
        { id: 4, text: 'Élément 4' },
      ],
    };
  },
};
</script>

<style>
.app-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.header {
  background: #f4f4f4;
  padding: 10px;
  text-align: center;
}

.main-content {
  display: flex;
  flex: 1;
}

.section {
  flex: 1;
  padding: 20px;
}

.left-section {
  background: #eef;
}

.right-section {
  background: #ffe;
}
</style>
