<template>
  <div>
    <div class="loader" id="loader"></div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
export default {
  transition:{
    name: 'layout',
    mode: 'out-in'
  },
  mounted(){
    const loader = document.getElementById('loader');
    loader.classList.add('loaded')
  }
}
</script>
