<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data () {
    return {
      a: 1,
      b: '2',
      c: []
    }
  },
  methods: {
    test () {
      // this.c
    }
  }
})
</script>

<style lang="scss" scoped>
.text {
  color: $warning-color;
}
</style>
