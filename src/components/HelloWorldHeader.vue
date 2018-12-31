<template>
  <div>
    <h1>{{msg}}</h1>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorldHeader extends Vue {
  private msg: string = 'HelloWorld Header Component';
}
</script>
<style scoped lang="scss">

</style>