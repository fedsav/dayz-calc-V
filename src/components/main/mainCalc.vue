<template>
  <div class="calc" >
      <p class="calc__stepone">Step one</p>
      <p class="calc__steponeTxt">Just enter number of your rounds in corresponding field.</p>
    <div class="calc__cards">
      <gunCard v-for="gun in guns" 
      :gun="gun"  
      :key="gun.id"
      v-model="gun.quantity"/>
    </div>
  </div>
</template>

<script>
import gunCard from './gunCard.vue';

export default {
  name: 'mainCalc',

  components: {
    gunCard,
  },

  props: ['guns'],

}
</script>

<style scoped lang="scss">
  .calc {
    display: flex;
    flex-direction: column;

    .calc__cards {
      display: flex;
      justify-content: space-evenly;
      flex-wrap: wrap;
    }
  }

  @media screen and (max-width: 760px) { 
    .calc__cards {
      display: block;
    }
  }

</style>