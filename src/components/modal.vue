<template>
  <div class="modal">
    <div class="modal__content">
        
        <div class="modal__qa">
            <p class="modal__q">How much HP is 1 door/fence?</p>
            <p class="modal__a">The whole emout of HP of door (main section + carcass) is approximately 28 500 hp. This number is based on gun HP damage and number of rounds shot in the wooden fence.</p>
        </div>
        <div class="modal__qa">
            <p class="modal__q">But how do you know the exact damge of all the weapons?</p>
            <p class="modal__a">All stats taken from <a href="https://wobo.tools/" class="modal__a" style="text-decoration: underline solid whitesmoke 1px">wobo.tools</a> You can find a lot off useful stuff there!</p>
        </div>
        <div class="modal__qa">
            <p class="modal__q">Why some weapons located in one section?</p>
            <p class="modal__a">Because they have the same damage (if you shoot point blank). Just like, for example, mosin, tundra and savanna</p>
        </div>
        <div class="modal__qa">
            <p class="modal__q">How accurate the countings are?</p>
            <p class="modal__a">While testing i was not trying to damage the carcass by shooting throung the min section of the wall, so final number may look overrated, but you can be 100% confident in results.</p>
        </div>
        <div class="modal__qa">
            <p class="modal__q">Why not all weapons mentioned?</p>
            <p class="modal__a">I decided to include weapons that are more efficient and used more often. So no BK-18 and etc.</p>
        </div>
        <button class="modal__close" @click="$emit('closeModal')">CLOSE</button>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Modal',

    emits: ['closeModal']

}
</script>

<style scoped lang="scss">


    .modal {
        position: fixed;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        display: flex;
        justify-content: center;
        background-color: #000000da;

        .modal__content {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
            background-color: #282A3A;
            border: 6px solid black;
            height: 500px;
            width: 500px;
            margin-top: 15%;
            padding: 50px 20px;
            border-radius: 20px;
        }

        .modal__qa {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-bottom: 18px;
        }

        .modal__q {
            font-family: 'HaasBold';
            font-size: 1.3em;
        }

        .modal__a {
            font-family: 'HaasRoman';
            text-align: justify;
        }
        
        .modal__a, .modal__q {
            color: whitesmoke;
        }
        
        .modal__close {
            cursor: pointer;
            align-self: flex-end;
            padding: 15px;
            background: #159f5f;
            border: solid black 2px;
            font-family: 'HaasBold';
            border-radius: 15px;
        }
    }

    @media screen and (max-width: 760px) {
        .modal__a, .modal__q {
            font-size: 0.9em;
        }

        .modal__close {
            left: 80%;
        }
    }
</style>