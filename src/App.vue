<template>
    <div class="container">
        <div class="row">
            <button class="control" @click="selectedPart = 'app-main-box'">Home</button>
            <button class="control" @click="selectedPart = 'app-about-project'">About project</button>
            <button class="control" @click="selectedPart = 'app-about-us'">About us</button>

            <app-header></app-header>
            <hr>

            <component :is="selectedPart"></component>
<!--
            <app-main-box></app-main-box>
-->
            <hr>
            <app-footer></app-footer>
        </div>
    </div>
</template>

<script>
    import Header from './components/Parts/Header.vue';
    import Footer from './components/Parts/Footer.vue';
    import MainBox from './components/Parts/MainBox.vue';
    import AboutProject from './components/Parts/AboutProject.vue';
    import AboutUs from './components/Parts/AboutUs.vue';


    export default {
        data: function () {
            return {
                lat: 41.39,
                lgn: 2.19,
                selectedPart: 'app-main-box'
            };
        },
        components: {
            appHeader: Header,
            'app-footer': Footer,
            'app-main-box': MainBox,
            'app-about-project': AboutProject,
            'app-about-us': AboutUs
        }
    }
</script>

<style>
    body {
        background: #F1F9FD;
    }
    button {
        border: none;
        background: #40C4FF;
        color: white;
        margin-top: 2em;
        opacity: 100;
        border-radius: 25px;
    }
    .control{
        margin-bottom: 20px;
    }

</style>
