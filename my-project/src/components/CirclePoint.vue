<template>
  <div class="circle-point" :style="circleStyle" @click="onClick">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    size: {
      type: String,
      default: "40px", 
    },
    color: {
      type: String,
      default: "var(--color-blue-soft-turquoise)", 
    },
    borderColor: {
      type: String,
      default: "var(--color-blue-deep)", 
    },
    onClick: {
      type: Function,
      default: () => {}, 
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
  transform: scale(1.1); 
}
</style>
