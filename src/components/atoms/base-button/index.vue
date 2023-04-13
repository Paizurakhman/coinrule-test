<template>
  <component
      class="base-button"
      :class="[variant, size]"
      :is="component"
      :href="href"
      v-bind="$attrs"
  >
    <span class="base-button__prepend" v-if="prependIcon"><icon :name="prependIcon" /></span>
    <span class="base-button__content"><slot>Submit</slot></span>
    <span class="base-button__append" v-if="appendIcon"><icon :name="appendIcon" /></span>
  </component>
</template>

<script>
import {computed} from "vue";
import Icon from "@/components/atoms/icon/index.vue";

export default {
  name: "BaseButton",
  components: {Icon},
  props: {
    href: {
      type: String,
      default: ''
    },
    tag: {
      type: String,
      default: ''
    },
    size: {
      type: String,
      default: 'md',
      validator(value) {
        return ['sm', 'md', 'lg', 'xl'].includes(value)
      }
    },
    variant: {
      type: String,
      default: 'default',
      validator(value) {
        return ['default', 'primary', 'secondary', 'outlined', 'danger', "outlined_gray"].includes(value)
      }
    },
    prependIcon: {
      type: String,
      default: ''
    },
    appendIcon: {
      type: String,
      default: ''
    }
  },
  setup(props) {
    const component = computed(() => {
      if (props.tag) return props.tag
      return props.href ? 'a': 'button'
    })
    return { component }
  }
}
</script>

<style scoped lang="scss" src="./index.scss">

</style>
