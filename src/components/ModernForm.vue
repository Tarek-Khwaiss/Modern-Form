<template>
  <div class="form-container">
    <h1>{{ title }}</h1>
    <h2>{{ subTitle }}</h2>
    <form>
      <div class="input-container">
        <label for="email">Email</label>
        <input type="text" id="email">
      </div>
      <div class="input-container">
        <label for="status">Status</label>
        <input type="text" id="status">
      </div>
    </form>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'modernFrom',
  props: {
    title: {
      type: String,
      required: false,
      default: 'WANT TO GET IN TOUCH'
    },
    subTitle: {
      type: String,
      required: false,
      default: 'HIT ME UP, YOUR OPINNION MATTERS'
    },
    defaultForm: {
      type: Boolean,
      required: true,
      default: false
    }
  },
  data () {
    return {
      formTitle: 'Want To get in touch',
      formSubTitle: "send me over you'r thoughts"
    }
  }
})
</script>

<style lang="scss" scoped>
@import url('@/styles/global.scss');
.form-container{
  background-color: $background;
  padding: 2rem;
  h1{
    font-size: 6.5rem;
    margin-left: 2rem;
    margin-bottom: 0;
  }
  h2{
    margin: 0;
    @include flex-box(row, end , center);
    display: flex;
  }
}
.input-container{
  margin: 1rem 0;
}

</style>
