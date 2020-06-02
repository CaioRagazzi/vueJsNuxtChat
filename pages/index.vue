<template>
  <div class="container">
    <div>
      <b-button variant="outline-primary">
        <nuxt-link to="/createLobby">
          Create Lobby
        </nuxt-link>
      </b-button>
      <b-button class="ml-2" variant="outline-primary" @click="show">
        Access Lobby
      </b-button>
    </div>
    <transition name="slide-fade">
      <b-form-input v-if="showInput" v-model="text" class="mt-3" placeholder="Enter Lobby ID" />
    </transition>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data () {
    return {
      text: '',
      showInput: false
    }
  },
  methods: {
    show () {
      this.showInput = true
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  max-width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>
