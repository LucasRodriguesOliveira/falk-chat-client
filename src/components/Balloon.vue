<template>
  <div class="balloon" @click="$emit('click')">
    <i class="fas fa-comments"></i>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
.balloon {
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
</style>