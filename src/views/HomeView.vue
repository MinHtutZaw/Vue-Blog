<template>
  <div class="home">
    
    <div v-if="posts.length>0">
         <ProjectsList :posts="posts"></ProjectsList>
    </div>
    <div v-else>
      <LoadingSpinner></LoadingSpinner>
    </div>
  </div>
</template>

<script>
import LoadingSpinner from './LoadingSpinner'
import { ref } from '@vue/reactivity'

import getPosts from "../composables/getPosts"
import ProjectsList from '../components/ProjectsList'
export default {
  name: 'HomeView',
  components: {
    LoadingSpinner,
    ProjectsList,      },
  setup(){
      let {posts,error,load}=getPosts()


    load()
    return {  posts,error   };
      

  }

}
</script>

<style >
  .home {
    max-width: 1200px;
    margin: 0 auto;
    padding: 10px;
  }
</style>