<template>
  <div class="hello">
    <HelloWorldHeader/>
    <h1 :style='data'>{{ msg }}</h1>
    <button @click="handleClick">Change color</button><br/>
    <label for="color">Change color by hex, color name or another pattern</label>
    <input name="color" id="color" v-model="data.color"/>
    <div>
      <h3>Comments:</h3>
      <Comments />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import HelloWorldHeader from './HelloWorldHeader.vue';
import Comments from './Comments.vue';

interface Data {
  color: string;
}

@Component( {
  components: {
    HelloWorldHeader,
    Comments,
  },
})
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
h1 {
  color: green;
}
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
