<template>
  <nav
    class="bg-cyan-500 header w-full flex flex-row justify-evenly items-center py-4 fixed top-0 left-0 z-50"
  >
    <img class="h-16 w-16" src="/favicon.ico" alt="notcapableofcan icon" />
    <ul class="center-row space-x-4">
      <li v-for="item in navList" :key="item.ID">
        <a :href="item.link" :id="item.id" class="text-black">{{
          item.name
        }}</a>
      </li>
    </ul>
    <a href="https://github.com/Erebus-Software/"
      ><img
        class="h-12 w-12"
        src="/icons/github.png"
        alt="notcapableofcan icon"
    /></a>
  </nav>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      navList: [
        {
          id: 'nav-home',
          name: 'Home',
          link: '/',
        },
        {
          id: 'nav-about',
          name: 'About',
          link: '#about',
        },
        {
          id: 'nav-products',
          name: 'Products',
          link: '#products',
        },
        {
          id: 'nav-contact',
          name: 'Contact',
          link: '#contact',
        },
      ],
    }
  },
}
</script>

<style lang="postcss" scoped></style>
