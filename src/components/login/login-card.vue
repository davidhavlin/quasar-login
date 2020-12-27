<template>
  <q-card class="col-xs-12 col-sm-6 col-lg-4 text-grey-9 q-pa-xl custom-card">
    <q-card-section>
      <div class="text-h3 text-center q-mb-lg text-bold">
        Login
      </div>
    </q-card-section>

    <q-card-section class="q-pa-sm">
      <!-- --------- EMAIL INPUT ----------- -->
      <custom-input
        label="E-mail adress: *"
        placeholder="Your email adress (..@..)"
        type="email"
        @handleInput="email = $event"
      />

      <!-- --------- PASSWORD INPUT ----------- -->
      <custom-input
        label="Password: *"
        placeholder="* * * * * * * *"
        type="password"
        :forgotPW="true"
        @handleInput="password = $event"
      />
      <!-- --------- CHECKBOX  ----------- -->
      <custom-checkbox label="Stay signed in" @check="staySigned = $event" />
    </q-card-section>

    <!-- --------- SIGN IN BUTTON  ----------- -->
    <q-card-actions align="stretch">
      <custom-button
        color="amber"
        text="Sign In"
        class="fit"
        @click.native="clickTest()"
      />
    </q-card-actions>

    <q-card-section>
      <div class="text-weight-bold text-center">
        Don`t have an account yet?
        <a class="text-grey-10" href="#">Register</a>.
      </div>
    </q-card-section>

    <q-card-actions align="stretch" class="row justify-between items-stretch ">
      <!-- --------- SIGN IN FACEBOOK BUTTON  ----------- -->
      <custom-button
        color="blue-10"
        text="Sign in with Facebook"
        class="col "
      />
      <!-- --------- SIGN IN GOOGLE BUTTON  ----------- -->
      <custom-button color="red-9" text="Sign in with Google" class="col" />
    </q-card-actions>
  </q-card>
</template>

<script>
import CustomButton from "src/components/common/custom-button.vue";
import CustomInput from "src/components/common/custom-input.vue";
import CustomCheckbox from "src/components/common/custom-checkbox.vue";

export default {
  components: {
    CustomButton,
    CustomInput,
    CustomCheckbox
  },
  data() {
    return {
      email: "",
      password: "",
      staySigned: false
    };
  },
  methods: {
    clickTest() {
      //
    }
  }
};
</script>

<style lang="scss">
.custom-card {
  max-width: 600px;
  border-radius: 20px;
  box-shadow: 11px 4px 20px 4px #0000000d;
}
.q-card__actions--horiz > .q-btn-item + .q-btn-item,
.q-card__actions--horiz > .q-btn-group + .q-btn-item,
.q-card__actions--horiz > .q-btn-item + .q-btn-group {
  margin-left: 16px;
}

// check-box
.q-checkbox__bg {
  border: 1px solid $grey-4;
  background: $grey-3;
}

.q-checkbox__inner--truthy .q-checkbox__bg {
  border: 1px solid currentColor;
}

@media (max-width: $breakpoint-xs-max) {
  .custom-card {
    padding: 0.5rem;
  }
}
@media (max-width: $breakpoint-sm-max) {
  .custom-card {
    padding: 1rem;
  }
}
</style>
