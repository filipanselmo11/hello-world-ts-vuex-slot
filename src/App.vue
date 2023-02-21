
<script lang="ts">
import { defineComponent, ref } from 'vue';
// import PostComponent from './components/PostComponent.vue';
import OtherPostComponent from './components/OtherPostComponent.vue';
export default defineComponent({
  name: 'App',
  components: {
    OtherPostComponent,
  },
  setup(){
      const autor = ref('Fílip Anselmo')
      return{ autor}
    }
});
</script>

<template>
  <h1>Vue Components</h1>
  <OtherPostComponent>
    <template v-slot:content>
      <!-- É possível aplicar estilos no slot do componente filho dentro do escopo do componente pai  -->
      <p class="post-p">Slot default</p>
    </template>
    <!-- Os slots do componente filho vão possuir acesso aos mesmos slots do componente pai -->
    <template v-slot:footer>
      <small> por {{ autor }}</small>
    </template>
    <template v-slot:button>
      Detalhes
    </template>
  </OtherPostComponent>
  <!-- <h1>Vue Components</h1>
  <PostComponent :name="name" @showName="showName">
    <template v-slot:header>
      <h1>Post Component</h1>
    </template>
    <template v-slot:content>
      <input @change="showName" v-model="name" type="text"/>
      <p>Este é um post component</p>
      <span>...</span>
    </template>
    <template v-slot:footer>
      <small>por Fílip Anselmo</small>
    </template>
  </PostComponent> -->
</template>

<style>

.post-p {
  color: red !important;
}
</style>
