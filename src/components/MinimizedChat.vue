<template>
  <div class="minimized-chat" @click="$emit('click')">
    <i class="fas fa-comments"></i>
    <div class="notification">3</div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style scoped>
  .minimized-chat {
    position: fixed;
    bottom: 10px;
    right: 10px;
  }

  .fa-comments {
    font-size: 80px;
    color: #49DC89;
    text-shadow: 3px 3px 1px rgba(0, 0, 0, 0.4);
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .fa-comments:hover {
    color: #2DDC79;
    text-shadow: 3px 3px 1px rgba(0, 0, 0, 0.6);
  }

  .notification {
    position: absolute;
    z-index: 2;
    top: 0;
    right: 10px;
    font-size: 1.1rem;
    font-weight: bold;
    background-color: #666666;
    color: white;
    padding: 5px 10px;
    border-radius: 15px;
  }
</style>