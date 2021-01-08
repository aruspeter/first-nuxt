<template>
    <div class="whole">
        <Header/>
        <About />
        <Footer />
    </div>
</template>

<script>
export default {
    aboutpage: true,
    mounted(){
        console.log(this.aboutpage)
    }
}
</script>