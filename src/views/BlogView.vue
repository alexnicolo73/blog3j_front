<template>
    <div class="main">

        <PostCard v-for="blog_post in info" :key="blog_post.id" :name="blog_post.title" :content="blog_post.contenu" :image="blog_post.img"></PostCard>

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
        .get('http://127.0.0.1:8000/api/getblogarticle')
        .then(response =>{ 
            this.info = response.data.blog_post;
            console.log(this.info[0].img)
           
            })


    }
} 
</script>

<style>

.main {
    display: flex;
    justify-content: space-between;
}

</style>
