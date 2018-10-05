<template>
  <div class="drum-kit">
    <h2>Drum kit</h2>
      <div class="container">
        <div>
        <button
          @click.prevent="playSound('http://soundbible.com/mp3/Bike Horn-SoundBible.com-602544869.mp3')"
          >
          A
        </button>
      </div>
      <div>
        <button>
          S
        </button>
      </div>
      <div>
        <button>
          D
        </button>
      </div>
      <div>
        <button>
          F
        </button>
      </div>
      <div>
        <button>
          G
        </button>
      </div>
      <div>
        <button>
          H
        </button>
      </div>
      <div>
        <button>
          J
        </button>
      </div>
      <div>
        <button>
          K
        </button>
      </div>
      <div>
        <button>
          L
        </button>
      </div>
      <div>
        <button>
          Ñ
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DrumKit',
  data() {
    return {
    };
  },

  methods: {
    playSound(sound) {
      console.log('clicked!')
      if (sound) {
       const audio = new Audio(sound)
       audio.play() 
      }
    },
  }
};

</script>

<style scoped>

.drum-kit {
  background-image: url('../assets/drum-kit.jpg');
  background-repeat: no-repeat;
  height: 750px ;
  width: 100%;
}

.container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-content: center;
}

</style>
