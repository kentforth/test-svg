<template>
  <component
    :is="dynamicIcon"
    :width="width"
    :height="height"
    class="svg-icon"
    v-on="$listeners"
  />
</template>

<script>
export default {
  name: 'SvgIcon',
  props: {
    name: {
      type: String,
      required: true,
    },
    // eslint-disable-next-line vue/require-default-prop
    width: [Number, String],
    // eslint-disable-next-line vue/require-default-prop
    height: [Number, String],
  },
  computed: {
    dynamicIcon() {
      return require(`~/assets/icons/${this.name}.svg`).default
    },
  },
}
</script>

