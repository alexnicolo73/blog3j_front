<template>
    <div class="main">
        <PostCard v-for="blog_post in info" 
            :key="blog_post.id" 
            :name="blog_post.title" 
            :content="blog_post.content" 
            :date="blog_post.publishedAt" 
            :image="blog_post.urlToImage">
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
        .get('https://newsapi.org/v2/everything?q=Apple&from=2022-05-05&sortBy=popularity&apiKey=326fa9ca5fb84f74b095c0b8de423cf5')
        .then(response =>{ 
            this.info = response.data.articles;
            console.log(this.info)
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
