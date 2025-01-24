<template>
  <div class="bg-secondaryGrey fullHeight">
    <image-text
      title="¡TPH MARKETING!"
      text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam condimentum, nibh at scelerisque pharetra, nunc tortor aliquet sem, vel mattis est nibh sit amet dolor. Integer mattis porta leo, ut suscipit metus elementum vel. Praesent non interdum metus. In feugiat vel tortor consequat tincidunt. Fusce dapibus eleifend libero, nec laoreet ante porttitor eu. Nam pellentesque arcu eu dolor ultrices molestie. Suspendisse ac elit pretium, efficitur augue id, posuere ligula. Maecenas vestibulum ex metus, ac semper eros placerat eu. Nulla id cursus lectus. Sed laoreet ipsum eu tortor ornare, quis facilisis leo tincidunt.."
      cta="Registrate"
    />
    
  </div>  
</template>

<script setup>
import ImageText from "@/components/ImageText.vue";
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.bg-secondaryGrey {
  background-color: #f1f3f5bd;
}

.fullHeight {
  height: 100vh;
}

@media (max-width: 900) {
  
}
</style>
