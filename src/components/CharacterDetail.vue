<template lang="html">
<div v-if='character' class="">
<h2></h2>
<p>Name: {{character.name}}</p>
<p>Nickname: {{character.nickname}}</p>
<p>Actor: {{character.portrayed}}</p>
<img :src="character.img" alt="character image" height="400">
</div>
</template>

<script>
export default {
  name: 'character-detail',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
