<script lang="ts">
import { defineComponent } from 'vue';
import PostListaItem from './PostListaItem.vue';
export default defineComponent({
    name: "PostLista",
    components: { PostListaItem },
    props:{
        posts: {
            type: Array,
            required: true,
        },
    },
});
</script>
<template>
    <div>
        <h1>Lista de posts</h1>
        <PostListaItem
            v-for="post in posts"
            :key="post.id"
            :post="post">
                <slot :meuPost="post"></slot>
        </PostListaItem>
    </div>
</template>