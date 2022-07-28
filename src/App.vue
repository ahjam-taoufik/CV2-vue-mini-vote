<template>
  <div>
    <Card-vote :seeds="seeds" :sortByVote="sortByVote"  @add-vote="addVote" />
  </div>
</template>

<script>
import CardVote from './components/CardVote.vue'
import seeds from './seed'
export default {
  components: {
    CardVote
  },
  data() {
    return {
      seeds: seeds.adherents
    }
  },
  methods: {
    addVote(seedId) {
      const index = this.seeds.findIndex(seed => seed.id === seedId)
      this.seeds[index].vote++

    }
  },
  computed: {
    sortByVote(){
      // eslint-disable-next-line vue/no-side-effects-in-computed-properties
      return this.seeds.sort((a,b)=>{
       return b.vote - a.vote;
     })
    }
  }
}
</script>

<style>
</style>
