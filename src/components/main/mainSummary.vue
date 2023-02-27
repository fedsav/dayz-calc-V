<template>
  <div class="summary">
    <p class="summary__text">Well, you can successfully raid</p>
    <div class="summary__doors">{{ totalDoors }}</div>
    <p class="summary__text">doors</p>
  </div>
</template>

<script>
export default {
    name: 'mainSummary',

    props: ['totalDamage', 'multiplier'],

    computed: {
        totalDoors () {
            return Math.floor(this.totalDamage / (28500 * this.multiplier))
        },
        doorHP () {
          return 28500 * this.multiplier
        }
    }
}

</script>

<style scoped lang="scss">
    .summary {
        padding-top: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 15px;
        max-width: 600px;
    }

    @keyframes animate-colour {
        from {
          background-position: 0% center;
        }
  
        to {
          background-position: -200% center;
        }
      }

    .summary__doors {
        min-height: 120px;
        min-width: 120px;
        background-color: #159f5f;
        font-family: 'HaasBold';
        display: flex;
        flex-direction: column;
        justify-content: center;
        text-align: center;
        font-size: 58px;
        border-radius: 50%;
        border: solid black 6px;
    }

    .summary__text {
        font-family: 'HaasRoman';
        font-size: 24px;
    }
</style>