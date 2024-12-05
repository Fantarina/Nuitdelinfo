<template>
  <div class="circle-point" :style="circleStyle" @click="onClick">
    <slot></slot> <!-- Permet d'ajouter du contenu si nécessaire -->
  </div>
</template>

<script>
export default {
  props: {
    size: {
      type: String,
      default: "40px", // Taille par défaut
    },
    color: {
      type: String,
      default: "var(--color-blue-soft-turquoise)", // Couleur par défaut
    },
    borderColor: {
      type: String,
      default: "var(--color-blue-deep)", // Bordure par défaut
    },
    onClick: {
      type: Function,
      default: () => {}, // Action au clic, facultative
    },
  },
  computed: {
    circleStyle() {
      return {
        width: this.size,
        height: this.size,
        backgroundColor: this.color,
        border: `2px solid ${this.borderColor}`,
        borderRadius: "50%",
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        cursor: this.onClick ? "pointer" : "default",
        transition: "transform 0.2s ease",
      };
    },
  },
};
</script>

<style>
.circle-point:hover {
  transform: scale(1.1); /* Agrandissement au survol */
}
</style>
