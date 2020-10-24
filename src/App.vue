<template>
  <div id="app">
    <v-title></v-title>
    <v-piano></v-piano>
    <v-notes></v-notes>
  </div>
</template>

<script>
import VTitle from '@/components/VTitle'
import VPiano from '@/components/VPiano'
import VNotes from '@/components/VNotes'
export default {
  name: 'App',
  components: {
    VTitle,
    VPiano,
    VNotes,
  }
}
</script>