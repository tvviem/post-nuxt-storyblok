<template>
  <section class="section">
    <div class="container">
      <h1 class="title is-size-3">{{ title }}</h1>
      <p class="is-size-4"> {{ content }} </p>
      <figure class="image is-256x256">
        <img :src="image" alt="Image">
      </figure>
    </div>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return context.app.$storyapi
      .get("cdn/stories/blog/" + context.params.postId, {
        version: 'draft'
      }).then(res => {
        return {
          image: res.data.story.content.thumbnail,
          title: res.data.story.content.title,
          content: res.data.story.content.content
        }
      })
  }
}
</script>

<style>

</style>
