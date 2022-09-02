<template>
  <div class="navbar bg-base-100">
    <div class="navbar-start">
      <div class="dropdown">
        <label tabindex="0" class="btn btn-ghost lg:hidden">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h8m-8 6h16"
            />
          </svg>
        </label>
        <ul
          tabindex="0"
          class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-base-100 rounded-box w-52"
        >
          <li><NuxtLink to="/discover">Notre histoire</NuxtLink></li>
          <li><NuxtLink to="/contact">Contactez-nous</NuxtLink></li>
          <li><NuxtLink to="/category">Catégories</NuxtLink></li>
          <!-- <li><NuxtLink to="/product">Produit (TODO)</NuxtLink></li> -->
        </ul>
      </div>
      <NuxtLink to="/" class="btn btn-ghost normal-case text-xl"
        >AtypikHouse</NuxtLink
      >
      <div class="navbar-center hidden lg:flex">
        <ul class="menu menu-horizontal p-0">
          <li><NuxtLink to="/discover">Notre histoire</NuxtLink></li>
          <li><NuxtLink to="/contact">Contactez-nous</NuxtLink></li>
          <li><NuxtLink to="/category">Catégories</NuxtLink></li>
          <!-- <li><NuxtLink to="/product">Produit (TODO)</NuxtLink></li> -->
        </ul>
      </div>
    </div>

    <div class="navbar-end">
      <NuxtLink
        to="/account"
        tabindex="0"
        class="btn btn-ghost btn-circle avatar"
      >
        <div class="w-10 rounded-full">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
            <!--! Font Awesome Pro 6.2.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. -->
            <path
              d="M272 304h-96C78.8 304 0 382.8 0 480c0 17.67 14.33 32 32 32h384c17.67 0 32-14.33 32-32C448 382.8 369.2 304 272 304zM48.99 464C56.89 400.9 110.8 352 176 352h96c65.16 0 119.1 48.95 127 112H48.99zM224 256c70.69 0 128-57.31 128-128c0-70.69-57.31-128-128-128S96 57.31 96 128C96 198.7 153.3 256 224 256zM224 48c44.11 0 80 35.89 80 80c0 44.11-35.89 80-80 80S144 172.1 144 128C144 83.89 179.9 48 224 48z"
            />
          </svg>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'HeaderComponent',
})
</script>
