<template>
    <div>
        <div class="whole">
            <Header/>
            <About />
            <Footer />
        </div>
    </div>
</template>

<script>
export default {
    head(){
        return{
            title: 'About'  
        }
    },
    mounted(){
        console.log(this.aboutpage)
    }
}
</script>