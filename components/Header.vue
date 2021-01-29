<template>
    <div class="header">
        <Cursorguy />
        <img class="header-bg" src="~/assets/images/1.png">
        <div  class="hamburger" @click="openNav()" id="hamburger">
            <div class="line line-one"></div>
            <div class="line line-two"></div>
            <div class="line line-go"></div>
        </div>
        <div class="nav-mobile" :class="{'nav-shown': navIsOpen}">
            <nav>
                <ul>
                    <li :v-if="navItems" v-for="(item, index) in navItems" :key="index" @click="openNav"><nuxt-link :to="item.href">{{item.text}}</nuxt-link></li>
                </ul>
            </nav>
        </div>
        <div class="main-nav">
            <nav>
                <ul>
                    <li :v-if="navItems" v-for="(item, index) in navItems" :key="index" class="main-nav-item"><nuxt-link :to="item.href">{{item.text}}</nuxt-link></li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            navIsOpen: false,
            navItems: [
                {
                    text: "home",
                    href: '/'
                },
                {
                    text: "about",
                    href: '/about'
                },
                {
                    text: "work",
                    href: '/work'
                },
                {
                    text: "skills",
                    href: '/skills'
                },
                {
                    text: "contact",
                    href: '/contact'
                }
            ]
        }
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
    },
}
</script>