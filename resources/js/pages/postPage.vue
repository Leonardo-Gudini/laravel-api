<template>
  <div class="container">
    <div v-if="loading" class="d-flex justify-content-center">
            <div class="spinner-border" role="status">
                <span class="sr-only">Loading...</span>
            </div>
        </div>

        <div v-else class="row">
            <div class="card col-12 mb-5" v-for="(post, index) in posts" :key="index">
                <div class="card-body">
                    <h5 class="card-title">{{post.title}}</h5>
                    <p class="card-text">{{post.description}}</p>
                    <p class="card-text">{{post.category?post.category.name:'-'}}</p>
                    <a href="#" class="btn btn-primary">Details</a>
                </div>
            </div>
        </div>
  </div>
</template>

<script>
export default {
    name: "postPage",
    data() {
        return{
            posts: [],
            loading: true
        }
    },
    methods:{
        getPosts() {
            Axios.get('/api/posts')
            .then((response)=>{
                this.posts = response.data.results;
                this.loading = false;
            });
        }
    },
    mounted(){
        this.getPosts();
    }
}
</script>

<style>

</style>