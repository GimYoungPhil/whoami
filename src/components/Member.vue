<template>
  <div class="card">
    <div class="card-image">
      <figure class="image">
        <img v-bind:src="member.imageURL" alt="Placeholder image">
      </figure>
    </div>
    <div class="card-content">
      <div class="content has-text-centered">
        <p class="title is-1">{{ member.koName }}</p>
        <p class="subtitle is-3">{{ member.enName }}</p>
      </div>
      <audio controls ref="audio" id="audio-example">
        <source v-bind:src="member.audio">
      </audio>
    </div>
  </div>
</template>

<script>
export default {

  props: [
    'member',
  ],

  mounted() {
    this.play()
  },

  updated() {
    this.play()
  },

  methods: {
    play() {
      this.$refs.audio.load()
      this.$refs.audio.play()
    }
  }
}
</script>

<style>

</style>
