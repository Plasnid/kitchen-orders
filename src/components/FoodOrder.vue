<template>
    <section>
        <h3 v-if="foodItems.length==0">Please Place Your Order</h3>
        <h3 v-else-if="foodItems.length>0 && foodItems.length<5">Working On Your Order</h3>
        <h3 v-else>The Kitchen Is Overloaded!</h3>

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

<style scoped>

</style>