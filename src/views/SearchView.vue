<template>
    <h1>
        Search
    </h1>
    <h3>
        Use the form to filter the hotels you wanna see
    </h3>
<FilterPanel v-model="selectedDistance"/>
<HotelList :hotels="filteredHotels"/>
</template>

<script>
import FilterPanel from '../components/FilterPanel.vue'
import HotelList from'../components/HotelList.vue'

export default{
 name: 'SearchView',
 components: {
    FilterPanel,
    HotelList
 },
 data() {
    return{
            selectedDistance: 500,
            hotels: [],
            filteredHotels: [],
        }
 },
    mounted(){
        fetch('http://localhost:3000/hotels')
        .then(res => res.json())
        .then(data => {
      console.log("Fetched data:", data); // Log the fetched data
      this.hotels = data;
    })
        .catch(err => console.log(err.message))
 },
    computed: {
    filteredHotels() {
            const filtered = this.hotels.filter(hotel => hotel.distance <= this.selectedDistance);
            console.log("filtered hotels", filtered);
            return filtered
        }
 }
}
</script>

<style scoped>

</style>