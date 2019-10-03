// this is a dynamically created template

<template>
  <article class="blog">
    <figure class="blog__hero" >
        <img :src="`/media/${ page.attributes.featured_image }`" :alt="page.attributes.title">
    </figure>
    <div class="blog__info" >
      <h1>{{ page.attributes.title }}</h1>
      <h3>{{ formattedDate }}</h3>
    </div>
    <div class="blog__body" v-html="page.html"></div>
  </article>
</template>
<script>
    export default {
        layout: "layout",
        // get the slug as a param to import the correct md file
        async asyncData({ params }) {
            try {
                // get current page data
                const page = await import(`~/content/pages/${params.slug}.md`);
                console.log(page)
                return {
                page
                }
            } catch(err) {
                console.debug(err)
                return false
            }
        }, 
    }
</script>