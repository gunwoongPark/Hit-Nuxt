<template>
  <div>
    <header>
      <h1>{{ $route.name }}페이지</h1>
    </header>
    <NuxtLink to="/">홈 페이지</NuxtLink>
    <NuxtLink to="/main">메인 페이지</NuxtLink>
    <NuxtLink to="/product">상품 페이지</NuxtLink>
    <Nuxt />
  </div>
</template>
