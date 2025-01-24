<template>
  <div class="container-fluid px-0">
    <div class="bgPrimary">
      <header-component :islogged="isLogged()" @updateLogged="isLogged()" :key="loggedKey"></header-component>
    </div>
    <router-view></router-view>
    <footer-component></footer-component>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import {ref} from 'vue';

export default {
  name: 'App',
  components : {
    HeaderComponent,
    FooterComponent
  },
  methods: {
    isLogged () { 
    const loggedKey = ref(0);
      if(localStorage.getItem('token')){
        return true
      }else{
        window.location.reload
        return false
      }
    },


  },
  provide(){
    return {
      callIsLogged: this.isLogged
    }
  },
  created(){
    this.isLogged()
  }
  
}


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.bgPrimary{
  background-color: #359369;
}

</style>
