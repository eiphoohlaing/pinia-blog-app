<template>
  <div class="container">
    <div class="row">
      <h1>Pinia</h1>
      <div class="d-flex align-items-center justify-content-center my-3">
        <img src="https://pinia.vuejs.org/logo.svg" alt="" style="width:40px;">
        <h4 class="text-warning text-center">Pinia Blog</h4>
      </div>
      <div class="col-md-6 offset-md-3">
        <BlogCreate/>
        <BlogItem v-for="blog in blogs" :key="blog.id" :blog="blog"/>
      </div>
    </div>
  </div>
</template>

<script>
import { storeToRefs } from 'pinia'
import { useBlogStore } from './stores/BlogStore'
import BlogCreate from './components/BlogCreate.vue'
import BlogItem from './components/BlogItem.vue'

export default {
  components:{BlogCreate,BlogItem},
  setup(){
    const blogStore = useBlogStore()
    const {blogs} =storeToRefs(blogStore)
    return {blogs}
  }

}
</script>

