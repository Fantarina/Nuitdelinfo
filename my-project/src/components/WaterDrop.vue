<template>
  <div class="water-drop" :style="{ width: size, height: size }">
    <svg
      :width="size"
      :height="size"
      viewBox="0 0 100 150"
      xmlns="http://www.w3.org/2000/svg"
      :style="{ fill: color }"
    >
      <path
        d="M50 0C50 0 0 75 0 100C0 131 22 150 50 150C78 150 100 131 100 100C100 75 50 0 50 0Z"
      />
    </svg>
  </div>
</template>

<script>
export default {
  props: {
    size: {
      type: String,
      default: "100px", // Taille par défaut
    },
    color: {
      type: String,
      default: "var(--color-blue-soft-turquoise)", // Couleur par défaut
    },
  },
};
</script>

<style>
.water-drop {
  display: inline-block;
  transition: transform 0.2s ease;
}

.water-drop:hover {
  transform: scale(1.1); /* Zoom léger au survol */
}
</style>
