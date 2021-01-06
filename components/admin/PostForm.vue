<template>
<div class="container-fluid mt-5 d-flex flex-wrap justify-content-center align-items-center">
    <form style="width: 500px" @submit.prevent="onSubmit">
        <fieldset>
            <legend v-if="isUpdate">Edit Post</legend>
            <legend v-else>New Post</legend>
            <div class="form-group">
                <label>Author Name</label>
                <input v-model="post.author" type="text" class="form-control" placeholder="Name of the author...">
            </div>
            <div class="form-group">
                <label>Title</label>
                <input v-model="post.title" type="text" class="form-control" placeholder="Title of the post...">
            </div>
            <div class="form-group">
                <label>Subtitle</label>
                <input v-model="post.subTitle" type="text" class="form-control" placeholder="Subtitle of the post...">
            </div>
            <div class="form-group">
                <label>Blog Post</label>
                <textarea v-model="post.text" class="form-control" rows="5"></textarea>
            </div>
            <button class="btn btn-danger" @click="$router.push('/admin')">Cancel</button>
            <button type="submit" class="btn btn-success">Save</button>
        </fieldset>
    </form>
</div>
</template>

<script>
export default {
    data(){
        return {
            post : {
                title : null,
                subTitle : null,
                author : null,
                text : null
            }
        }
    },
    props : {
        isUpdate : {
            type : Boolean,
            required : false,
            default : false
        },
        post : {
            type : Object,
            required : false
        }
    },
    methods : {
        onSubmit(){
            this.$emit("submit", this.post)
        }
    },
    created() {
        this.post = this.post ? this.post : {
            id : null,
            title : null,
            subTitle : null,
            text : null,
            author : null
        }
    }
}
</script>