<template>
    <div>
        <div class="whole">
            <About />
        </div>
    </div>
</template>

<script>
export default {
    transition: 'about',
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