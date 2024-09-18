<script>
import ListCardsItem from './ListCardsItem.vue';
import axios from 'axios';

export default {
  data(){
    return{
        apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
        cardsList:[],
    }
  },
  components: {
    ListCardsItem
  },
  methods: {
    getListCardsItem(){
        axios.get(this.apiUrl)
            .then( response => {
                this.cardsList = response.data.data;
                console.log('cardsList', this.cardsList)
            })
    }
  },
  mounted(){
    this.getListCardsItem()
  }
}
</script>

<template>
    <span>{{ cardsList.length }}</span>
    <ul>
        <ListCardsItem v-for="card in cardsList" :key="card.id"
        :name = 'card.name'
        :type = 'card.archetype'
        :imgUrl = 'card.card_images[0].image_url'
        />
    </ul>
</template>

<style lang="scss">

</style>
