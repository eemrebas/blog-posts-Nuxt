<template>
    <div class="container mt-5 d-flex flex-column justify-content-center align-items-center">
        <blockquote class="blockquote">
            <h2 class="title">Post Detail</h2>
            <h3 class="title"> {{ post.title }} </h3>
            <p class="subtitle"> {{ post.subTitle }} </p>
            <p class="mb-0"> {{ post.text }} </p>
            <footer class="blockquote-footer">Software Engineer <cite title="Source Title"> {{ post.author }} </cite></footer>
        </blockquote>
    </div>
</template>

<script>
export default {
    props : {
        post : {
            type : Object,
            required: true
        }
    }
}
</script>

<style scoped>
.title {
    font-family: 'Special Elite', cursive;
}
.subtitle {
    font-family: 'Special Elite', cursive;
    font-size: 15px;
}
h2 {
    margin-bottom: 1.5rem;
}
</style>