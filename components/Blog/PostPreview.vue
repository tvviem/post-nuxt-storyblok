<template>
    <div class="column">
      <div class="card large">
        <div class="card-image">
          <figure class="image">
            <img :src="thumbnailImage" alt="Image">
          </figure>
        </div>
        <div class="card-content">
          <div class="media">
            <div class="media-left">
              <figure class="image is-96x96">
                <img :src="thumbnailImage" alt="Image">
              </figure>
            </div>
            <div class="media-content">
              <nuxt-link :to="id"> <p class="title is-4 no-padding">{{title}}</p> </nuxt-link>
              <p><span class="title is-6"><a href="http://twitter.com/#">@twitterid</a></span></p>
            </div>
          </div>
          <div class="content">
            {{excerpt}}
            <div class="background-icon"><span class="icon-twitter"></span></div>
          </div>
        </div>
      </div>
    </div>
  
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    excerpt: {
      type: String,
      required: true
    },
    thumbnailImage: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    }
  }
};
</script>