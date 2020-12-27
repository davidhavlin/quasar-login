<template>
  <q-btn
    :color="color"
    :text-color="textColor"
    :label="text"
    unelevated
    no-caps
    class="q-pa-xs"
  />
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: "Primary"
    },
    text: {
      type: String,
      default: "Button"
    },
    textColor: {
      type: String,
      default: "white"
    }
  }
};
</script>

<style lang="scss" scoped></style>
