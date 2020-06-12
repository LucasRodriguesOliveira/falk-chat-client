<template>
  <div class="chat">
    <ChatHeader title="Carlos"
      @click="$emit('close')"></ChatHeader>
    <div class="messages">
      <Message v-for="message in messages"
        :key="message.id"
        :message="message">
      </Message>
    </div>
    <div class="form-group">
      <form @submit.prevent>
        <input type="text" name="message" placeholder="Digite sua mensagem" v-model="message">
        <div class="send-button">
          <i class="fas fa-paper-plane"></i>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import ChatHeader from './ChatHeader';
import Message from './Message';

export default {
  components: {
    ChatHeader,
    Message
  },
  data() {
    return {
      message: '',
      messages: [
        {
          id: 1,
          user: 'Carlos',
          text: 'Olá! Bem vindo ao website.com',
          automessage: true
        },
        {
          id: 2,
          user: 'Carlos',
          text: 'Irei responder suas mensagens assim que possível. Ative as notificações e fique atento.',
          automessage: true
        },
        {
          id: 3,
          user: 'Guest',
          text: 'Olá! Pode me ajudar?',
          automessage: false
        }
      ]
    }
  },
  created() {
    addEventListener('close', () => {});
  }
}
</script>

<style scoped>
  .chat {
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1;
  }

  .form-group {
    width: 100%;
    position: fixed;
    bottom: 0;
    left: 0;
    background-color: #49DC89;
    padding: 20px;
  }

  form {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  input[type="text"] {
    font-size: 1.2rem;
    padding: 2%;
    border: 0;
    border-radius: 5px;
  }

  .send-button {
    padding: 4%;
    margin-left: 3%;
    font-size: 1.4rem;
    color: white;
    text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.16);
  }

  .messages {
    max-height: 450px;
    overflow: auto;
  }
</style>