<template>
    <div>
      <h2>{{ customTitle }}</h2>
    <!-- <p>{{ counter }} Contador: {{ squareCounter }}</p> -->
    <!-- <p>{{ counter }} Contador: {{ squareCounter }}</p> -->
    <!-- <button @click="sumarCounter()">+ 1</button>  --><!-- @ == v-on -->
    <!-- <button v-on:click="restarCounter()">- 1</button> -->
  </div>
</template>

<script>

export default {
    props: { // Parametros recibidos desde el padre
        title: String,
        start: {
            type: Number,
            default: 100,
            required: true,
            validator( value ) {
                return value < 100
            }
        }
    }, 
    name: 'Contador',
    data() {
        return {
            counter: this.start
        }
    },
    methods: {
        getSquareValue(){ 
            return this.counter * this.counter;
        },
        sumarCounter(){
            this.counter++;
        },
        restarCounter(){
            this.counter--;
        }

    },
    computed: {
        squareCounter() {
            return this.counter * this.counter
        },
        customTitle(){
            return this.title ||  'Counter'
        }
    }
}
</script>

<style>

    button {
        /* margin: 0 5px; */
        background-color: #64B687;
        /* border: 1px; */
        /* margin: 0 5px; */
    }

</style>