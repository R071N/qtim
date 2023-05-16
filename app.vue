<template>
  <div id="page">
    <div class="container">
      <TheHeader />
      <div id="content" class="site-content">
        <div id="primary" class="content-area column full">
          <NuxtPage />
        </div>
      </div>
    </div>
    <TheFooter />
    <a href="#top" class="smoothup" title="Back to top"><span class="genericon genericon-collapse"></span></a>
  </div>
</template>

<script>
import TheFooter from '@/components/TheFooter.vue';
import TheHeader from '@/components/TheHeader.vue';

export default {
  components: { TheFooter, TheHeader },
}
</script>

<style>
@import '@/assets/css/woocommerce-layout.css';
@import '@/assets/css/woocommerce-smallscreen.css';
@import '@/assets/css/woocommerce.css';
@import '@/assets/css/font-awesome.min.css';
@import '@/assets/css/style.css';
@import '@/assets/css/easy-responsive-shortcodes.css';
</style>
