<template>

  <div id="show-blogs">
    <h1>All Blogs Articles</h1>
    <input type="text" v-model="search" placeholder="searchBlogs">
    <div v-for="blog in filteredBlogs" class="single-blog">
      <router-link v-bind:to="'/blog/' + blog.id"><h2>{{ blog.title|to-uppercase }}</h2></router-link>
      <article>{{ blog.body|snippet }}</article>
    </div>
  </div>
</template>


<script>

export default {
  components:{

  },
  data(){
    return {
      blogs:[],
      search:''
    }
  },
  methods:{

  },
  created(){
    this.$http.get('https://jsonplaceholder.typicode.com/posts/').then(function(data){
      this.blogs=data.body.slice(0,10);
    })
  },
  computed:{
    filteredBlogs:function(){
      return this.blogs.filter((blog) => {
        return blog.title.match(this.search);
      });
    }
  }
}
</script>

<style>

#show-blogs{
  margin: 0 auto;
  max-width:800px;
}

.single-blog{
  padding:20px;
  margin: 20px 0;
  box-sizing: border-box;
  background: #eee;
}


</style>
