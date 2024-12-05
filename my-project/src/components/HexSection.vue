<template>
    <div class="hex-section">
      <h2>{{ title }}</h2>
      <div v-for="item in items" :key="item.id" class="hex-item">
        <div class="hexagon"></div>
        <p>{{ item.text }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      items: Array,
    },
  };
  </script>
  
  <style>
  .hex-section {
    display: flex;
    flex-direction: column;
  }
  
  .hex-item {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }
  
  .hexagon {
    width: 50px;
    height: 50px;
    background: #ccc;
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    margin-right: 10px;
  }
  </style>
  