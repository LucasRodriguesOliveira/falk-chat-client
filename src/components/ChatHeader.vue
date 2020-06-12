<template>
  <div class="header">
    <div class="title">{{ title }}</div>
    <div class="close-button" @click="$emit('click')">
      <i class="fas fa-times"></i>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
  .header {
    width: 100%;
    padding: 10px;
    background-color: #49DC89;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.16);
  }

  .header .title {
    font-size: 2.5rem;
    font-weight: bold;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
    color: white;
  }

  .header .close-button {
    padding: 6px 10px;
    cursor: pointer;
    border-radius: 50%;
  }

  .header .close-button .fa-times {
    color: #666666;
    font-size: 1.5rem;
  }

  .header .close-button:hover .fa-times {
    color: #f43b54;
  }

  .header .close-button:hover {
     background-color: #49AC89;
  }
</style>