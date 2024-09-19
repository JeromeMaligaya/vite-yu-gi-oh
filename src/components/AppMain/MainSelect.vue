<script>
export default {
  data(){
    return{

    }
  },
  components: {

  },
  methods: {

  },
}
</script>

<template>
    <div class="container">
        <select name="" id="select-archetype">
            <option selected disabled>Choose an archetype</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
@use "./../../style/general.scss" as *;

.container{
    margin-bottom: 30px;
    background-color: #D78D44;

    #select-archetype{
        width: 150px;
        height: 25px;
    }
}

</style>
