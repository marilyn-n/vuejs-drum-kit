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
        @click.prevent="playSound('http://soundbible.com/mp3/killdeer_song-Mike_Koenig-1144525481.mp3')"
        >
          J
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Coin_Drop-Willem_Hunt-569197907.mp3')"
        >
          K
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Demon_Girls_Mockingbir-Hello-1365708396.mp3')"
        >
          L
        </button>
      </div>
      <div>
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Tinkle-Lisa_Redfern-1916445296.mp3')"
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
      sounds: { 
        '65' : 'http://soundbible.com/mp3/Tinkle-Lisa_Redfern-1916445296.mp3',
        '68' : 'http://soundbible.com/mp3/Demon_Girls_Mockingbir-Hello-1365708396.mp3',
        '83' : 'http://soundbible.com/mp3/Bike Horn-SoundBible.com-602544869.mp3',
        '70' : 'http://soundbible.com/mp3/Accordion-SoundBible.com-74362576.mp3',
        '71' : 'http://soundbible.com/mp3/front-desk-bells-daniel_simon.mp3',
        '72' : 'http://soundbible.com/mp3/Judges Gavel-SoundBible.com-1321455227.mp3',
        '74' : 'http://soundbible.com/mp3/Music_Box-Big_Daddy-1389738694.mp3',
        '75' : 'http://soundbible.com/mp3/Temple Bell Bigger-SoundBible.com-1940249027.mp3',
        '76' : 'http://soundbible.com/mp3/killdeer_song-Mike_Koenig-1144525481.mp3',
        '186': 'http://soundbible.com/mp3/Coin_Drop-Willem_Hunt-569197907.mp3'
      }
    };
  },
  created() {
    window.addEventListener('keydown', (e) => {
      if (`data-key="${e.keyCode}"`) {
        const link = this.sounds[e.keyCode]
        this.playSound(link)
      }
    })
  },

  methods: {
    playSound(sound) {
      if (sound) {
       const audio = new Audio(sound);
       audio.play();
      }
    },
  },
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
