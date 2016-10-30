<template>
  <div id="app" class="container">
    <h3>Emoji Bouquet Generator</h3>
    <EmojiInput :option.sync="option"></EmojiInput>
    <BouquetCanvas :option.sync="option"></BouquetCanvas>
  </div>
</template>

<script>
import EmojiInput from './components/EmojiInput'
import BouquetCanvas from './components/BouquetCanvas'

export default {
  name: 'app',
  data() {
    return {
      option: {
        emoji: '🙄',
        number: 12
      }
    }
  },
  components: {
    EmojiInput, BouquetCanvas
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 16px;
}
</style>
