<template>
  <div class="emoji-input">
    <div class="input-group">
      <span class="input-group-addon">选择表情</span>
      <input type="search" class="form-control" v-model="option.emoji" maxlength="1" />
      <div class="input-group-btn">
        <button type="button" class="btn btn-default" @click="toggleEmojiPicker">
          <span class="caret"></span></button>
        <button type="button" class="btn btn-primary">Generate</button>
      </div>
    </div>
    <div class="emoji-picker" v-if="showEmojiPicker">
      <Emojis @pick="handleEmojiPick" />
    </div>

  </div>
</template>

<script>
import Emojis from './Emojis'

export default {
  name: 'emoji-input',
  props: {
    option: {
      type: Object
    }
  },
  data () {
    return {
      showEmojiPicker: false
    }
  },
  methods: {
    toggleEmojiPicker() {
      this.showEmojiPicker = !this.showEmojiPicker
    },
    handleEmojiPick(c) {
      this.option.emoji = c
      this.showEmojiPicker = false
    }
  },
  components: {
    Emojis
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.emoji-picker {
  margin-top: .6em;
  position: relative;
}
.emoji-picker .emojis {
  background-color: white;
  position: absolute;
  z-index: 28;
  left: 0;
  right: 0;
}
</style>
