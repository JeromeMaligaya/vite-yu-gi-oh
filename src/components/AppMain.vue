<script>
import ListCards from './AppMain/ListCards.vue';
import MainSelect from './AppMain/MainSelect.vue';
import axios from 'axios';


export default {
  data(){
    return{
      apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
      cardsList:[],
    }
  },
  components: {
    ListCards,
    MainSelect
  },
  methods: {
    getListCardsItem(archetypeSearched = ""){
      console.log(archetypeSearched)

      if (archetypeSearched) {
        this.apiUrl += `&archetype=${encodeURIComponent(archetypeSearched)}`;
      }

      axios.get(this.apiUrl)
        .then( response => {
          this.cardsList = response.data.data;
          console.log('cardsList', this.cardsList)
        }
      )
    }
  },
  mounted(){
    this.getListCardsItem()
  },
}
</script>

<template>
    <main>
        <MainSelect @select-archetype="getListCardsItem"/>
        <ListCards :cardsList="cardsList"/>
    </main>
</template>

<style lang="scss" scoped>
   main{
    margin-top: 50px;
   }

</style>
