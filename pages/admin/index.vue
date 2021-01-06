<template>
    <div>
        <div class="container d-flex justify-content-center align-items-center">
            <h1 class="title">Admin Panel</h1>
            <button class="btn btn-dark" @click="$router.push('/admin/new-post')">Add New Post</button>
        </div>
        <PostList 
            :posts="posts"
            :is-admin="true"
        />
    </div>
</template>

<script>
import PostList from "@/components/post/PostList"
export default {
    layout: "admin",
    components : {
        PostList
    },
    computed : {
        posts() {
            return this.$store.getters.getPosts
        }
    }
}
</script>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
}
</style>