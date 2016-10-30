<style scoped>
.emojis {
    font-size: 2em;
    line-height: 1;
    display: flex;
    flex-wrap: wrap;
}
.emoji {
    margin: .3em;
}
</style>

<template>
<div class="emojis" @click="handleEmojiClick($event)">
    <span class="emoji" v-for="(icon, index) in emoticons" v-bind:data-index="index">{{icon}}</span>
</div>
</template>

<script>
export default {
  name: 'emojis',
  props: {

  },
  data() {
    let emoticons = [];
    for (let i = 0; i < 80; i++) {
        emoticons.push(String.fromCharCode(0xd83d) + String.fromCharCode(i + 0xde00));
    }

    return {
        emoticons
    }
  },
  computed: {

  },
  methods: {
    handleEmojiClick(evt) {
        var i = window.parseInt(evt.target.dataset.index, 10);
        if (window.isNaN(i)) {
            return
        }
        this.$emit('pick', this.emoticons[i]);
    }
  },
  events: {

  },
  components: {

  },
  ready() {

  }
}
</script>
