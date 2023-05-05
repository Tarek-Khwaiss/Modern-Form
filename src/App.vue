<template>
  <ModernForm defaultForm></ModernForm>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import ModernForm from './components/ModernForm.vue'
export default defineComponent({
  name: 'App',
  components: {
    ModernForm
  },
  data () {
    return {
      title: 'The Ultimate Form',
      subTitle: 'Subtitle'
    }
  }
})
</script>
<style lang="scss">
</style>
