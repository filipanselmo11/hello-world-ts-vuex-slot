<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'OtherPostComponent',
    // setup(){
    //   const autor = ref('Fílip Anselmo')
    //   return{ autor}
    // }
});
</script>

<template>
  <div class="post">
    <div class="post-header">
      <slot name="header"></slot>
    </div>
    <div class="post-content">
      <!-- Slot nomeado -->
      <slot name="content"></slot>
      <!-- Slot default -->
      <!-- <slot></slot> -->
    </div>
    <div class="post-footer">
      <!-- Slot Nomeado -->
      <slot name="footer"></slot>
      <!-- Slot Default -->
      <a href="#">
        <slot name="button">Ler Mais</slot>
      </a>
    </div>
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

/* Aqui não funfou .post-p {
  color: green !important;
} */

a {
  float: right !important;
}
</style>