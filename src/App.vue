<template>
  <div>
    <Card-vote  :seeds="seeds"  @add-vote="addVote" />
  </div>
</template>

<script>
import CardVote from './components/CardVote.vue'
import seeds from './seed' 
export default {
  components: {
    CardVote
  },
  data(){
    return {
       seeds:seeds.adherents
    }
  },
  methods: {
    addVote(seedId){
        const index=this.seeds.findIndex(seed=>seed.id===seedId)
        this.seeds[index].vote++

    }
  }
}
</script>

<style>


</style>
