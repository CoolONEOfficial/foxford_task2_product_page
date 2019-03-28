<template>
    <div>
        <v-icon :key="index" v-for="index of Array(5).keys()" size="12px" color="#003980" class="pr-1" @click="stars = index + 1">fa{{index >= stars ? 'r' : 's'}} fa-star</v-icon>
    </div>
</template>

<script>
    export default {
        name: "Rating",
        props: ["stars"],
    }
</script>

<style scoped>

</style>