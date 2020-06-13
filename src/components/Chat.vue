<template>
  <div class="chat">
    <div class="chat-content">
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

  .chat-content {
    position: relative;
    width: 100%;
    min-height: 450px;
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

  .fa-paper-plane {
    cursor: pointer;
  }

  .messages {
    max-height: 450px;
    overflow: auto;
  }

  @media only screen and (min-width: 600px) {
    .chat {
      width: 400px;
      position: fixed;
      left: unset;
      top: unset;
      right: 10px;
      bottom: 10px;
      background-color: #49DC89;
    }

    .chat-content {
      background-color: #49DC89;
    }

    .messages, .header, .form-group {
      position: absolute;
    }

    .messages {
      top: 75px;
    }

    .header {
      top: 0;
    }

    .form-group {
      bottom: 0;
      left: 0;
      background-color: #49DC89;
      padding: 0;
    }

    .send-button {
      padding: 4%;
      margin-left: 8%;
      font-size: 1.4rem;
      color: white;
      text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.16);
    }

    .send-button .fa-paper-plane:hover {
      color: #3A634C;
      cursor: pointer;
    }

    .messages {
      height: 320px;
      background-color: white;
      margin: 0 5px 0 5px;
    }
  }
</style>