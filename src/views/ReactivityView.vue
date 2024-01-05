<script setup>
  import { ref, nextTick, reactive } from 'vue'

  const count = ref(0)
  console.log(count);

  const state = reactive({ count2: 0 })
  console.log(state);

  const increment = async () =>{
    count.value++
    console.log(document.getElementById('counter').textContent);
    await nextTick()  // 업데이트 완료된 후
    console.log(document.getElementById('counter').textContent);
  }

</script>

<template>
  {{ console.log('template 실행') }}
  <div class="layout">
    <h1>This is an Reactivity page</h1>
    <!-- <button @click="count++">증가</button> -->
    <button @click="increment">증가</button>
    <div id="counter">{{ count }}</div>
    <hr>
    <button @click="state.count2++">count2 증가</button>
    <div>{{ state.count2 }}</div>
  </div>    
</template>

<style>
@media (min-width: 1024px) {
  .layout {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
