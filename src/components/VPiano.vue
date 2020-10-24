<template>
  <div>
    <img id="emoji" src="" alt="emoji">
    <div id="app" class="bloc_piano">
      <button id="C" @click.prevent="playSound('/assets/sounds/C.mp3')" @click="getGifs()"></button>
      <button id="D" @click.prevent="playSound('/assets/sounds/D.mp3')" @click="getGifs()"></button>
      <button id="E" @click.prevent="playSound('/assets/sounds/E.mp3')" @click="getGifs()"></button>
      <button id="F" @click.prevent="playSound('/assets/sounds/F.mp3')" @click="getGifs()"></button>
      <button id="G" @click.prevent="playSound('/assets/sounds/G.mp3')" @click="getGifs()"></button>
      <button id="A" @click.prevent="playSound('/assets/sounds/A.mp3')" @click="getGifs()"></button>
      <button id="B" @click.prevent="playSound('/assets/sounds/B.mp3')" @click="getGifs()"></button>
      <button id="CD" @click.prevent="playSound('/assets/sounds/C%23.mp3')" @click="getGifs()"></button>
      <button id="DD" @click.prevent="playSound('/assets/sounds/C%23.mp3')" @click="getGifs()"></button>
      <button id="FD" @click.prevent="playSound('/assets/sounds/C%23.mp3')" @click="getGifs()"></button>
      <button id="GD" @click.prevent="playSound('/assets/sounds/C%23.mp3')" @click="getGifs()"></button>
      <button id="AD" @click.prevent="playSound('/assets/sounds/C%23.mp3')" @click="getGifs()"></button>
    </div>
  </div>
</template>



<script>
import { GiphyFetch } from '@giphy/js-fetch-api'
export default {
  data() {
    return {
      gifs:[]
    }
  },
  methods: {
    playSound: function (url) {
      new Audio(url).play();
    },
    async getGifs() {      
      const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
      const { data: gifs } =  await gf.emoji()
      const nbRandom = Math.floor(Math.random() * Math.floor(10));
      const urlRandom = gifs[nbRandom].images['fixed_width'].webp;

      document.getElementById('emoji').src=urlRandom;
    },       
  }
}
</script>