<template>
    <h1>
        Search
    </h1>
    <h3>
        Use the form to filter the hotels you wanna see
    </h3>
    <div class="filterPanel">
        <form>
            <input id="distance" type="range" min="20" max="2000" step="10" v-model="selectedDistance"
                style="width: 500px;"><br>
            <label for="distance">Distance from Drammen: {{ this.selectedDistance }}km </label>
        </form>
    </div>
    <div class="hotel-list">
        <h2>Filtered Hotels</h2>
        <ul>
            <li class="hotel" v-for="hotel in filteredHotels" :key="hotel.name">
                <a :href="hotel.link" target="_blank">
                    <h3> {{ hotel.name }} </h3>
                </a>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            hotels: [
                { name: "Dalen Hotel", link: "https://www.dalenhotel.no/", "distance": 167 },
                { name: "Storfjord Hotel", link: "https://www.storfjordhotel.com/no/", "distance": 531 },
                { name: "Panorama Hotell", link: "https://panoramahotell.no/", "distance": 477 },
                { name: "Hotel Union Øye", link: "https://www.unionoye.no/no", "distance": 580 },
                { name: "Copperhill Mountain Lodge", link: "https://copperhill.se/", "distance": 685 },
                { name: "Sund Nergården", link: "https://sundnergarden.se/", "distance": 549 },
                { name: "Clarion Hotel The Hub", link: "https://www.strawberry.no/hotell/norge/oslo/clarion-hotel-the-hub/?utm_campaign=gmb-listing&utm_medium=organic&utm_source=google", "distance": 47 },
                { name: "Thon Hotel Opera", link: "https://www.thonhotels.no/hoteller/norge/oslo/thon-hotel-opera/?utm_source=google&utm_medium=infoboks&utm_campaign=GMB", "distance": 49 },
                { name: "Scandic Ishavhotel", link: "https://www.scandichotels.no/hotelreservation/select-rate?hotel=310&fromDate=2023-09-10&toDate=2023-09-11&room[0].adults=2&utm_source=gha&utm_medium=meta&utm_campaign=ppa&utm_id=google_ppa&utm_content=meta_ads&dsclid=55848482809331712", "distance": 1787 },
                { name: "THE THIEF", link: "https://thethief.com/", "distance": 45 },
                { name: "Amerikalinjen", link: "https://amerikalinjen.com/", "distance": 47 },
                { name: "Farris Bad", link: "https://farrisbad.no/", "distance": 98 },
                { name: "Thorbjørnrud Hotell", link: "https://thorbjornrudhotell.no/nb", "distance": 76 },
                { name: "Juvet Landskapshotell", link: "https://www.juvet.com/", "distance": 500 },
                { name: "Comfort Hotel Union Brygge", link: "https://www.strawberry.no/hotell/norge/drammen/comfort-hotel-union-brygge/?utm_campaign=gmb-listing&utm_medium=organic&utm_source=google", "distance": 3 }
            ],
            selectedDistance: 500,
        }
    },
    computed: {
        filteredHotels() {
            return this.hotels.filter((hotel) => hotel.distance <= this.selectedDistance)
        }
    }
}
</script>

<style scoped>
li {
    list-style-type: none;
    margin-bottom: 40px;
}

a {
    color: #2c3e50;
}
</style>