<template>
  <div class="containerStyle">
    <div class="navPanel">
      <img alt="Vue logo" src="./assets/logo.png">
      <button class="links" v-on:click="updateComponent('')">None</button>
      <button class="links" v-on:click="updateComponent('ImgNoAlt')">Text Alternatives</button>
      <button class="links" v-on:click="updateComponent('InfoRelationship')">Information and Relationships</button>
      <button class="links" v-on:click="updateComponent('MeaningfulSequence')">Meaningul Sequence</button>
      <button class="links" v-on:click="updateComponent('InputPurpose')">Incorrect Input Purpose</button>
      <button class="links" v-on:click="updateComponent('IdentifyPurpose')">No Purpose on Elements</button>
      <button class="links" v-on:click="updateComponent('UseOfColor')">No Use of Color</button>
      <button class="links" v-on:click="updateComponent('AudioControl')">No Audio Control</button>
      <button class="links" v-on:click="updateComponent('ColorContrastMinimum')">Insuffcient Color Constrast</button>
      <button class="links" v-on:click="updateComponent('TextResize')">Text Resize</button>
      <button class="links" v-on:click="updateComponent('ImageOfText')">Image Of Text</button>
      <button class="links" v-on:click="updateComponent('ColorContrastEnhanced')">Color Contrast Enhanced</button>
      <button class="links" v-on:click="updateComponent('VisualPresentation')">Visual Presentation</button>
    </div>
    <div class="inaccessibleContent">
      <component v-bind:is="currentComponent"/>
    </div>
  </div>
</template>

<script>
import ImgNoAlt from './components/1.1TextAlternatives.vue'
import InfoRelationship from './components/1.3.1InfoRelationship.vue';
import MeaningfulSequence from './components/1.3.2MeaningfulSequence.vue';
import InputPurpose from './components/1.3.5InputPurpose.vue';
import IdentifyPurpose from './components/1.3.6IdentifyPurpose.vue';
import UseOfColor from './components/1.4.1UseOfColor';
import AudioControl from './components/1.4.2AudioControl';
import ColorContrastMinimum from './components/1.4.3ColorContrastMinimum';
import TextResize from './components/1.4.4TextResize';
import ImageOfText from './components/1.4.5ImageOfText';
import ColorContrastEnhanced from './components/1.4.6ColorContrastEnhanced.vue';
import VisualPresentation from './components/1.4.8VisualPresentation.vue';

export default {
  name: 'App',
  components: {
    ImgNoAlt,
    InfoRelationship,
    MeaningfulSequence,
    InputPurpose,
    IdentifyPurpose,
    UseOfColor,
    AudioControl,
    ColorContrastMinimum,
    TextResize,
    ImageOfText,
    ColorContrastEnhanced,
    VisualPresentation
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
