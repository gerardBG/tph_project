<template>
  <div class="d-flex container pt-50 mobileFlex">
    <div>
      <img src="../assets/banner.webp" alt="" class="imageSize"/>
    </div>
    <div>
      <div class="d-flex flex-column ms-lg-4 mt-sm-3 gap-2">
        <h1>
          {{ title }}
        </h1>
        <p class="text-left">
          {{ text }}
        </p>
        <div class="w-100 text-center">
            <router-link to='/register' class="btn btn-primary px-3 colorPrimary">
                {{cta}}
            </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default({
  props: {
    title: {
      type: String,
      default: "",
    },
    text: {
      type: String,
      default: "",
    },
    cta:{
        type: String,
        default: ""
    }
    // imagen: {
    //     type: String,
    //     default: "",
    // }
}
});
</script>

<style scoped>
.text-left {
    text-align: left;
}
.pt-50{
    padding-top: 50px;
}
.colorPrimary{
  background-color: #41B883;
  border: none;
  width: 12vh;
  text-align: center;
}
.colorPrimary:hover{
  background-color: #35495E;
}

.imageSize{
  width: 600px;
}

@media (max-width: 900px){
  .mobileFlex{
    flex-direction: column;
  }
  .imageSize{
    width:300px;
  }
  .mt-sm-3{
    margin-top: 2rem;
  }
}

</style>