<template>
  <q-page class="flex flex-center">
    <div class="fit row  justify-center items-start ">
      <login-card />
    </div>
  </q-page>
</template>

<script>
import LoginCard from "src/components/login/login-card.vue";

export default {
  components: {
    LoginCard
  }
};
</script>

<style lang="scss"></style>
