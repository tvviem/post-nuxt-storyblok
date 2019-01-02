<template>
  <section class="section">
    <div class="container">
      <h1 class="title is-3">{{ title }}</h1>
      <p class="subtitle">{{ content }}</p>
    </div>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return context.app.$storyapi.get('cdn/stories/about', {
      version: 'draft'
    }).then(res => {
      return {
        title: res.data.story.content.title,
        content: res.data.story.content.content
      }
    })
  }
}
</script>
