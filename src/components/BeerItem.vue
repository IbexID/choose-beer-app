<template>
  <div class="beer__list">
    <li class="item__list"><strong>Brand: </strong> <span>{{sort.brand}}</span></li>
    <li class="item__list"><strong>Name: </strong> <span>{{sort.name}}</span></li>
    <li class="item__list"><strong>Style: </strong> <span>{{sort.style}}</span></li>
    
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
    min-width: 400px;
    display: flex;
    justify-content: space-between;
    span {
        display: flex;
        justify-content: flex-end;
    }
}
</style>