<template>
    <div class="container">
        <div class="about">
            <h2>{{title}}</h2>
            <p :v-if="paragraphs" v-for="(text, index) in paragraphs" :key="index">{{text}}</p>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            title: "About me",
            paragraphs: ["I was working as a professional stage actor for 5 years. I quit my job recently to start a new life, so here I am looking for work and new challenges.", "things i love: simple & smooth design. finding answers & solutions. good movies. quality music. video games. humour. cultural diversity. discussions. craft beer." ]
        }
    }
}
</script>