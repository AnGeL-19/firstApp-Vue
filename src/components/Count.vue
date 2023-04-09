

<script lang="ts">

    export default {
        
        props: {
            count: {
                type: Number,
                default: 0
            }        
        },
        data() {
            return {
                counter: this.count
            }
        },
        methods: {
            increment() {
                this.counter++
            },
            decrement() {
                if (this.counter <= 0) return
                this.counter--  
            },
            reset() {
                this.counter = this.count
            }
        },
        mounted() {
            // this.increment()
        }
    }

</script>


<template lang="">
    <div class="container">

        <div class="modify">
            <button @click="decrement" >-</button>
            <span>Count number:{{ counter }}</span>
            <button @click="increment">+</button>
        </div>
        <span v-if="counter <= 0" class="negative">The number can't be negative</span>
        <div>
            <button @click="reset">Reset</button>
        </div>

    </div>
</template>

<style scoped>
    
    .container{
        width: 40%;
        display:flex;
        flex-direction: column;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
    }

    .negative{
        color: rgb(238, 20, 20);
    }

    .modify{
        width: 100%;
        height: auto;
        display: flex;
        justify-content: space-between;
    }

    span{
        width: auto;
        height: auto;
        font-size: 20px;
    }

    button{
        min-width:20px;
        min-height: 20px;
        padding: 10px;
    }

</style>