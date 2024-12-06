<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    :width="size"
    :height="size"
    viewBox="0 0 24 24"
    :fill="color"
    @click="$emit('click')"
  >
    <path
      d="M12 2C12 2 4 10 4 14C4 17.866 7.13401 21 11 21C14.866 21 18 17.866 18 14C18 10 12 2 12 2Z"
    ></path>
  </svg>
</template>

<script>
export default {
  props: {
    size: {
      type: String,
      default: "50px",
    },
    color: {
      type: String,
      default: "var(--color-blue-light)",
    },
  },
};
</script>

<style>
svg:hover {
  cursor: pointer;
}
</style>