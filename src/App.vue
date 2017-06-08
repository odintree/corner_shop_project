<template>
    <div class="container">
        <div class="row">
            <button>Home</button>
            <button>About project</button>
            <button>About us</button>

            <app-header></app-header>
            <hr>
            <app-main-box></app-main-box>
            <hr>
            <app-footer></app-footer>
        </div>
    </div>
</template>

<script>
    import Header from './components/Parts/Header.vue';
    import Footer from './components/Parts/Footer.vue';
    import MainBox from './components/Parts/MainBox.vue'

    export default {
        data: function () {
            return {
                lat: 41.39,
                lgn: 2.19,
                selectedComponent: 'app-main-box '
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
