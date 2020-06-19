<template lang="html">
<div class="">
<select v-on:change="handleSelect" v-model="selectedCharacter">
<option disabled value="">Select a Character</option>
<option v-for="character in characters" :value="character" :key="character.id">{{character.name}}</option>
</select>
</div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'character-list',
  props: ['characters'],
  data(){
    return{
      "selectedCharacter": null
    }
  },
  methods:{
    handleSelect(){
      eventBus.$emit('character-selected', this.selectedCharacter)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
