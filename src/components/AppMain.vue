<script>
import ListCards from './AppMain/ListCards.vue';
import MainSelect from './AppMain/MainSelect.vue';

export default {
  data(){
    return{

    }
  },
  components: {
    ListCards,
    MainSelect
  },
  methods: {

  },
}
</script>

<template>
    <main>
        <MainSelect />
        <ListCards />
    </main>
</template>

<style lang="scss" scoped>
   main{
    margin-top: 50px;
   }

</style>
