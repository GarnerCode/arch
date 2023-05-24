<template>
    <div id="map">
        <client-only>
            <l-map 
                :center="center"
                :zoom="zoom">
                <l-tile-layer url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"></l-tile-layer>
                <l-marker :lat-lng="tnOffice"></l-marker>
                <l-marker :lat-lng="txOffice"></l-marker>
            </l-map>
        </client-only>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #map {
            .leaflet-container {
                height: 367px;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #map {
            .leaflet-container {
                height: 560px;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Map',
        data: () => {
            return {
                center: [34.355719938671704,-92.90011295009472],
                zoom: 6,
                tnOffice: [35.54995441269548, -86.58243887719517],
                txOffice: [33.070631504189066, -96.08827557674867],
            }
        }
    })
</script>