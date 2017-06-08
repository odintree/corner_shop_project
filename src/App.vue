<template>
    <div class="container">
        <app-header></app-header>
        <hr>
        <div class="row">
            <maps></maps>
            <shop-display></shop-display>
        </div>
        <hr>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Shared/Header.vue';
    import Footer from './components/Shared/Footer.vue';
    import ShopDisplay from './components/Objects/ShopDisplay.vue';
    import Maps from './components/Objects/Maps.vue';

    export default {
        data: function () {
            return {
                lat: 41.39,
                lgn: 2.19
            };
        },
        components: {
            appHeader: Header,
            'shop-display': ShopDisplay,
            'maps': Maps,
            'app-footer': Footer
        }
    }
</script>

<style>
    body {
        background: #F1F9FD;
    }

</style>
