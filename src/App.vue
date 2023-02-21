
<script lang="ts">
import { defineComponent } from 'vue';
import PostLista from './components/PostLista.vue';
export default defineComponent({
  name: 'App',
  components: {
    PostLista,
  },
  setup(){
      const posts = [
        {
          id: 1,
          titulo: 'Components no Vue',
          conteudo: 'Componentes são uma das peaças importantes'
        },
        {
          id: 2,
          titulo: 'Distribuindo conteudo com slots',
          conteudo: 'Slots podem ser usados como repositórios de conteudo ?'
        },
      ];
      return{ posts}
    }
});
</script>

<template>
  <h1>Vue Components</h1>
  <h2>Forma Padrão</h2>
  <PostLista :posts="posts"/>
  <h2>Slot com escopo</h2>
  <PostLista :posts="posts">
    <template v-slot="slotProps">
      <h2>{{ slotProps.meuPost.titulo }}</h2>
      <p>{{ slotProps.meuPost.conteudo }}</p>
      <small>{{ slotProps.meuPost.autor }}</small>
    </template>
  </PostLista>
</template>

<style>

.post-p {
  color: red !important;
}
</style>
