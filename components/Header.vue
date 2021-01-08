<template>
    <div class="header">
        <Cursorguy />
        <img class="header-bg" src="~/assets/images/1.png">
        <div class="nav-mobile">
            <img  class="hamburger" :class="{'hamburger-animate': navIsOpen}" src="~/assets/icons/hamburger.png" @click="openNav()" id="hamburger">
            <nav :class="{'nav-shown': navIsOpen}">
                <ul>
                    <li v-if="notHome()" ><a href="/" class="back">back to home</a></li>
                    <li v-if="notAbout()"><a href="/about">about me</a></li>
                    <li v-if="notWorks()"><a href="/works">works</a></li>
                    <li v-if="notSkills()"><a href="/skills">skills</a></li>
                    <li v-if="notContact()"><a href="/contact">contact</a></li>
                </ul>
            </nav>
        </div>
        <div class="main-nav">
            <nav>
                <ul>
                    <li v-if="notHome()" ><a href="/" class="back">back to home</a></li>
                    <li v-if="notAbout()"><a href="/about">about me</a></li>
                    <li v-if="notWorks()"><a href="/works">works</a></li>
                    <li v-if="notSkills()"><a href="/skills">skills</a></li>
                    <li v-if="notContact()"><a href="/contact">contact</a></li>
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