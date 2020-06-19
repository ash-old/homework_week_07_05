<template>
  <div id="app">
<h1>Breaking Bad</h1>
<character-list :characters="characters"></character-list>
<character-detail :character="selectedCharacter"></character-detail>
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
      "selectedCharacter": null
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
