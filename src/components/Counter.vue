<template>
   <div>
        <h1>{{ customTitle }}</h1>
        <h2> {{ counter }} <sup>2</sup> = {{ counter * counter }} </h2>
        <h2> {{ counter }} <sup>2</sup> = {{ squareCounter }} </h2>
        <h2> {{ counter }} <sup>2</sup> = {{ squareCounter }} </h2>
        <h2> {{ counter }} <sup>2</sup> = {{ squareCounter }} </h2>

        <button @click="increase()">+1</button>
        <button @click="decrease()">-1</button>
   </div>
</template>

<script>
export default {
    name: 'Counter',
    props:{
        titulo: String,
        start: {
            type: Number,
            default: 10,
            validator(value) {
                return value > 100
            }
        }
    },
    data() {
        return {
            counter: this.start
        }
    },
    methods: {
        getSquareValue() {
            return this.counter * this.counter
        },
        increase(){
            this.counter++
        },
        decrease(){
            if(this.counter > 0) this.counter-=1
        }
    },
    computed: {
        squareCounter() {
            return this.counter * this.counter
        },
        customTitle(){
            return this.titulo || 'Counter'
        }
    }
}
</script>

<style>

button {
    background-color: #64bb87;
    border-style: none;
    color: white;
    cursor: pointer;
    font-size: 14px;
    height: 20px;
    margin: 0 5px;
    width: 5%;
}

</style>