<template>
    <div class="container">
        <app-header></app-header>
        <hr>
        <app-main-box></app-main-box>
        <hr>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Shared/Header.vue';
    import Footer from './components/Shared/Footer.vue';
    import MainBox from './components/Shared/MainBox.vue'

    export default {
        data: function () {
            return {
                lat: 41.39,
                lgn: 2.19
            };
        },
        components: {
            appHeader: Header,
            'app-footer': Footer,
            'app-main-box': MainBox
        }
    }
</script>

<style>
    body {
        background: #F1F9FD;
    }

</style>
