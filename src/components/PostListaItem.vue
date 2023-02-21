<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "PostListaItem",
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
});
</script>
<template>
  <div class="post">
    <slot>
      <div class="post-header">
        <h2>{{ post.titulo }}</h2>
      </div>
      <div class="post-content">
        <p>{{ post.conteudo }}</p>
      </div>
      <div class="post-footer">
        <small>{{ post.autor }}</small>

        <a href="#">Ler mais...</a>
      </div>
    </slot>
  </div>
</template>
<style scoped>
.post {
  margin: 15px auto !important;
}

.post-header {
  padding: 5px 12px !important;
  background: #eee !important;
}
.post-content {
  font-size: 16px !important;
}
.post-footer {
  font-style: italic !important;
}
</style>
