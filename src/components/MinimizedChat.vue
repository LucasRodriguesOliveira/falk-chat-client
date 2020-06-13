<template>
  <div class="minimized-chat" @click="$emit('click')">
    <i class="fas fa-comments"></i>
    <div class="notification">3</div>
    <div class="bar">
      <div class="title">Carlos</div>
      <div class="actions">
        <div class="maximize" @click="$emit('maximize')">
          <i class="fas fa-window-maximize"></i>
        </div>
        <div class="close" @click="$emit('close')">
          <i class="fas fa-times"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  created() {
    addEventListener('maximize', () => {});
    addEventListener('close', () => {});
  }
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

  .bar {
    display: none;
  }

  @media only screen and (min-width: 600px) {
    .fa-comments {
      display: none;
    }

    .bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 200px;
      background-color: #49DC89;
      padding: 2%;
      border-radius: 5px;
      box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.2);
      cursor: default;
    }

    .title {
      padding: 1%;
      font-size: 1.1rem;
      text-align: left;
      margin-right: 5px;
    }

    .actions {
      display: flex;
      justify-content: end;
      align-items: center;
      margin-left: 20px;
    }

    .actions > *:hover {
      text-shadow: 2px 2px 1px rgba(0, 0, 0, 0.4);
      cursor: pointer;
    }
    
    .fas {
      color: white;
      margin: 0 5px 0 5px;
    }

    .notification {
      right: 30%;
      top: 4px;
      font-size: 1rem;
      padding: 2px 8px;
    }
  }
</style>