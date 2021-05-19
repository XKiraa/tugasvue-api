<template>
  <div class="about">
    <HelloWorld msg="Berhasil Menambhakan Data"/>
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'About',
  components: {
    HelloWorld
  },
  data() {
      return {
        // value: ''
      }
  }
}
</script>

<style>

</style>