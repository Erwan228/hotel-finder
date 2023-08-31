<template>
    <h1>
        Search
    </h1>
    <h3>
        Use the form to filter the hotels you wanna see
    </h3>
    <FilterPanel v-on:input="getInput($event)" />
    <div v-if="hotels.length">
        <HotelList :selectedDistance="selectedDistance" />
    </div>
</template>

<script>
import FilterPanel from '../components/FilterPanel.vue'
import HotelList from '../components/HotelList.vue'

export default {
    name: 'SearchView',
    components: {
        FilterPanel,
        HotelList
    },
    data() {
        return {
            selectedDistance: 500,

            // filteredHotels: [],
            loading: true,
        }
    },

    methods: {
        getInput: function (newValue) {
            this.selectedDistance = newValue;
            // console.log(this.selectedDistance)
        }
    },
    // computed: {
    //     filteredHotels() {
    // const filtered = this.hotels.filter(hotel => hotel.distance <= this.selectedDistance);
    // console.log("filtered hotels", filtered);
    // return filtered
    // console.log(this.hotels.map((hotel) => {hotel.distance <= this.selectedDistance}))
    // const newHotel = this.hotels.map((hotel) => { hotel.distance <= this.selectedDistance })
    // return newHotel
}
</script>

<style scoped></style>