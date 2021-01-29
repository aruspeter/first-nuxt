<template>
  <div>
    <div class="whole">
      <Contact />
    </div>
  </div>
</template>

<script>
export default{
  transition: {
      name: 'contact',
      mode: 'out-in'
    },
  head(){
    return{
      title: 'Contact',
    }
  }
}
</script>