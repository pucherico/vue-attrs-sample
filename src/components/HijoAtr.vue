<template>
  <div>
      {{texto}}
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
    // inheritAttrs: false,
    props: ['mensaje'],
    setup(props) {
        const texto = ref(props.mensaje);
        return { texto };
    }
}
</script>

<style>

</style>