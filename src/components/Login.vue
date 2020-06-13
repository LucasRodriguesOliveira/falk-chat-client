<template>
  <div class="login">
    <ChatHeader title="Chat Online"
      @click="$emit('close')"></ChatHeader>
    <div class="form-group">
      <form @submit.prevent="$emit('login')">
        <label for="name">Insira seu nome</label>
        <input type="text"
          name="name"
          id="name"
          :placeholder="placeholder"
          v-model="name">
        <input type="submit" value="Entrar">
      </form>
    </div>
    <div class="logo">
      Falk
    </div>
  </div>
</template>

<script>
import ChatHeader from './ChatHeader';

export default {
  components: {
    ChatHeader
  },
  data() {
    return {
      name: '',
      placeholder: 'Fulano da Silva'
    }
  },
  created() {
    addEventListener('close', () => {});
    addEventListener('login', () => {});
  }
}
</script>

<style scoped>
  .login {
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1;
  }

  .form-group {
    width: 100%;
    padding: 10px;
    margin-top: 20%;
  }

  form {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  form > * {
    margin: 15px auto 20px;
  }

  label {
    font-size: 2.5rem;
    font-weight: bold;
    color: #2DDC79;
    text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.16);
  }

  input[type="text"] {
    font-size: 1.5rem;
    text-align: center;
    border: 1px solid #49DC89;
    padding: 1%;
    border-radius: 5px;
    box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
  }

  input[type="submit"] {
    font-size: 1.5rem;
    border: 0;
    border-radius: 5px;
    background-color: #49DC89;
    color: white;
    font-weight: bold;
    padding: 10px;
    box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.16);
    cursor: pointer;
    transition: all 0.4s ease 0.1s;
  }

  input[type="submit"]:hover {
    box-shadow: 3px 3px 2px rgba(0, 0, 0, 0.4);
  }

  .logo {
    font-size: 1.2rem;
    color: #49DC89;
    text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.16);
    font-weight: bold;
    position: fixed;
    bottom: 10px;
    right: 10px;
  }

  @media only screen and (min-width: 600px) {
    .login {
      width: 400px;
      position: fixed;
      bottom: 10px;
      right: 10px;
      left: unset;
      top: unset;
      z-index: 1;
      background-color: #49DC89;
      box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
    }

    .form-group {
      margin-top: 0;
    }

    label {
      font-size: 1.5rem;
      color: white;
    }

    input[type="submit"] {
      background-color: white;
      color: #49DC89;
    }
  }
</style>