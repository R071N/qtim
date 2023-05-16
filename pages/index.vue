<template>
  <main id="main" class="site-main">
    <div class="grid portfoliogrid">
      <article class="hentry" v-for="item in posts" :key="item.id">
        <header class="entry-header">
          <div class="entry-thumbnail">
            <NuxtLink :to="`/posts/${item.id}`">
              <img :src="item.image" class="attachment-post-thumbnail size-post-thumbnail wp-post-image" :alt="item.title"
                onerror="this.src='https://assets.atlanticbt.com/content/uploads/2016/02/404_atlanticbt_blog.jpg';" />
            </NuxtLink>
          </div>
          <h2 class="entry-title">
            <NuxtLink :to="`/posts/${item.id}`" rel="bookmark">
              {{ item.title }}
            </NuxtLink>
          </h2>
          <p class='portfoliotype'>
            {{ item.createdAt }}
          </p>
        </header>
      </article>
    </div>
    <BasePagination v-model:page="page" :count="countProducts" :per-page="productsPerPage" />
    <br />
  </main>
</template>

<script>
import axios from 'axios'
import BasePagination from '@/components/BasePagination.vue'

export default {
  components: { BasePagination },
  data() {
    return {
      postsData: [],

      page: 1,
      productsPerPage: 12,
      countProducts: 0,
    };
  },
  async mounted() {
    try {
      const response = await axios.get(`https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts`);
      this.postsData = response.data;
      this.countProducts = this.postsData.length;
    } catch (error) {
      console.error(error);
    }
  },
  computed: {
    posts() {
      const offset = (this.page - 1) * this.productsPerPage;
      return this.postsData.slice(offset, offset + this.productsPerPage).map(post => {
        return {
          ...post,
          id: encodeURIComponent(post.id)
        }
      });
    },
  },
}

</script>
