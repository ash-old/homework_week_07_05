<template lang="html">
  <div v-if='character'>
    <p>Name: {{character.name}}</p>
    <p>Nickname: {{character.nickname}}</p>
    <p>Actor: {{character.portrayed}}</p>
    <p v-if="showStatus">Status: {{character.status}}</p>
    <!-- <transition name="bounce"> -->
    <img :src="character.img" v-on:click="status" alt="character image" height="250" class="pic">
  <!-- </transition> -->
  </div>
</template>

<script>
export default {
  name: 'character-detail',
  props: ['character'],
  data(){
    return {
      showStatus: false
    }
  },
  methods: {
    status(){
      this.showStatus = !this.showStatus
    }

  }
}
</script>

<style lang="css" scoped>

.pic{
  border-radius: 2px;
  border-style:inset;
  border-color: white;
}
/* .bounce-enter-active {
  animation: bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0%{
    transform:scale(0);
  }
  50%{
    transform:scale(1.5);
  }
  100%{
    transform:scale(1);
  }
} */
</style>
