<template>
  <div class="appContainer">
    <Header></Header>
    <Form v-model="inputValue"></Form>
    <Btn @inputLog="inputLog" :title="'Submit'"></Btn>
  </div>
</template>

<script>
import Header from './components/header.vue'
import Form from './components/form.vue'
import Btn from './ui/button.vue'

export default{
    components:{
        Header, Form, Btn
    },
    data(){
      return{
        inputValue: {name:'', phoneNum:'', email:'',date:''}
      }
    },
    methods:{
      inputLog(){
        console.log(this.inputValue)
      }
    }
}
</script>

<style>
  @font-face {
    font-family: 'DM Sans';
    src: url('./assets/DMSans-VariableFont_opsz\,wght.ttf') format('truetype');
    }

    .appContainer{
        display: flex;
        flex-direction: column;
        align-items: center;
        font-family: DM Sans;
    }

</style>