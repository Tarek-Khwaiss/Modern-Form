<template>
  <div class="pop-up">
    <div></div>
  </div>
  <div class="page-container">
    <h1>{{ title }}</h1>
    <h2>{{ subTitle }}</h2>
    <form>
      <div class="form-container">
        <div class="input-container">
          <div class="label-container">
            <label for="email">Email</label>
          </div>
        <input type="email" id="email" :placeholder="emailPlaceholder" required/>
      </div>
      <div class="input-container">
        <div class="label-container">
          <label for="status">Status</label>
        </div>
          <input type="text" id="status" :placeholder="statusPlaceholder" required/>
      </div>
      <div class="input-container">
        <div class="label-container">
          <lable for="message">Message</lable>
        </div>
        <textarea id="message" :placeholder=messagePlaceholder required></textarea>
      </div>
      <div class="btn-container">
        <button @click="submitForm">Send</button>
      </div>
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
      formSubTitle: "send me over you'r thoughts",
      emailPlaceholder: 'EXAMPLE@HOTMAIL.COM',
      statusPlaceholder: 'SOFTWARE ENGINEER',
      messagePlaceholder: "LET'S COLLAB"
    }
  },
  methods: {
    submitForm () {
      console.log('test')
    }
  }
})
</script>

<style lang="scss" scoped>
@import url('@/styles/global.scss');

section{
  width: 100vw;
  height: 100vh;
  background-color: whitesmoke;
}
.page-container{
  height: 100vh;
  padding: 2rem;
  h1{
    font-size: 5.5rem;
    margin: 0;
  }
  h2{
    margin: 0;
    @include flex-box(row, end , center);
    display: flex;
  }
}
.form-container{
  padding: 3rem 3rem 0.2rem 3rem;
  border-top: 0.5rem solid $primary;
  border-right: 0.5rem solid $primary;
  margin: 1rem 0;
  width: 55%;
}
.input-container{
  margin-bottom: 2rem;
  input {
    width: 100%;
    background-color: $background;
    border-style: none;
    border-bottom: 0.3rem solid $primary;
    border-left: 0.3rem solid $primary;
    color: $primary;
    padding: 0.5rem 0 0.5rem 0.5rem;
    font-size: 0.8rem;
    font-family: inherit;
  }
  textarea{
    background-color: $background;
    color: $primary;
    width: 100%;
    height: 10rem;
    padding: 0.5rem 0 0.5rem 0.5rem;
    font-size: 1.5rem;
    margin: 1rem 0;
    resize: none;
    border-style: none;
    border-bottom: 0.3rem solid $primary;
    border-left: 0.3rem solid $primary;
    font-family: inherit;
    overflow-y: visible;
    &::placeholder{
      color: #a3a3a3;
    }
  }
  textarea:focus{
    outline-style: none;
  }

}
.label-container{
  @include flex-box(row,end,center);
}

.input-container input:focus{
  outline-style: none;
}
.input-container {
  input::placeholder{
  color: #a3a3a3;
}
}
.btn-container{
  @include flex-box(row,end,center);
  button{
    border-style: none;
    width: 5rem;
    background-color: $background;
    border: 0.3rem solid $primary;
    color: $primary;
    padding: 0.5rem 1rem;
    box-shadow: 1px 1px 5px #131313;
    min-width: 2rem;
    &:hover{
      background-color: $primary;
      color: $background;
      cursor: pointer;
    }
  }
}
@media (max-width: 50rem){
  .form-container{
    width: 100%;
  }
  .page-container{
    h1{
      font-size: 4rem;
    }
    h2{
      font-size: 1.5rem;
    }
  }
}
</style>
