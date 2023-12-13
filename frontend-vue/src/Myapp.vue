<template>
    <div>
      <button @click="toggleComponent">Toggle Components</button>
      <!-- 使用动态组件来渲染不同的子组件 -->
      <component :is="currentComponent"></component>
      <button @click="increment">cnt: {{ cnt }}</button>
    </div>
  </template>
  
  <script>
  import { markRaw } from 'vue';
  import ComponentA from './components/ComponentA.vue';
  import ComponentB from './components/ComponentB.vue';
  
  export default {
    data() {
      return {
        // 设置初始渲染的组件为 ComponentA
        currentComponent: markRaw(ComponentA),
        cnt:0
      };
    },
    methods: {
      toggleComponent() {
        // 切换当前渲染的组件
        this.currentComponent = (this.currentComponent === ComponentA ? ComponentB : ComponentA);
      },
      increment(){
        this.cnt++;
      }
    },
    components: {
      ComponentA,
      ComponentB
    }
  };
  </script>
  