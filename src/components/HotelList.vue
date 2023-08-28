<template>
    <div class="hotelList" v-for="hotel in hotels">
        <p><a :href="hotel.link">{{ hotel.name }}</a></p>
    </div>
</template>

<script>
export default{
       
}
</script>