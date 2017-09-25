<template>
  <div id="app" class="container is-fullhd">
    <div class="columns">
      <div class="column is-2">
        <Family v-bind:family="family" v-on:select="selectMember"></Family>
      </div>
      <div class="column">
        <Member v-bind:member="selected"
                v-if="selected"></Member>
      </div>
    </div>
  </div>
</template>

<script>
import Member from './components/Member.vue'
import Family from './components/Family.vue'
import data from './data'

export default {
  name: 'app',

  components: {
    Member,
    Family,
  },

  methods: {
    selectMember: function(enName) {
      this.current = enName
    }
  },

  computed: {
    selected: function() {
      return this.family.find(member => member.enName === this.current)
    }
  },

  data () {
    return {
      current: undefined,
      family: data
    }
  }
}
</script>

<style>

</style>
