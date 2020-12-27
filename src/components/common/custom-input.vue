<template>
  <div>
    <label class="q-mb-sm block text-bold " for="">{{ label }}</label>
    <q-input
      class="rounded-borders q-mb-lg my-input"
      standout="bg-grey-3"
      style="border-radius: 20px"
      hide-underline
      hide-bottom-space
      v-model="text"
      :placeholder="placeholder"
      :type="type"
      dense
    >
      <template v-if="forgotPW" v-slot:append>
        <a href="#" class="text-caption text-amber">Forgot password?</a>
      </template>
    </q-input>
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: "text"
    },
    placeholder: {
      type: String
    },
    label: {
      type: String
    },
    forgotPW: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      text: "",
      something: false
    };
  },
  watch: {
    text(newValue, oldValue) {
      this.$emit("handleInput", this.text);
    }
  }
};
</script>

<style lang="scss">
.my-input {
  .q-placeholder {
    color: $grey-9 !important;

    &::placeholder {
      font-style: italic;
      color: $grey-6;
    }
  }
}
.q-field--standout.q-field--focused .q-field__control {
  box-shadow: none;
}

.q-field--dense .q-field__control,
.q-field--dense .q-field__marginal {
  height: 44px;
}
</style>
