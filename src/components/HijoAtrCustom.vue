<template>
  <div :style="{backgroundColor: $attrs.color}">
      {{texto}}
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
    inheritAttrs: false,
    props: ['mensaje'],
    setup(props) {
        const texto = ref(props.mensaje);
        return { texto };
    }
}
</script>

<style>

</style>