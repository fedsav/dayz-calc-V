<template>
  <div class="card">
    <p class="card__name">{{ gun.title }}</p>
    <div class="card__pic"></div>
    <input 
      type="number" 
      class="card__input"
      :value="gun.quantity"
      @input="$emit('update:modelValue', $event.target.value)">
  </div>
</template>

<script>
export default {
  name: 'gunCard',

  props: ['gun'],
  emits: ['update:modelValue'],

  computed: {
        picUrl () {
          return `url(${this.getUrl()})`
        },
    },

    methods: {
        getUrl () {
            return new URL(`/src/assets/images/${this.gun.name}.png`, import.meta.url).href
        },
    }
}

</script>

<style scoped lang="scss">
    .card {
      height: 135px;
      width: 250px;
      padding: 15px;
      background-color: #282A3A;
      border: 2px solid black;
      border-radius: 15px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 15px;
      

      .card__name {
        font-family: 'HaasBold';
        letter-spacing: 3px;
        word-wrap: break-word;
        text-align: center;
      }

      .card__pic {
        height: 70%;
        width: 90%;
        background-image: v-bind(picUrl);
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center;
      }

      .card__input {
        background-color: rgba(223, 215, 215, 0.6);;
        border: 2px solid black;
        border-radius: 10px;
        max-width: 80px;
        padding: 6px;
      }
    }
    
    @media screen and (max-width: 760px) {

      .card {
        height: 150px;
        width: 100px;
        padding: 6px;
        gap: 10px
      }

      .card__name {
        font-size: 0.8em;
      }
    }
</style>