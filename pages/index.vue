<template>
  <div>
    <div class="whole">
      <Hero />
    </div>
  </div>
</template>

<script>
export default{
  transition:'hero',
  head(){
    return{
      title: 'Homepage',
    }
  }
}

</script>