

<template>
    <div class="col-xs-12 col-sm-8">
        <gmap-map
                :center="center"
                :zoom="13"
                style="width: 500px; height: 300px"
        >
            <gmap-marker
                    :key="index"
                    v-for="(m, index) in markers"
                    :position="m.position"
                    :clickable="true"
                    :draggable="true"
                    :icon = "m.icon"
                    @click="center=m.position"
            ></gmap-marker>
        </gmap-map>
    </div>
</template>

<script>
    /////////////////////////////////////////
    // New in 0.4.0
    import * as VueGoogleMaps from '../../../node_modules/vue2-google-maps';
    import Vue from 'vue';



    Vue.use(VueGoogleMaps, {
        load: {
            key: 'AIzaSyABooIFniiFUgChYv5J0F7nMcWCtb5TwZc',

            // libraries: 'places', //// If you need to use place input
        }
    });

    export default {

        data () {
            return {
                center: {lat: 41.392166, lng: 2.19083},
                markers: [{
                    position: {lat: 41.392166, lng: 2.19083},
                    icon: 'src/assets/shop.png'
                },{
                    position: {lat: 41.412376, lng: 2.166382},
                    icon: 'src/assets/house.png'

                }]
            }
        }
    }
</script>

<style>

</style>
