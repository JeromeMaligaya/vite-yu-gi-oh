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
    <div class="container">
        <p class="card-found">Found <span><b>{{ cardsList.length }}</b></span> cards</p>
        <ul id="card-list">
            <ListCardsItem v-for="card in cardsList" :key="card.id"
            :name = 'card.name.toUpperCase()'
            :type = 'card.archetype'
            :imgUrl = 'card.card_images[0].image_url'
            />
        </ul>
    </div>
</template>

<style lang="scss">
    .container{
        background-color: #fff;
        padding: 30px; 
        
        .card-found{
            background-color: #000;
            color: #fff;
            padding:15px 10px;
            font-size: 12px;
        }
        #card-list{
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }
    }

</style>
