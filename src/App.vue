<template>

  <div id="app" :class="this.$store.getters['theme']">
    
    <Nav/>
    <Message/>
    
    <div class="base" :class="{'sidebar-open' : this.$store.getters.sidebar}">
      <Sidebar />
      <Editor />
    </div>
    
    
  </div>
</template>

<script>

import Nav from './components/Nav.vue'
import Sidebar from './components/Sidebar.vue'
import Message from './components/Message.vue'
import Editor from './components/editor/Editor.vue'

export default {
  name: 'app',
  components: {
      Nav,
      Sidebar,
      Editor,
      Message
  },
  created() {
    
    //open sidebar after 100ms
    if (window.screen.availWidth > 900) {
      setTimeout(() => {
      this.$store.commit('sidebar');
    }, 100);

    }

  }
}
</script>
