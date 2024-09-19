<script>
import axios from 'axios';

export default {
  data(){
    return{
        archetypeApiUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",
        archetypeList: [],
    }
  },
  components: {

  },
  methods: {
    getArchetype(){
        axios.get(this.archetypeApiUrl)
        .then(response => {
            this.archetypeList = response.data.slice(0, 80);
            console.log('archetypeList',this.archetypeList);
        })
        .catch(function (error) {
            console.log(error);
        })
        .finally(function () {

        })
    },
  },
  created(){
    this.getArchetype()
  }
}

</script>

<template>
    <div class="container">
        <select name="" id="select-archetype">
            <option value="#" disabled selected>Choose an Archetype</option>
            <option v-for="(item, index) in archetypeList" :key="index" :value="item.archetype_name">
                {{ item.archetype_name }}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
@use "./../../style/general.scss" as *;

.container{
    margin-bottom: 30px;
    background-color: #D78D44;

    #select-archetype{
        width: 175px;
        height: 25px;
    }
}

</style>
