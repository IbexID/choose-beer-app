<template>
  <div class="beer__list">
    <li class="item__list"><b>Brand: </b> <span>{{sort.brand}}</span></li>
    <li class="item__list"><b>Name: </b> <span>{{sort.name}}</span></li>
    <li class="item__list"><b>Style: </b> <span>{{sort.style}}</span></li>
    <li class="item__list"><b>IBU: </b> <span>{{sort.ibu}}</span></li>
    <li class="item__list"><b>Alcohol: </b> <span>{{sort.alcohol}}</span></li>
    
  </div>
</template>

<script>
export default {
    props: {
        sort:{
            required: true,
        }
    }
}
</script>

<style lang="scss" scoped>
.beer__list{
    padding-top: 20px;
}
li {
    min-width: 20vw;
    max-width: 80vw;
    display: flex;
    justify-content: space-between;
}
</style>