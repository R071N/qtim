<template>
  <main id="main" class="site-main">
    <article class="portfolio hentry">
      <header class="entry-header">
        <div class="entry-thumbnail">
          <img width="800" height="533" :src="postData.image"
            class="attachment-post-thumbnail size-post-thumbnail wp-post-image" :alt="postData.title"
            onerror="this.src='https://assets.atlanticbt.com/content/uploads/2016/02/404_atlanticbt_blog.jpg';" />
        </div>
        <h1 class="entry-title">{{ postData.title }}</h1>
      </header>
      <div class="entry-content">
        <p>{{ postData.preview }}</p>
        <blockquote>
          <p>{{ postData.description }}</p>
        </blockquote>
      </div>
    </article>

    <nav class="navigation post-navigation" role="navigation">
      <div class="nav-links">
        <div class="nav-previous">
          {{ postData.createdAt }}
        </div>
      </div>
    </nav>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      postData: [],
    }
  },
  async mounted() {
    try {
      const id = this.$route.params.id;
      const response = await axios.get(`https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/${id}`);
      this.postData = response.data;
    } catch (error) {
      console.error(error);
    }
  },
}
</script>
