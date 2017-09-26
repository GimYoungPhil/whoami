<template>
  <div class="columns is-gapless is-multiline is-mobile">
    <div class="column is-one-quarter-mobile is-12-desktop" v-for="(member, index) in family" v-bind:key="index">
      <button class="button has-text-centered is-family"
              v-bind:class="[member.color]"
              v-on:click="select(member.enName)">
        <figure class="">
          <img class="img-family" v-bind:src="member.imageThmb">
        </figure>
      </button>
    </div>
  </div>
</template>

<script>
export default {

  props: [
    'family'
  ],

  methods: {
    select: function (enName) {
      this.$emit('select', enName)
    }
  }
}
</script>

<style>
.is-family {
  height: 100%;
}

.img-family {
  border-radius: 50%;
  width: 100px;
  height: 100px;
}
</style>
