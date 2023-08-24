<template>
<form>
    <input 
    id="distance" 
    type="range" 
    min="20" 
    max="2000"
    step="10"
    v-model="selectedDistance"
    style="width: 500px;"
    /><br>
    <label for="distance">Distance from Drammen: {{ this.selectedDistance }}km </label>
</form>
</template>

<script>
export default{
    data() {
        return{
            selectedDistance: 500,
        }
    }
}
</script>