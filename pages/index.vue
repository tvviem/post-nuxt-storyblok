<template>
  <section class="section">
    <div class="row columns">
      <PostPreview
        v-for="post in posts" :key="post.id"
        :title="post.title"
        :excerpt="post.previewText"
        :thumbnailImage="post.thumbnailUrl"
        :id="post.id" />
    </div>
  </section>
</template>

<script>

import PostPreview from '~/components/Blog/PostPreview.vue'

export default {
  components: {
    PostPreview
  },
  /* data() {
    return {
      posts: [
        {
          title: "A New Beginning",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "http://www.healthyfood.co.uk/wp-content/uploads/2015/01/Cherry-tomato-bocc-olive-basil-pasta.jpg",
          id: "a-new-beginning"
        },
        {
          title: "A Second Beginning",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl:
            "http://www.healthyfood.co.uk/wp-content/uploads/2015/01/Cherry-tomato-bocc-olive-basil-pasta.jpg",
          id: "a-second-beginning"
        }
      ]
    };
  } */
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories', {
      version: 'draft',
      starts_with: 'blog/' // slug name on Storyblog
    }).then(res => {
      return {
        posts: res.data.stories.map(bp => {
          return {
            id: bp.slug,
            title: bp.content.title,
            previewText: bp.content.summary,
            thumbnailUrl: bp.content.thumbnail
          }        
        })
      }; // Return array of posts object 
    })
  }
}
</script>

<style>

</style>
