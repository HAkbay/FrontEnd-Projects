<template>
  <h1>Reaction Speed</h1>
  <button @click="start" :disabled="isPlaying">Start!</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
</template>

<script>
  import Block from './components/Block.vue'
  import Results from './components/Results.vue'
  export default {
    name: 'App',
    components: { Block, Results },
    data(){
      return {
        isPlaying: false,
        delay: null,
        score: null,
        showResults: false
      }
    },
    methods:{
      start(){
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
        this.showResults = false
      },
      endGame(reactionTime){
        this.showResults = true
        this.score = reactionTime
        this.isPlaying = false
      }
    }
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: gray;
    margin-top: 60px;
  }
  button{
    background: lightslategray;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
  }
  button:hover{
    opacity: 0.6;
  }
  button[disabled]{
    opacity: 0.3;
    cursor: not-allowed;
  }
</style>
