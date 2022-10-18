<template>
  <main>
    <div class="container p-5">
       <router-view></router-view>
    </div>
  </main>
</template>

<script>
import Axios from 'axios';

export default {
    name: 'MyMain',
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