<template>
  <div class="drum-kit">
    <h1>JS Drumkit</h1>
      <div class="container__keys">
        <div class="key">
        <button
          @click.prevent="playSound('http://soundbible.com/mp3/Tinkle-Lisa_Redfern-1916445296.mp3')"
          >
        <kbd>A</kbd>
        <span class="sound">stars</span>
        </button>
      </div>
      <div class="key">
        <button
          @click.prevent="playSound('http://soundbible.com/mp3/Accordion-SoundBible.com-74362576.mp3')"
          >
        <kbd>S</kbd>
        <span class="sound">trumppet</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/front-desk-bells-daniel_simon.mp3')"
        >
        <kbd>D</kbd>
        <span class="sound">dream</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Judges Gavel-SoundBible.com-1321455227.mp3')"
        >
        <kbd>F</kbd>
        <span class="sound">accordion</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Music_Box-Big_Daddy-1389738694.mp3')"
        >
        <kbd>G</kbd>
        <span class="sound">bell</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Temple Bell Bigger-SoundBible.com-1940249027.mp3')"
        >
        <kbd>H</kbd>
        <span class="sound">shoot</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/killdeer_song-Mike_Koenig-1144525481.mp3')"
        >
        <kbd>J</kbd>
        <span class="sound">box</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Coin_Drop-Willem_Hunt-569197907.mp3')"
        >
        <kbd>K</kbd>
        <span class="sound">bum</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Demon_Girls_Mockingbir-Hello-1365708396.mp3')"
        >
        <kbd>L</kbd>
        <span class="sound">whistle</span>
        </button>
      </div>
      <div class="key">
        <button
        @click.prevent="playSound('http://soundbible.com/mp3/Tinkle-Lisa_Redfern-1916445296.mp3')"
        >
        <kbd>Ñ</kbd>
        <span class="sound">coins</span>
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
        65: 'http://soundbible.com/mp3/Tinkle-Lisa_Redfern-1916445296.mp3',
        68: 'http://soundbible.com/mp3/Demon_Girls_Mockingbir-Hello-1365708396.mp3',
        83: 'http://soundbible.com/mp3/Bike Horn-SoundBible.com-602544869.mp3',
        70: 'http://soundbible.com/mp3/Accordion-SoundBible.com-74362576.mp3',
        71: 'http://soundbible.com/mp3/front-desk-bells-daniel_simon.mp3',
        72: 'http://soundbible.com/mp3/Judges Gavel-SoundBible.com-1321455227.mp3',
        74: 'http://soundbible.com/mp3/Music_Box-Big_Daddy-1389738694.mp3',
        75: 'http://soundbible.com/mp3/Temple Bell Bigger-SoundBible.com-1940249027.mp3',
        76: 'http://soundbible.com/mp3/killdeer_song-Mike_Koenig-1144525481.mp3',
        186: 'http://soundbible.com/mp3/Coin_Drop-Willem_Hunt-569197907.mp3',
      },
    };
  },
  created() {
    window.addEventListener('keydown', (e) => {
      if (e.keyCode) {
        const link = this.sounds[e.keyCode];
        this.playSound(link);
      }
    });
  },

  methods: {
    playSound(sound) {
      if (sound) {
        const audio = new Audio(sound);
        if (!audio) return;
        audio.currentTime = 0;
        audio.play();
      }
    },
  },
};

</script>

<style lang="scss" scoped>

.drum-kit {
  background-image: url('../assets/b9r5sEL.jpg');
  background-repeat: no-repeat;
  height: 100%;
  width: 100%;
  margin: 0;
  h1 {
    font-size: 50px;
    color: palevioletred;
    font-weight: bolder;
    margin: 0;
  }
}

html {
  font-size: 10px;
  background-image: url('../assets/b9r5sEL.jpg');
  bottom: center;
  background-size: cover;
  margin: 0;
  
}

body,html {
  margin: 0;
  padding: 0;
  font-family: sans-serif;
}

.container {
  display: flex;
  flex-wrap: wrap;
  &__keys {
    display: flex;
    flex: 1;
    flex-wrap: wrap;
    min-height: 100vh;
    align-items: center;
    justify-content: center;
  }
}

.key {
  border: .4rem solid black;
  border-radius: .5rem;
  margin: 1rem;
  font-size: 1.5rem;
  padding: 1rem .5rem;
  transition: all .07s ease;
  width: 10rem;
  text-align: center;
  color: white;
  background: rgba(0,0,0,0.4);
  text-shadow: 0 0 .5rem black;
}

.playing {
  transform: scale(1.1);
  border-color: #ffc600;
  box-shadow: 0 0 1rem #ffc600;
}

kbd {
  display: block;
  font-size: 4rem;
}

.sound {
  text-transform: uppercase;
  letter-spacing: .1rem;
  color: #ffc600;
}

</style>
