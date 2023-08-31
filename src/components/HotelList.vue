<template>
  <div class="hotel-list">
    <h2>Filtered Hotels</h2>
    <ul>
      <li class="hotel" v-for="hotel in filteredHotels" :key="hotel.name">
        <h3> {{ hotel.name }} </h3>
        <p>{{ hotel.link }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    selectedDistance
  },
  data: {
    return: {
      hotels: [],
    }
  },
  mounted() {
    fetch('http://localhost:3000/hotels')
      .then(res => res.json())
      .then(data => {
        //   console.log("Fetched data:", data); // Log the fetched data
        this.loading = false
        this.hotels = data;
        console.log('new log', data)


      })
      .catch(err => console.log(err.message))
  },
  computed: {
    filteredHotels() {
      const newHotel = this.hotels.map((hotel) => { hotel.distance <= this.selectedDistance })
      return newHotel
    }
  }
}
</script>

<style scoped>
li {
  list-style-type: none;
  margin-bottom: 50px;
}
</style>