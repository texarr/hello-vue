<template>
  <div>
    <ul>
      <li v-for="comment in comments">
        <h5>{{ comment.name }}</h5>
        <h6>{{ comment.text }}</h6>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

interface Comment {
  name: string;
  text: string;
}

@Component
export default class Comments extends Vue {
  private comments: Comment[] = [
    {
      name: 'Roman',
      text: 'Vue jest spoko',
    },
    {
      name: 'Daniel',
      text: 'Kasia jest spoko',
    },
    {
      name: 'Kasia',
      text: 'Daniel jest spoko',
    },
    {
      name: 'Zosia',
      text: 'Wszyscy są spoko',
    },
  ];
}
</script>
<style scoped lang="scss">
  li {
    list-style: none;
    padding: 10px;
    background: azure;
    text-align: left;
    margin-bottom: 10px;
  }
  h5, h6 {
    margin: 0;
  }
</style>