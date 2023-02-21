<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "PostComponent",
  props:{
      name:{
          type: String,
      },
  },
//   setup() {
//     const name = ref("");
//     return { name };
//   },
  methods: {
    showName() {
      this.$emit('showName');
    },
  },
//   watch:{
//     name(val){
//         if(val){
//             this.showName();
//         }
//     }
//   },
  created() {
    this.showName();
  },
});
</script>

<template>
  <div class="post">
    <div class="post-header">
      <slot name="header"></slot>
    </div>
    <div class="post-content">
      <slot name="content"></slot>
    </div>
    <div class="post-footer">
      <slot name="footer"></slot>
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
</style>
