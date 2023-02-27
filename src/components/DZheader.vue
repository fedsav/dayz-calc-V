<template>
  <div class="header">

    <div class="header__title">
      <p class="header__welcome">
        Welcome to
      </p>
      <div class="header__dayz">
        <div>DayZ</div>
        <div>Raid</div>
        <div>Calculator</div>
      </div>
    </div>

    <div class="header__content">
      <div class="header__txt">
        Greetings, survivor! Here you can experience one of the most useful tools in DayZ made by an experienced player. Never know if you have enought resourses to ruin your opponents base? Well today is the day of truth. The process of counting is pretty simple and intuitive, so lets get into it!
      </div>
      <button 
        class="header__faq" 
        @click="openModal">
        But maybe you need a FAQ?
      </button>
      <Teleport to="body" >
        <transition name="fade">
          <Modal v-show="visible" @closeModal="visible = false"/>
        </transition>
      </Teleport>
    </div>
  </div>
</template>

<script>
import Modal from './modal.vue';

export default {
  name: 'DZheader',

  components: {
    Modal,
  },

  data () {
    return {
      visible: false,
    }
  },

  methods: {
    openModal () {
      this.visible = true
    },
  }
}

</script>

<style scoped lang="scss">

    

    @keyframes animate-colour {
      from {
        background-position: 0% center;
      }

      to {
        background-position: -200% center;
      }
    }

    .header {
      min-height: 160px;
      margin: 20px;
      color: whitesmoke;

      .header__title {
        display: flex;
        flex-direction: column;
        gap: 5px;
        font-family: 'HaasBold';
        font-size: 46px;
        padding: 20px;
        flex-wrap: wrap;
        word-break: break-all;
      }

      .header__dayz {
        animation: animate-colour 5s linear infinite;
        background: linear-gradient(
          to right,
          #159f5f,
          #f7ca13,
          #ecca1e,
          #159f5f,
        );

        background-size: 200%;
        background-clip: text;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        white-space: nowrap;
        font-size: 1.3em;

        display: flex;
        gap: 10px;
        flex-wrap: wrap;
      }

      .header__content {
        background-color: #282A3A;
        padding: 20px;
        border-radius: 15px;
      }

      .header__txt {
        font-family: 'HaasRoman';
        font-size: 24px;
        margin: 10px;
        text-align: justify;
      }

      .header__faq {
        cursor: pointer;
        margin: 10px;
        padding: 10px;
        font-family: 'HaasBold';
        font-size: 20px;
        border-radius: 6px;
        border: solid black 2px;
        background-color: #159f5f;
      }
    }

    .fade-enter-active,
    .fade-leave-active {
      transition: opacity 0.5s ease;
    }

    .fade-enter-from,
    .fade-leave-to {
      opacity: 0;
    }

    @media screen and (max-width: 760px) {
      .header {
        margin: 10px;
      }
    }
</style>