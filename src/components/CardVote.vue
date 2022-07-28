<template>
    <div>
        <div v-for="seed in sortByVote" :key="seed.id" class="container-adherent">
            <img :src='seed.img' alt="">
            <p class="card">

                <span class="card-span">Name: {{ seed.name }}</span>
                <span class="card-span">
                    vote :
                    <span 
                          :class="[seed.vote<=3? 'card-span-badge-white':seed.vote>10?'card-span-badge-blue':'card-span-badge-green']"
                          @click="addVote(seed.id)"
                          >
                        {{ seed.vote }}
                    </span>
                </span>

            </p>
        </div>
    </div>
</template>

<script>
export default {
    props: ["seeds", "sortByVote"],
    methods: {
        addVote(seedId) {
            this.$emit('add-vote', seedId);
        }
    },
}
</script>
<style>
.container-adherent {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background: rgba(71, 74, 250, 0.726);
    /* width:100%; */
    /* max-width: 25%; */
    width: 400px;
    height: 150px;
    margin: 10px 30px;
    border-radius: 10px
}

img {
    border-radius: 50%;
    width: 90px
}

.card {
    background: rgb(167, 179, 248);
    border-radius: 5px;

}

.card-span {
    display: block;
    font-size: 20px;
    padding: 10px 50px
}

.card-span-badge-white {
    border-radius: 10px;
    background-color: rgb(255, 255, 255);
    font-size: 20px;
    padding: 5px 7px;
    margin-left: 10px;
    cursor: pointer;
}
.card-span-badge-green {
    border-radius: 10px;
    background-color: rgb(121, 247, 48);
    font-size: 20px;
    padding: 5px 7px;
    margin-left: 10px;
    cursor: pointer;
}
.card-span-badge-blue {
    border-radius: 10px;
    background-color: rgb(55, 171, 248);
    font-size: 20px;
    padding: 5px 7px;
    margin-left: 10px;
    cursor: pointer;
}

</style>