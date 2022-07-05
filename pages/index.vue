<template>
  <div class="center-col pt-24">
    <section id="home" class="container-lg bg-red-400 h-screen"></section>
    <section id="about" class="container-lg bg-green-400 h-screen"></section>
    <section id="products" class="container-lg bg-blue-400 h-screen"></section>
    <section id="contact" class="container-lg bg-orange-400 h-screen"></section>
  </div>
</template>
<script>
export default {
  name: 'Home',
  data() {
    return {
      sections: ['home', 'about', 'products', 'contact'],
    }
  },
  mounted() {
    let el
    let observer
    this.sections.forEach((section) => {
      el = document.getElementById(section)
      observer = new IntersectionObserver(this.callback)
      observer.observe(el)
    })
  },
  methods: {
    callback(entries) {
      entries.forEach((entry) => {
        console.log(entry)
        if (entry.isIntersecting) {
          this.setNavActiveClass(entry.target.id)
        }
      })
    },
    setNavActiveClass(id) {
      this.sections.forEach((section) => {
        console.log(`nav-${section}`)
        const el = document.getElementById(`nav-${section}`)
        // you need to add same classes inside "if" and inside "else"
        if (id === section) {
          // change array items for active navbar item classes
          el.classList.add(...['border-b-2', 'border-black'])
          if (section !== 'home') {
            this.$router.push(`#${section}`)
          }
        } else {
          el.classList.remove(...['border-b-2', 'border-black'])
        }
      })
    },
  },
}
</script>
