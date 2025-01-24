
<script setup>
import FormAccess from '@/components/FormAccess.vue';
</script>
<template>
  <div class="centerOnPage fullHeight bg-secondaryGrey">
    <div class="boxShadow p-5 centerOnPage">
      <p class="font-weight-bold fsize-23">Registrate aquí</p>
        <form-access :apiUrl="'https://reqres.in/api/register'"></form-access>
    </div>
  </div>
</template>


<style scoped>

p{
  margin: 0;
  padding: 0;
}

.centerOnPage{
  display: grid;
          place-content: center;
          place-items: center;
}

.fullHeight{
  height: 100vh;
}

.fsize-23{
  font-size: 23px;
}

.bg-secondaryGrey{
  background-color: #f1f3f5bd;
}

.font-weight-bold{
  font-weight: bold;
}

.boxShadow{
  border-radius: 10px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, .1);
}

.btn-secondary{
  background-color: #35495E;
}

.btn-secondary:hover{
  background-color: #41B883;
}

</style>