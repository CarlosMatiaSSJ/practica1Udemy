<script setup>
import { ref, computed } from "vue";

const name = "Vue 3";

const arrayNumeros = ref([]);

const counter = ref(0);

const increment = () => {
    counter.value++;
};

const decrement = () => {
    counter.value--;
};

const reset = () => {
    counter.value = 0;
};

const addNumer = () =>{
   arrayNumeros.value.push(counter.value);
};


  


const classCounter = computed(() => {
    if (counter.value === 0) {
        return "zero";
    }
    return counter.value > 0 ? "positive" : "negative";
});

</script>

<template>
    <h1>Hola {{ name }}!</h1>
    <h2 :class="classCounter">
        {{ counter }}
    </h2>
    <button @click="increment">Incremet</button>
    <button @click="decrement">Decrement</button>
    <button @click="reset">Reset</button>

      

    
    <ul>
      <li v-for="numeros in arrayNumeros">{{numeros}}</li>
    </ul>


    
 
   



</template>

<style>
.repeated{
  color: blueviolet;
}

.negative {
    color: red;
}

.positive {
    color: green;
}

.zero {
    color: peru;
}
</style>