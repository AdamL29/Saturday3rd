<template>
    <div>
        <h1>{{foodName}}</h1>
        <p>In stock: {{stock}}</p>
        <img :src="foodImage">
        <button @click="addToCart">Add to Cart</button>
    </div>
</template>

<script>
    export default {
        name: "FoodCard",
        props: {
            foodName: String,
            foodImage: {
                type: String,
                default: "https://m.media-amazon.com/images/I/61je8va-QgL._AC_SY450_.jpg",
            },
            stock: Number
        },
        methods: {
            addToCart() {
                this.$emit(`buyItem`, this.foodName)
            },
            toggleDarkMode(){
                console.log("Dark mode toggled in food card for: "+this.foodName);
            }
        },
        mounted(){
            this.$root.$on(`toggleDark`, this.toggleDarkMode);
        }
    }
</script>

<style scoped>
    img{
        width: 30vw;
    }
    div{
        border: navy 1px solid;
        width: 50vw;
        position: relative;
        left: 50vw;
        transform: translateX(-50%);
    }
</style>