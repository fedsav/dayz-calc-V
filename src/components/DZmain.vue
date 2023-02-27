<template>
  <div class="wrap">
    <div class="wrap__main">
      <mainCalc :guns="guns"/>
      <div class="wrap__bottom">
        <mainMultiplier v-model:multiplier="multiplier"/>
        <mainSummary :totalDamage="totalDamage" :multiplier="multiplier" class="sum"/>
      </div>
    </div>
  </div>
</template>

<script>
import mainCalc from './main/mainCalc.vue';
import mainMultiplier from './main/mainMultiplier.vue';
import mainSummary from './main/mainSummary.vue';

export default {
  name: 'DZmain',

  components: {
    mainCalc,
    mainMultiplier,
    mainSummary,
  },

  computed: {
    totalDamage () {
      return this.guns.map((item) => {
        return Math.floor(item.quantity * item.dmg)
      }).reduce((a, b) => a + b)
    },
  },

  data () {
    return {
      guns: [
        {
          name: 'vsssval',
          title: 'SVAL / VSS',
          dmg: 75,
          id: 1,
          quantity: 0,
        },
        {
          name: 'aur',
          title: 'AUR-AX',
          dmg: 107.4,
          id: 2,
          quantity: 0,
        },
        {
          name: 'kam',
          title: 'AKM',
          dmg: 90.1,
          id: 3,
          quantity: 0,
        },
        {
          name: 'ka101',
          title: 'KA-101',
          dmg: 96.7,
          id: 4,
          quantity: 0,
        },
        {
          name: 'ak74',
          title: 'AK-74',
          dmg: 92,
          id: 5,
          quantity: 0,
        },
        {
          name: 'lar',
          title: 'LAR',
          dmg: 122.8,
          id: 6,
          quantity: 0,
        },
        {
          name: 'vsd',
          title: 'VSD',
          dmg: 144.8,
          id: 7,
          quantity: 0,
        },
        {
          name: 'm16lemas',
          title: 'LE-MAS / M16',
          dmg: 107.4,
          id: 8,
          quantity: 0,
        },
        {
          name: 'm4a1',
          title: 'M4A1',
          dmg: 96.7,
          id: 9,
          quantity: 0,
        },
        {
          name: 'blaze',
          title: 'BLAZE',
          dmg: 143.3,
          id: 10,
          quantity: 0,
        },
        {
          name: 'snipers',
          title: 'TUNDRA / MOSIN / SAVANNA',
          dmg: 150,
          id: 11,
          quantity: 0,
        },
        {
          name: 'sks',
          title: 'SK 59/66',
          dmg: 110,
          id: 12,
          quantity: 0,
        },
        {
          name: 'vaigaGreen',
          title: 'VAIGA-SLUGS',
          dmg: 99.5,
          id: 13,
          quantity: 0,
        },
        {
          name: 'vaigaRed',
          title: 'VAIGA-BUCK',
          dmg: 125.9,
          id: 14,
          quantity: 0,
        },
      ],

      multiplier: 1,
    }
  }
}

</script>

<style scoped lang="scss">
    .wrap__main {
        color: whitesmoke;
        min-height: 900px;
        background-color: #282A3A;
        margin: 20px;
        padding: 20px;
        border-radius: 15px;
    }

    .wrap__bottom {
      display: flex;
      justify-content: space-between;
      padding-top: 15px;
    }

    .sum {
      align-self: flex-end;
    }

    @media screen and (max-width: 760px) {
      .wrap__bottom {
        flex-direction: column;
      }
    
      .sum {
        align-self: center;
      }

      .wrap__main {
        margin: 10px;
        padding: 10px;
      }
    }

</style>