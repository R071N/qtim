<template>
  <div>
    <nav class="woocommerce-pagination">
      <ul class="page-numbers ul-style">
        <li>
          <button class="page-numbers btn" @click.prevent="paginate(page - 1)" aria-label="Предыдущая страница"
            :disabled="page === 1">
            Пред
          </button>
        </li>
        <li v-for="pageNumber in pages" :key="pageNumber.id">
          <a href="#" class="page-numbers" :class="{ 'current': pageNumber === page }"
            @click.prevent="paginate(pageNumber)">
            {{ pageNumber }}
          </a>
        </li>
        <li>
          <button class="page-numbers btn" @click.prevent="paginate(page + 1)" aria-label="Следующая страница"
            :disabled="page === pages">
            След
          </button>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  props: ['page', 'count', 'perPage'],
  computed: {
    pages() {
      return Math.ceil(this.count / this.perPage);
    },
  },
  methods: {
    paginate(page) {
      this.$emit('update:page', page);
    },
  },
};
</script>

<style>
.ul-style {
  display: flex;
  justify-content: center;
  gap: 10px;
  list-style: none;
}

.ul-style li {
  padding: 0 10px;
  background-color: rgb(172, 172, 255);
  border-radius: 5px;
}

.btn {
  border: none;
  background: none;
}
</style>
