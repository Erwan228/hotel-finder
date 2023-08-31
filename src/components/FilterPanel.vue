<template>
    <div class="filterPanel">
        <form>
            <input @change="emitFunc(this.value)" id="distance" type="range" min="20" max="2000" step="10"
                v-model="selectedDistance" style="width: 500px;"><br>
            <label for="distance">Distance from Drammen: {{ this.selectedDistance }}km </label>
        </form>
    </div>
</template>

<script>
export default {
    props: {
        value: {
            type: Number,
            required: true,
        },
    },
    data() {
        return {
            selectedDistance: 500
        }
    },
    methods: {
        emitFunc(value) {
            this.$emit("distance", this.selectedDistance)
        }
    },
    watch: {
        selectedDistance(newValue) {
            console.log(this.selectedDistance);
            this.$emit("input", newValue);
        }
    }
}
</script>