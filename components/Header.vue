<template>
    <div class="header">
        <Cursorguy />
        <img class="header-bg" src="~/assets/images/1.png">
        <div class="nav-mobile">
            <div  class="hamburger" @click="openNav()" id="hamburger">
                <div class="line line-one"></div>
                <div class="line line-two"></div>
                <div class="line line-go"></div>
            </div>
            <nav :class="{'nav-shown': navIsOpen}">
                <ul>
                    <li v-if="notHome()" ><nuxt-link to="/" class="back">back to home</nuxt-link></li>
                    <li v-if="notAbout()"><nuxt-link to="/about">about me</nuxt-link></li>
                    <li v-if="notWorks()"><nuxt-link to="/works">works</nuxt-link></li>
                    <li v-if="notSkills()"><nuxt-link to="/skills">skills</nuxt-link></li>
                    <li v-if="notContact()"><nuxt-link to="/contact">contact</nuxt-link></li>
                </ul>
            </nav>
        </div>
        <div class="main-nav">
            <nav>
                <ul>
                    <li v-if="notHome()" ><nuxt-link to="/" class="active">back to home</nuxt-link></li>
                    <li v-if="notAbout()"><nuxt-link to="/about">about me</nuxt-link></li>
                    <li v-if="notWorks()"><nuxt-link to="/works">works</nuxt-link></li>
                    <li v-if="notSkills()"><nuxt-link to="/skills">skills</nuxt-link></li>
                    <li v-if="notContact()"><nuxt-link to="/contact">contact</nuxt-link></li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            navIsOpen: false
        };
    },
    methods:{
        openNav(){
            this.navIsOpen = !this.navIsOpen;
            const lines = document.getElementsByClassName('line');
            console.log(lines)
            lines.forEach(line => {
                line.classList.toggle('animate');
            })
        },
        notHome(){
            return window.location.href.split("/")[3] != "";
        },
        notAbout(){
            return window.location.href.split("/")[3] != "about";
        },
        notWorks(){
            return window.location.href.split("/")[3] != "works";
        },
        notSkills(){
            return window.location.href.split("/")[3] != "skills";
        },
        notContact(){
            return window.location.href.split("/")[3] != "contact";
        },
    }
}
</script>