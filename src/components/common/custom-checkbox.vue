<template>
  <q-checkbox
    dense
    v-model="check"
    :label="label"
    color="amber"
    class="text-bold"
  />
</template>

<script>
export default {
  props: {
    label: {
      type: String
    }
  },
  data() {
    return {
      check: false
    };
  },
  watch: {
    check(newValue, oldValue) {
      this.$emit("check", this.check);
    }
  }
};
</script>

<style lang="scss" scoped></style>
