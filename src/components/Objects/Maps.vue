

<template>
    <div class="col-xs-12 col-sm-8">
        <button @click="show = !show ">{{ showOption() }}</button>
        <template v-if="show">
            <div> Your address : {{ homeLocation.addr }}</div>
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
        </template>
        <template v-else>
            <div> The distance from your <span :title="homeLocation.addr">place: </span>{{ calcDistance(myLat,myLng,homeLocation.position.lat,homeLocation.position.lng) }}
            m. Go faster - get some drinks! </div>
        </template>
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
                homeLocation: {
                    position: {lat: 41.397315, lng: 2.190144},
                    icon: 'src/assets/house.png',
                    type: 'house',
                    addr: 'Almogàvers 123, Barcelona'
                },
                show: true,
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
        methods: {
            showOption : function() {
                return (this.show == true) ? 'More information' : 'Back to Map'
            },
            calcDistance: function (lat1,lon1,lat2,lon2) {
                let p = 0.017453292519943295;    // Math.PI / 180
                let c = Math.cos;
                let a = 0.5 - c((lat2 - lat1) * p)/2 +
                    c(lat1 * p) * c(lat2 * p) *
                    (1 - c((lon2 - lon1) * p))/2;

                return Math.ceil(12742 * Math.asin(Math.sqrt(a)) * 1000);
            },
        }
    }
</script>

<style>

</style>
