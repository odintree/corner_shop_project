<template>
    <div class="col-xs-12 col-sm-4 component">

        <div class="time">{{ new Date().toLocaleString("de-DE", {timeZone: "Europe/Madrid"}) }}</div>
        <div id="container" >
            <ul>
                <li v-for="(item, index) in shops_list" @click="changeLat(index)">
                    <div>Store:  {{item.name}} </div>
                    <div>Address: {{ item.addr }}</div>
                    <div>{{ item.working_hour}}</div>
                    <hr>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['myLat','myLng','myZoom'],
        data: function () {
            return {
                shops_list: [
                    {name: 'Nohan Supermarket', addr: 'Carrer de Marina 68', working_hour: '08:00 - 00:00', lat:41.392166, lng: 2.19083},
                    {name: 'Supermercat Olimpic', addr: 'Carrer de Moscou 26', working_hour: '24h', lat:41.3896, lng: 2.194417},
                    {name: 'de fresca store', addr: 'Carrer de Marina 90', working_hour: '09:00 - 21:00', lat:41.393631, lng: 2.18889},
                    {name: 'Supermercat', addr: 'Carrer de Marina 200', working_hour: '09:00 - 23:00', lat:41.400441, lng: 2.179932},
                    {name: 'Max Supermercat', addr: "Avinguda d'Icaria 134", working_hour: '09:00 - 00:00', lat:41.389472, lng: 2.195313},
                    {name: 'Max Supermercat', addr: "Avinguda d'Icaria 134", working_hour: '09:00 - 00:00', lat:41.3896, lng: 2.194417},
                ],
                position: 5
            }
        },
        methods: {
            changeLat(i) {
                this.myLat = this.shops_list[i].lat;
                this.myLng = this.shops_list[i].lng;
                this.myZoom = 20;
                this.$emit('changedLat', this.myLat);
                this.$emit('changedLng', this.myLng);
                this.$emit('changedZoom', this.myZoom);
            }
        }
    }
</script>

<style scoped>
    li {
        list-style-type: none;
    }
    li:nth-child(odd) {
        background: #E0F6FF;
    }
    li:nth-child(even) {
        background: #EEF9E2;
    }

    .time {
        background: lightgoldenrodyellow;
        margin-bottom: 1px;
        text-align: right;
    }
    #container {
        max-height:400px;
        overflow-y: auto;
    }
</style>
