<template>
    <section>
        <ul>
            <li v-for="(food, index) in foodItems" :key="index">{{ food }}</li>
        </ul>
    </section>
</template>

<script>
export default {
    name: "FoodOrder",
    props: {
        foodItems: {
            type: Array
        },
    },
}
</script>

<style>

</style>