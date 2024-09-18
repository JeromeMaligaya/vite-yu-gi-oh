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
    <li>
        <img :src="`${imgUrl}`" alt="">
        {{ name }}
        {{ type }}
    </li>
</template>

<style lang="scss" scoped>
    @use "./../../style/general.scss" as *

</style>
