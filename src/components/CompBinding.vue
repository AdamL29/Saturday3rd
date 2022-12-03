<template>
    <div>
        {{counter}} <!-- Binding variable-->
        {{counter > 5 ? "large" : "small"}}
        <!-- Below removes the mounted section for the event listener -->
        <button @click="increment">Increment</button>
        <button @click="toggleImage">Show/Hide Image</button>
        <!-- @ only works with JS actions; All lowercase -->

        <!-- Binding the image -->
        <!-- v-if statement with v-else -->
        <img v-if="isImageVisible" :src="imgSrc" alt="">
        <!-- Above with the toggleImage is now works with a boolean IF to show and remove the image -->
        <!-- Above IF is linked to METHODS -->
        <h3 v-else>No Image Available</h3>

        
        <!-- 2 ways to right the v-for loop -->
        <p v-for="(item,index) in foods" :key="index">
        <!-- index cover lists with matching items/arrays -->
        <!-- <p v-for="item in foods" :key="item">  -->
            <!-- :key binds the key to the item -->
            {{index}} {{item}} 
        </p>
    </div>
</template>

<script>
    export default {
        name: "CompBinding",
        data(){
            return{
                counter: 0,
                isImageVisible : false,
                imgSrc : "https://i5.walmartimages.com/asr/8ca44267-6301-42d1-9bcc-d2b0bd839f91.54920c2e6be1b154de49b324995fc10c.jpeg?odnHeight=2000&odnWidth=2000&odnBg=ffffff",
                foods: [`fettuccine`, 
                        `watermelon`, 
                        `lasagna`, 
                        `tacos`,
                        `donair poutine`, 
                        `buddha bowl`, 
                        `pizza`, 
                        `dates`],
            }
        },
        methods: {
            // Changes the number and the image when the button is clicked.
            increment() {
                this.counter++;
                this.imgSrc ="https://m.media-amazon.com/images/I/61je8va-QgL._AC_SY450_.jpg";
            },
            toggleImage(){
                this.isImageVisible = !this.isImageVisible;
            }
        },
    }
</script>

<style scoped>
    img{
        width: 40vw;
    }
</style>