<script>
export default {
  data(){
    return{

    }
  },
  props:{
    name:{
        type: String,
        Required: true
    },
    type:{
        type: String,
        Required: true
    },
    imgUrl:{
        type: String,
        Required: true
    },
  },
  components: {

  },
  methods: {

  },
}
</script>

<template>
    <li class="card">
        <img :src="`${imgUrl}`" alt="">
        <h4>{{ name }}</h4>
        <p>{{ type }}</p>
    </li>
</template>

<style lang="scss" scoped>
    @use "./../../style/general.scss" as *;

    .card{
        flex-basis: calc(20% - 60px / 5);
        background-color: #D78D44;

        h4,p{
            font-size: 10px;
            text-align: center;
            margin: 7px 3px;
        }

        h4{
            color: #fff;   
        }
    }

</style>
