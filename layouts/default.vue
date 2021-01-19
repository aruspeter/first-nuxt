<template>
  <div>
    <div class="loader" id="loader"></div>
    <Nuxt />
  </div>
</template>

<script>
export default {
  mounted(){
    const loader = document.getElementById('loader');
    loader.classList.add('loaded')
  }
}
</script>
