<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
export default {
  middleware: 'log',
    computed: {
        loadedPosts() {
            return this.$store.getters.loadedPosts
        }
    }
    // asyncData(context) {
    //     return new Promise((resolve, reject) => {
    //         setTimeout(() => {
    //         resolve({
    //             loadedPosts: [
    //                 { id:'1', title: 'First Post', previewText: 'This is our first post!', thumbnail: 'https://www.globalfocusmagazine.com/wp-content/uploads/2020/02/Engaging_with_technology-scaled.jpg' },
    //                 { id:'2', title: 'Second Post', previewText: 'This is our second post!', thumbnail: 'https://www.globalfocusmagazine.com/wp-content/uploads/2020/02/Engaging_with_technology-scaled.jpg' } 
    //             ]
    //         })
    //     } ,1000)
    //     // reject(new Error())
    //     })
    //     .then(data => {
    //         return data
    //     })
    //     .catch(e => {
    //         context.error(e);
    //     })
    // },
    // created() {
    //     this.$store.dispatch('setPosts', this.loadedPosts)
    //     // console.log(this.$store.getters.loadedPosts)
    // }
}
</script>

<style scoped>
.posts-page {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>