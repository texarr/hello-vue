<template>
  <div>
    <ul>
      <li v-for="comment in comments" class="comment" :key="comment.id">
        <h5>{{ comment.name }}</h5>
        <h6>{{ comment.text }}</h6>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

interface Comment {
  id: number;
  name: string;
  text: string;
}

@Component
export default class Comments extends Vue {
  private comments: Comment[] = [
    {
      id: 12345,
      name: 'Roman',
      text: 'Vue jest spoko',
    },
    {
      id: 12346,
      name: 'Daniel',
      text: 'Kasia jest spoko',
    },
    {
      id: 12347,
      name: 'Kasia',
      text: 'Daniel jest spoko',
    },
    {
      id: 12348,
      name: 'Zosia',
      text: 'Wszyscy są spoko',
    },
  ];
}
</script>
<style scoped lang="scss">
  .comment {
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