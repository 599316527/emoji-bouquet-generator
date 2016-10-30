<style scope>
.bouquet-canvas {
    margin: 1em;
    font-size: 1em;
    position: relative;
    transform: scale(1.38);
    transform-origin: 0 0;
}
.bouquet-canvas .emoji {
    position: absolute;
}
</style>

<template>
<div class="bouquet-canvas">
    <div class="emoji" v-for="i in option.number"
        :style="getEmojiPos(i - 1)">{{option.emoji}}</div>
</div>
</template>

<script>


const EMOJI_POS_MAP = [
    {
        left: 5,
        top: 5,
        rotate: -15,
        scale: 2
    },
    {
        left: 60,
        top: 2,
        rotate: -8,
        scale: 2
    },
    {
        left: 125,
        top: 3,
        rotate: 5,
        scale: 1.3
    },
    {
        left: 171,
        top: 1,
        rotate: -140,
        scale: .9
    },
    {
        left: 21,
        top: 52,
        rotate: 110,
        scale: 1.2
    },
    {
        left: 5,
        top: 79,
        rotate: -3,
        scale: 1.8
    },
    {
        left: 48,
        top: 52,
        rotate: 4,
        scale: 3.3
    },
    {
        left: 105,
        top: 30,
        rotate: 24,
        scale: 2.8
    },
    {
        left: 155,
        top: 28,
        rotate: 38,
        scale: 1.6
    },
    {
        left: 156,
        top: 56,
        rotate: 20,
        scale: 2.2
    },
    {
        left: 16,
        top: 116,
        rotate: 15,
        scale: 3.1
    },
    {
        left: 100,
        top: 92,
        rotate: -22,
        scale: 4.5
    }
]

export default {
  name: 'bouquet-canvas',
  props: {
    option: {
        type: Object
    }
  },
  data() {
    return {

    }
  },
  computed: {
    emojis() {
        let {emoji, number} = this.option
        let emojis = []
        for (let i = number.length - 1; i >= 0; i--) {
            emojis[i] = getEmojiPos(i)
        }
    }
  },
  methods: {
    getEmojiPos(i) {
        // TODO: generating emoji position randomly
        let {left, top, rotate, scale} = EMOJI_POS_MAP[i]
        // return `translate(${left}px, ${top}px) rotate(${rotate}deg) scale(${scale})`
        return {
            // position: 'absolute',
            left: `${left}px`,
            top: `${top}px`,
            transform: `rotate(${rotate}deg)`,
            fontSize: `${scale}em`
        }
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
