<template>
  <div class="hello">
    <h1 :style='data'>{{ msg }}</h1>
    <button @click="handleClick">Change color</button><br/>
    <label for="color">Change color by hex</label>
    <input name="color" id="color"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

interface Data {
  color: string;
}

@Component
export default class HelloWorld extends Vue {
  @Prop() public msg!: string;
  public data: Data = {
    color: '#fab',
  };

  private handleClick() {
    if (this.data.color !== '#baf') {
      this.data.color = '#baf';
    } else {
      this.data.color = '#afb';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
