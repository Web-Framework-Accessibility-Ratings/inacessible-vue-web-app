<template>
  <div class="containerStyle">
    <div class="navPanel">
      <img alt="Vue logo" src="./assets/logo.png">
      <button class="links" v-on:click="updateComponent('')">None</button>
      <button class="links" v-on:click="updateComponent('ImgNoAlt')">Text Alternatives</button>
    </div>
    <div class="inaccessibleContent">
      <component v-bind:is="currentComponent"/>
    </div>
  </div>
</template>

<script>
import ImgNoAlt from './components/1.1TextAlternatives.vue'

export default {
  name: 'App',
  components: {
    ImgNoAlt
  },
  data: function() {
    return {
      currentComponent: ''
    }
  },
  methods: {
    updateComponent: function(newComponent) {
      this.currentComponent = newComponent
    }
  }
}
</script>

<style>
  .containerStyle{
    width: 100%;
    flex: 1;
    flex-direction: 'row';
    padding-top: 10px;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  .inaccessibleContent{
    width: 80%;
    float: right;
  }

  .navPanel{
    width: 20%;
    float: left;
  }

  .links{
    width: 70%;
    align-self: center;
  }
</style>
