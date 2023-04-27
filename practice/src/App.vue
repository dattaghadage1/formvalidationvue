<template>
  <div id="app" class="h-100">
    <div class="container-fluid h-100">
      <div class="row h-100">
        <div class="vue-bg col-md-3 h-100 d-flex justify-content-center align-items-center">
          <img class="w-50" src="./assets/vue.svg" alt="vue-logo" width="100">
        </div>
        <div class="col-md-9 h-100  d-flex justify-content-center align-items-center">
          <div class="col-md-8 shadow rounded py-4 px-5 bg-white">
            <UserFormValidation />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import UserFormValidation from './components/userFormValidation.vue';
export default {
  name: "App",
  components: {
    UserFormValidation
  }
}
</script>
<style>
#app {
  height: 100%;
}

.vue-bg {
  background-color: rgb(186, 224, 212);
}
</style>