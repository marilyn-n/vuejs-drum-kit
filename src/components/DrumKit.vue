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
        <button
          @click.prevent="playSound('http://soundbible.com/mp3/Accordion-SoundBible.com-74362576.mp3')"
          >
          S
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/front-desk-bells-daniel_simon.mp3')"
        >
          D
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Judges Gavel-SoundBible.com-1321455227.mp3')"
        >
          F
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Music_Box-Big_Daddy-1389738694.mp3')"
        >
          G
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Temple Bell Bigger-SoundBible.com-1940249027.mp3')"
        >
          H
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/')"
        >
          J
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/')"
        >
          K
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/')"
        >
          L
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/')"
        >
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
