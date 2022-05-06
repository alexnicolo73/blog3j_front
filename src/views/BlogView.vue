<template>
    <div class="main">
        <PostCard v-for="blog_post in info" 
            :key="blog_post.id" 
            :name="blog_post.title" 
            :content="blog_post.contenu" 
            :date="blog_post.created_at" 
            :image="blog_post.img">
        </PostCard>
    </div>
</template>

<script>
import PostCard from "@/components/PostCard.vue";
import axios from 'axios';

export default {
    name: 'Blog_Post_List',

    components : {
        PostCard
        },
    data () {
        return {
        info: null
        }
    },
    mounted () {
        axios
        .get('https://site3j2.herokuapp.com/api/getblogarticle')
        .then(response =>{ 
            this.info = response.data.blog_post;
        })
    }
} 
</script>

<style>

.main {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    grid-gap: 20px;
    align-items: normal;
}

</style>
