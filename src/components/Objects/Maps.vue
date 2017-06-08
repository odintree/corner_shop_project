

<template>
    <div class="col-xs-12 col-sm-8">
        <div> Your address : Almogàvers 123, Barcelona</div>
        <gmap-map
                :center="{lat: myLat, lng: myLng}"
                :zoom="myZoom"
                style="width: 500px; height: 350px"
        >
            <gmap-marker
                    :key="index"
                    v-for="(m, index) in markers"
                    :position="m.position"
                    :clickable="true"
                    :draggable="true"
                    @click="center=m.position"
                    :icon="m.icon"
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
        props: ['myLat', 'myLng','myZoom'],
        data () {
            return {
                markers: [{
                    position: {lat: 41.397315, lng: 2.190144},
                    icon: 'src/assets/house.png',
                    type: 'house'
                },{
                    position: {lat: 41.392166, lng: 2.19083},
                    icon: 'src/assets/shop.png',
                    type: 'shop'
                },{
                    position: {lat: 41.3896, lng: 2.194417},
                    icon: 'src/assets/shop.png',
                    type: 'shop'
                },{
                    position: {lat:41.393631, lng: 2.18889},
                    icon: 'src/assets/shop.png',
                    type: 'shop'
                },{
                    position: {lat:41.400441, lng: 2.179932},
                    icon: 'src/assets/shop.png',
                    type: 'shop'
                },{
                    position: {lat:41.389472, lng: 2.195313},
                    icon: 'src/assets/shop.png',
                    type: 'shop'
                },
                ]
            }
        },
    }
</script>

<style>

</style>
