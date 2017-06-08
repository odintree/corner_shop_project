<template>
    <div class="component">
        <div class="row">
            <app-maps
                    :myLat="lat"
                    :myLng="lng"
                    :myZoom="zoomLvl"></app-maps>
            <app-shops-display
                    :myLat="lat"
                    :myLng="lng"
                    :myZoom="zoomLvl"
                    @changedLat="lat = $event"
                    @changedLng="lng = $event"
                    @changedZoom="zoomLvl=$event"
            > </app-shops-display>
        </div>
    </div>
</template>

<script>
    import ShopDisplay from './../Objects/ShopDisplay.vue';
    import Maps from './../Objects/Maps.vue';


    export default {
        data: function () {
            return {
                lat: 41.39,
                lng: 2.19,
                zoomLvl: 10
            };
        },
        methods: {
        },
        components: {
            'app-shops-display': ShopDisplay,
            'app-maps': Maps
        }
    }
</script>

<style scoped>


</style>
