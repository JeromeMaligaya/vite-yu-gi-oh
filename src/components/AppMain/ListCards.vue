<script>
import ListCardsItem from './ListCardsItem.vue';
import axios from 'axios';

export default {
  data(){
    return{
        apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
    }
  },
  components: {
    ListCardsItem
  },
  methods: {

  },

}
</script>

<template>
    <ul>
        <ListCardsItem />
    </ul>
</template>

<style lang="scss">

</style>
