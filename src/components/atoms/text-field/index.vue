<template>
<div class="text-field" :class="addClass">
  <h5>{{ label }}</h5>
  <input
      ref="input"
      type="text"
      v-bind="$attrs"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      @focus="onFocus"
      @blur="onBlur"
  >
</div>
</template>

<script>
import {ref} from "vue";

export default {
  name: "TextField",
  props: {
    modelValue: {
      type: String,
      default: ''
    },
    label: {
      type: String,
      default: ''
    },
  },
  setup() {
    const addClass = ref('')

    const onFocus = () => {
      addClass.value = 'focus'

    }
    const onBlur = (e) => {
      if (!e.target.value) {
        addClass.value = ''
      }
    }

    return { addClass, onFocus,
      onBlur }
  }
}
</script>

<style scoped lang="scss">
.text-field {
  $self: &;
  position: relative;
  //margin-bottom: 20px;
  padding: 5px 0;
  border: 2px solid #E6E6E6;
  border-radius: 7px;
  height: 56px;
  transition: .3s;

  & + #{ $self } {
    margin-top: 20px;
    //margin-bottom: 4px;
  }

  & > h5{
    position: absolute;
    left: 19px;
    top: 50%;
    transform: translateY(-50%);
    transition: .3s;
    display: block;

    font-weight: 500;
    font-size: 15px;
    line-height: 20px;
    color: #9B9B9B;
  }

  //& > div{
  //  position: relative;
  //  height: 45px;
  //
  //}

  //&:before, &:after{
  //  content: '';
  //  position: absolute;
  //  bottom: -2px;
  //  width: 0%;
  //  height: 2px;
  //  background-color: #38d39f;
  //  transition: .4s;
  //}
  //
  //&:before{
  //  right: 50%;
  //}
  //
  //&:after{
  //  left: 50%;
  //}

  &.focus {
    border-color: #7D3AF4;
    //&:before, &:after{
    //  width: 50%;
    //}
    h5 {
      top: 4px;
      left: 14px;
      font-weight: 500;
      font-size: 11.25px;
      line-height: 20px;
      color: #192A3E;
    }
  }

  input {
    border: none;
    outline: none;
    background: transparent;
    display: block;
    width: 100%;
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    padding: 0.5rem 14px;
    font-size: 1.2rem;
    color: #555;
  }
}

</style>