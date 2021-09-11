<template>
  <div>
    <p>메인 페이지입니다</p>
    <ProductList />
  </div>
</template>

<script>
import ProductList from '~/components/ProductList.vue';

export default {
  components: { ProductList },
};
</script>

<style lang="scss" scoped>
</style>