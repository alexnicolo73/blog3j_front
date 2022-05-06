<template>
    <div id="blog_post_card">
        <h2 class="category_title">
            {{date}}
        </h2>
        <h1 class="post_title">
            <a href="#">
                {{name}}
            </a>
        </h1>
        <p class="post_content">
            {{content}}
        </p>
        <a href="#">
            <img class="post_image" :src="image" alt="">
        </a>
        </div>
</template>

<script>

export default {
    name: 'PostCard',
    props: {
    name: String,
    content: String,
    image: String,
    date: String
  }
}
</script>

<style lang="scss" scoped>

    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&display=swap');

    #blog_post_card {
        box-shadow: 0px 0px 5px 2px rgba(0,0,0,0.62);
        //width: 30vw;
        //height: auto;
        padding: 2rem;
        border-radius: 0 0 1.5% 1.5%;
        border-top: 1.5px solid #E4EE89;

        .category_title {
            font-size: 0.8rem;
            font-family: Open-Sans;
            text-transform: uppercase;
            color: #E4EE89;
            font-weight: 500;
            letter-spacing: .2rem;
        }
        .post_title {
            font-family: Open-Sans;
            text-transform: capitalize;
            color: white;
            font-weight: 600;
            margin: 1.5rem 0;
            a {
                text-decoration: none;
                color: inherit;
            }
        }
        .post_content {
            color: #A7A7A7;
            margin-bottom: 1.5rem;
            font-family: Open-Sans;
            font-size: 1.2rem;
            overflow: hidden;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
        }
        .post_image {
            // width: 300px;
            // height: 100px;
            object-fit: cover;
            max-width: 100%;
        }
    }

</style>