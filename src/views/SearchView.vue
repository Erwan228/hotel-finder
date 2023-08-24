<template>
    <h1>
        Search
    </h1>
    <h3>
        Use the form to filter the hotels you wanna see
    </h3>
<FilterPanel/>
<HotelList/>
</template>

<script>
import FilterPanel from '../components/FilterPanel.vue'
import HotelList from'../components/HotelList.vue'

export default{
 name: 'SearchView',
 components: {
    FilterPanel,
    HotelList
 }
}
</script>

<style scoped>

</style>