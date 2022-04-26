<template>
        <ul class="beer__list">
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
    max-width: 400px
    display: flex
    flex-direction: column
    align-items: center
    margin: 0 auto
</style>