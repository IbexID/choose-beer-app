<template>
  <div id='app' class="beer__chooser">
    <UserItem 
    v-bind:user="user"
    v-bind:avatar="avatar"
    />
    <ChooseBeer
    @click="getNewBeer"
     />
    <BeerChoice 
    v-bind:beers="beers"
     />
  </div>
</template>

<script>
import BeerChoice from '@/components/BeerChoice.vue'
import UserItem from '@/components/UserItem'
import ChooseBeer from './components/UI/button/ChooseBeer.vue'

export default {
  name: 'App',
  data() {
    return {
      beers: [
        {brand:"",name:"",style:""},
      ],
      user: 
        {employment:{
          title: ''
        }},
      
      avatar: [
        ''
      ]
    }
  },
  methods: {
    getNewBeer(){
      fetch('https://random-data-api.com/api/beer/random_beer')
      .then(curBeer => curBeer.json())
      .then( beerJson => 
        this.beers = [beerJson])
  }
  },
  mounted () {
    fetch('https://random-data-api.com/api/beer/random_beer')
      .then(curBeer => curBeer.json())
      .then( beerJson => {
        this.beers = [beerJson]
    fetch('https://random-data-api.com/api/users/random_user', {
      mode: 'cors'
    })
        .then(user => user.json())
        .then( userJson => {
        this.user = Object.assign({}, userJson)
        this.avatar = userJson['avatar']
      })
      })},
  components: {
    BeerChoice,
    UserItem,
    ChooseBeer,
  }
}
</script>

<style lang="scss">
body{
  font-family: Montserrat, sans-serif;
  background: #3c6792;
  color: white
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
.beer__chooser{
  display: block;
}
</style>
