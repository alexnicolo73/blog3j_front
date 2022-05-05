<template>
    <div class="main">
        <PostCard v-for="blog_post in info" :key="blog_post.id" :name="blog_post.name" :content="blog_post.content" :image="blog_post.image"></PostCard>
    </div>
</template>

<script>
import PostCard from "@/components/PostCard.vue";
import axios from 'axios';

export default {
    name: 'Blog_Post_List',

    data () {
        return {
        info: null
        }
    },
    mounted () {
        axios
        .get('')
        .then(response => (this.info = response.data))
    }
} 
</script>

<style>

.main {
    display: flex;
    justify-content: space-between;
}

</style>
