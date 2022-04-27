<template>
        <ul class="beer__list">
            <p> Ваше пиво: </p>
            <BeerItem
            v-bind:user="user"
            v-for="item of beers"
            v-bind:sort="item" :key="item"
            />
        </ul>
</template>

<script>
import BeerItem from "@/components/BeerItem";
export default {
    props: ['beers', 'user'],
  components: {
    BeerItem,
  },
};
</script>

<style lang="sass" scoped>
.beer__list
    color: white
    list-style: none
    min-width: 80vw
    padding: 0
    display: flex
    flex-direction: column
    align-items: center
    margin: 20px auto
</style>