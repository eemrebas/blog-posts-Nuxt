<template>
    <div class="card mr-3 mb-3 card-success" style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-title"> {{ post.title }} </h5>
            <h6 class="card-subtitle mb-2"> {{ post.subTitle }} </h6>
            <p class="card-text"> {{ post.text }} </p>
            <div class="admin-button-container" v-if="isAdmin">
                <a href="#" @click.prevent="$router.push('/admin/' + post.id)" class="btn btn-outline-success btn-sm">Edit</a>
                <a href="#" @click.prevent="deletePost(post.id)" class="btn btn-outline-danger btn-sm">Delete</a>
            </div>
            <a href="#" @click.prevent="$router.push('/post/' + post.id)" class="btn btn-outline-warning btn-sm" v-else>Details</a>
        </div>
    </div>
</template>

<script>
export default {
    props : {
        isAdmin : {
            required : true,
        },
        post : {
            required : true,
            type : Object
        }
    },
    methods : {
        deletePost(postId) {
            this.$store.dispatch("deletePost", postId)
                .then(response => {
                    this.$router.push("/")
                })
        }
    }
}
</script>

<style scoped>
    .card-title {
        font-family: 'Special Elite', cursive;
    }
    .card-subtitle {
        font-family: 'Special Elite', cursive;
        font-size: 15px;
    }
</style>