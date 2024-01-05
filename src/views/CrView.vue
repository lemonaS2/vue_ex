<script>

export default {
  data() {
    return {
      awesome: true,
      type: 'A',
      page: true
    }
  }
}
</script>
<template v-if="ok">
  <div class="layout">
    <h1>This is an Conditional page</h1>
    <button @click="awesome = !awesome">전환</button>
    <h1 v-if="awesome">Vue는 정말 멋지죠!</h1>
    <h1 v-else>아닌가요? 😢</h1>
    <hr>
    <div v-if="type === 'A'">
      A
    </div>
    <div v-else-if="type === 'B'">
      B
    </div>
    <div v-else-if="type === 'C'">
      C
    </div>
    <div v-else>
      A/B/C 아님
    </div>
    <hr>
    <button @click="page=!page" :class="{ active:page }">페이지 전환</button>
    <template v-if="page === true">
      <h1>제목1</h1>
      <p>단락 1</p>
      <p>단락 1</p>
      <h1 v-show="true">안녕1</h1>
    </template>
    <template v-else="page === false">
      <h1>제목2</h1>
      <p>단락 2</p>
      <p>단락 2</p>
      <h1 v-show="false">안녕2</h1>
    </template>
    <hr>
  
  </div>
</template>

<style>
  button.active {
    background: #000;
    color: #fff;
  }
</style>

