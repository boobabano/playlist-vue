<template>

  <div>
    <!--<add-blog></add-blog>
    <show-blogs></show-blogs>-->
    <app-header></app-header>
    <router-view></router-view>

</div>
</template>

<script>
import addBlog from './components/addBlog.vue'
import showBlogs from './components/showBlogs.vue'
import header from './components/header.vue'
export default {
  components:{
    'add-blog':addBlog,
    'show-blogs':showBlogs,
    'app-header': header
  },
  data(){
    return {

    }
  },
  methods:{

  }
}
</script>

<style>



</style>
