<template>
  <div class="user__info">
    <p class="user__item"> Имя: {{user.first_name}} {{user.last_name}} </p>
    <p class="user__item"> Возраст: {{
      Math.floor((new Date() - new Date(user.date_of_birth))/31557600000) || ''
      }} </p>
    <p class="user__item"> Должность: {{user.employment.title}} </p>
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
.user__item
  color: white
  font-family: Montserrat, sans-serif
  margin-top: 5px
  margin-bottom: 5px
</style>
