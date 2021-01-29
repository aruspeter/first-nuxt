<template>
    <div class="container">
        <div class="works">
            <div class="hover-glower"></div>
            <div v-for="(work, index) in works" :key="index" class="work"  @mouseover="work.open = true" @mouseout="work.open = false">
                <div class="work-main" >
                    <h2 class="work-title">{{work.title}}</h2>
                    <p class="short-description" :class="{'transparent' : work.open}">{{work.shortDescription}}</p>
                </div>
                <div v-if="work.longDescription" :class="{'is-open' : work.open, 'long-description' : !work.open}" >
                    <p>{{work.longDescription}}</p>
                </div>
                <a class="work-link" :href="work.link" target="_blank">{{work.linkText}}</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            title: "My works",
            works: [
                {
                    title: 'Mulpleo',
                    shortDescription: 'A Pharma website',
                    longDescription: 'This project was the one that got my feet wet. It\'s the first larger website I\'ve ever worked on. Technologies used: Javascript, Sass, Webpack, MVC Razor, Umbraco. My role: Upgrading existing html and css to have a completely new theme and some new functionality whilst not affecting old code.',
                    link: 'https://mulpleo.co.uk/',
                    open: false,
                    linkText: 'Link to website' ,
                },
                {
                    title: 'Red Carnation Hotels',
                    shortDescription: 'I\'m currently maintaining the Front End of this major Hotel Chain website',
                    longDescription: 'The first time I\'ve met Vue. It was very challenging at first, I had a lot to catch up with. Currently I\'m very proud to be a part of this large & amazing project. Tech used: Webpack, Vue.js, Typescript, Javascript, SCSS, Yarn, Git, Umbraco.',
                    link: 'http://redcarnationhotels.com/',
                    open: false,
                    linkText: 'Link to website' ,
                },
                {
                    title: 'Matter Of Form',
                    shortDescription: 'Website of a Digital Agency ',
                    longDescription: 'I like this one very much. This was the first Vue project I was working on from the beginning. My role was: Developing Modules, Fixing bugs in framework and modules, Tech used: Vue.js, Javascript, SCSS, etc.',
                    link: 'https://matterofform.com/',
                    open: false,
                    linkText: 'Link to website' ,
                },
                {
                    title: 'This page of course',
                    shortDescription: 'This is made with Nuxt. The github repo below:',
                    longDescription: null,
                    link: 'https://github.com/aruspeter/first-nuxt',
                    open: false,
                    linkText: 'Right here' ,
                },

            ]
        }
    }
}
</script>
