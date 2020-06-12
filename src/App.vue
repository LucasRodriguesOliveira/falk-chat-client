<template>
  <div id="app">
    <Balloon :class="toggle('closed')"
      @click="changeStageTo(stages[1])">
    </Balloon>
    <Login :class="toggle('login')"
      @close="changeStageTo(stages[0])"
      @login="changeStageTo(stages[2])">
    </Login>
    <Chat :class="toggle('open')"
      @close="changeStageTo(stages[3])">
    </Chat>
    <MinimizedChat :class="toggle('minimized')"
      @click="changeStageTo(stages[2])">
    </MinimizedChat>
  </div>
</template>

<script>

import Balloon from './components/Balloon';
import Login from './components/Login';
import Chat from './components/Chat';
import MinimizedChat from './components/MinimizedChat';

export default {
  name: 'App',
  components: {
    Balloon,
    Login,
    Chat,
    MinimizedChat
  },
  data() {
    return {
      currentStage: 'closed',
      stages: [
        'closed',
        'login',
        'open',
        'minimized'
      ]
    }
  },
  methods: {
    changeStageTo(stage) {
      this.currentStage = stage;
    },
    toggle(stage) {
      return this.currentStage === stage ? '' : 'hide';
    }
  }
}
</script>

<style>
@font-face {
  font-family: 'Quicksand';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url(https://fonts.gstatic.com/s/quicksand/v20/6xKtdSZaM9iE8KbpRA_hK1QN.woff2) format('woff2');
  unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
}

@font-face {
  font-family: 'Quicksand';
  font-style: normal;
  font-weight: 700;
  font-display: swap;
  src: url(https://fonts.gstatic.com/s/quicksand/v20/6xKtdSZaM9iE8KbpRA_hK1QN.woff2) format('woff2');
  unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
}

* {
  margin: 0;
  padding: 0;
  outline: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
  scroll-behavior: smooth;
}

#app {
  font-family: 'Quicksand', 'Segoe UI', Arial, Helvetica, sans-serif;
}

.hide {
  display: none;
}
</style>