<script setup>
import { useAttrs } from '@vue/runtime-core'

const props = defineProps({
  message: {
    type: String,
    required: true
  }
})

const attrs = useAttrs()

const upperMessage = props.message.toUpperCase()
</script>

<script>
export default {
  inheritAttrs: false,
  props: {
    message: {
      type: String,
      required: true
    },
    initialCount: {
      type: [Number, String],
      default: 10
    }
  }
}
</script>

<template>
  <h1>{{ upperMessage }}</h1>
  <p v-bind="attrs">This is my paragraph!!!</p>
</template>
