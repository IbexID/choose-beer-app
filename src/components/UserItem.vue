<template>
  <div class="user__info">
    <p class="user__item"> <b>Имя: </b>
      <span>{{user.first_name}} {{user.last_name}}  </span>
      </p>
    <p class="user__item"> <b>Возраст: </b>
      <span>{{
      Math.floor((new Date() - new Date(user.date_of_birth))/31557600000) || ''
      }} </span>
      </p>
    <p class="user__item"><b> Должность: </b>
      <span>{{user.employment.title}} </span>
      </p>
    <p class="user__img"> 
      <img v-bind:src=avatar alt="avatar not available" /> 
    </p>
    
  </div>
</template>

<script>

export default {
  props: {
    user: {
      required: true,
    },
    avatar: {
      required: true,
    }
  },
};
</script>

<style lang="sass" scoped>
.user__info
  display: flex
  align-items: center
  justify-content: flex-start
  flex-direction: column
.user__item
  color: white
  font-family: Montserrat, sans-serif
  margin-top: 5px
  margin-bottom: 5px
  display: flex
  justify-content: space-between
  min-width: 340px
  max-width: 80vw
  b 
    padding-right: 10px
</style>
