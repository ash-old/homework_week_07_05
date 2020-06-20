<template lang="html">
<div v-if='character' class="fadeIn">
<h2></h2>
<p>Name: {{character.name}}</p>
<p>Nickname: {{character.nickname}}</p>
<p>Actor: {{character.portrayed}}</p>
<img :src="character.img" alt="character image" height="300" class="pic">
</div>
</template>

<script>
export default {
  name: 'character-detail',
  props: ['character']
}
</script>

<style lang="css" scoped>


.pic{
  border-radius: 2px;
  border-style:inset;
  border-color: white;
}
</style>
