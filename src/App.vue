<template>
  <div id="app">
    <v-title></v-title>
    <v-emoji></v-emoji>
    <v-piano></v-piano>
    <v-note></v-note>
  </div>
</template>

<script>
import VTitle from '@/components/VTitle'
import VPiano from '@/components/VPiano'
import VNote from '@/components/VNote'
import VEmoji from '@/components/VEmoji'
export default {
  name: 'App',
  components: {
    VTitle,
    VPiano,
    VNote,
    VEmoji,
  }
}
</script>

<style lang="postcss" scoped>
#app {
  min-height: 100vh;
  width: 100%;
}
</style>