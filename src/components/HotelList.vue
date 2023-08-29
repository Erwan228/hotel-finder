<template>
  <div class="hotel-list">
    <h2>Filtered Hotels</h2>
    <ul>
      <li class="hotel" v-for="hotel in hotels" :key="hotel.name">
        <h3> {{ hotel.name }} </h3>
        <p>{{ hotel.link }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default{
       props: {
        hotels: {
            type: Array,
            required: true,
        }
       }
}
</script>

<style scoped>
li{
    list-style-type: none;
    margin-bottom: 50px;
    }
</style>