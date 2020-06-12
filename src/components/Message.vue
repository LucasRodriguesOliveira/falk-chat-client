<template>
  <div class="message-group">
    <div class="message" :class="cssClass()">{{ message.text }}</div>
    <div class="automessage" v-if="message.automessage">Mensagem automática.</div>
  </div>
</template>

<script>
export default {
  props: {
    message: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      staffName: 'Carlos'
    }
  },
  methods: {
    cssClass() {
      return this.message.user === this.staffName ? 'other' : 'me';
    }
  }
}
</script>

<style scoped>
  .message-group {
    max-width: 100%;
    margin: 5px 2% 2% 3%;
    display: flex;
    flex-direction: column;
  }

  .message, .automessage {
    display: inline-block;
  }

  .message {
    padding: 2%;
    color: #000;
    text-shadow: 0 0 1px rgba(0, 0, 0, 0.5);
  }

  .automessage {
    color: #F43D5A;
  }
  
  .other {
    border-radius: 0 15px 15px 15px;
    background-color: #8DDCB0;
    align-self: flex-start;
  }

  .me {
    border-radius: 15px 0 15px 15px;
    background-color: #8DAFDC;
    align-self: flex-end;
  }
</style>