<template>
  <div >
    <span class="logo">
      <img src="./assets/logo.png" height="120" width="220" alt="Breaking Bad logo">
    </span>
    <div id="app">
      <character-list :characters="characters"></character-list>
      <character-detail :character="selectedCharacter"></character-detail>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import CharacterList from './components/CharacterList.vue'
import CharacterDetail from './components/CharacterDetail.vue'


export default {
  data(){
    return{
      characters: [],
      "selectedCharacter": null,
    }
  },
  components: {
    'character-list': CharacterList,
    'character-detail': CharacterDetail
  },
  mounted(){
    fetch('https://www.breakingbadapi.com/api/characters')
    .then(res => res.json())
    .then(characters => this.characters = characters)

    eventBus.$on('character-selected', (character) =>{
      this.selectedCharacter = character
    })

  }
}

</script>

<style>
.logo{
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

body {
  background: url(assets/bkg.jpg);
  background-size:cover;
  background-repeat: no-repeat;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 35px;
}

</style>
