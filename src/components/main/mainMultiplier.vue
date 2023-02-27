<template>
  <div class="multi">
    <p class="multi__steptwo">Step two</p>
    <p class="multi__steptwoTxt">Select correct door HP multiplier set on your server</p>
    <div class="multi__form">
        
        <input type="radio"  
               class="multi_radio" 
               name="multiplier" 
               id="x1"
               checked
               :value="multiplier"
               @input="$emit('update:multiplier', 1)">
        <label class="multi_label" for="x1">x1</label>


        <input type="radio" 
               class="multi_radio" 
               name="multiplier"
               id="x1.5" 
               :value="multiplier"
               @input="$emit('update:multiplier', 1.5)">
        <label class="multi_label" for="x1.5">x1.5</label>
 

        <input type="radio" 
               class="multi_radio" 
               name="multiplier" 
               id="x2"
               :value="multiplier"
               @input="$emit('update:multiplier', 2)">
        <label class="multi_label" for="x2">x2</label>
 
    </div >
  </div>
</template>

<script>

export default {
    name: 'mainMultiplier',

    props: ['multiplier'],
    emits: ['update:multiplier']
}
</script>

<style>
    .multi {
        display: flex;
        flex-direction: column;
    }
    .multi__form {
        align-self: center;
        display: flex;
        justify-content: center;
        overflow: hidden;
        border: solid black 6px;
        border-radius: 10px;
        max-width: 400px;
    }

    .multi_radio {
        display: none;
    }
    
    .multi_label {
        flex-grow: 1;
        text-align: center;
        padding: 30px;
        font-family: 'HaasBold';
        font-size: 30px;
        background-color: #159f5f;
        cursor: pointer;
        transition: background-color 0.5s;
    }

    .multi_label:not(:last-of-type) {
        border-right: 6px solid black;
    }
    
    .multi_radio:checked + .multi_label {
        background-color: #9acd32;
    }

</style>