<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  },
  msg2: {
    type: String,
    required: true
  }
})
const rawHtml = '<a href="">Link</a>';
const pid = 10;
const isButtonDisabled = true;
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper'
}
const number = 1;
const ok = 1;
const message = 'Hello World';
const id = 'itemList'
const sayHello = (msg) => {
  alert(msg);
}
const url = 'http://www.google.com';
const attributeName = 'href';

const items = [
  {id:0, title:'html'},
  {id:1, title:'css'},
  {id:2, title:'javascript'}
]

const onSubmit = () => {
  alert('제출되었습니다.');
}

</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}{{ msg2 }}</h1>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
    <hr>
    <p>{{ rawHtml }}</p>
    <p><span v-html="rawHtml"></span></p>
    <hr>
    <h2>속성 바인딩</h2>
    <div v-bind:id="pid"></div>
    <div :id="pid"></div>
    <h2>불리언 바인딩</h2>
    <button :disabled="isButtonDisabled2">버튼1</button>
    <button :disabled="!isButtonDisabled2">버튼2</button>
    <h2>여러속성 바인딩</h2>
    <div v-bind="objectOfAttrs"></div>
    <h2>자바스크립트 표현식</h2>
    {{ number + 1 }}
    {{ ok === 1 ? '예' : '아니오' }}
    {{ message.split('').reverse().join('') }}
    <div :id="`list-${id}`"></div>
    <h2>함수 호출</h2>
    <!-- <span :title="sayHello('안녕')"></span>
    <div>{{ sayHello(date) }}</div> -->
    <h2>디렉티브</h2>
    <a :href="url">구글</a>
    <a :[attributeName]="url"> ... </a>
  </div>

  <div v-for="item in items" :key="item.id">
    {{ item.title }}
  </div>
  
  <h2>v-on</h2>
  <div>
    <button type="button" v-on:click="sayHello('방가1')">방가1</button>
    <button type="button" @click="sayHello('방가2')">방가2</button>
    <button type="button" @mouseover="sayHello('방가3')">방가3</button>
  </div>

  <form action="" @submit.prevent="onSubmit">
    <button>제출</button>
  </form>

</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
