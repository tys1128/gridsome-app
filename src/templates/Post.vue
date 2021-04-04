<template>
  <Layout class="">
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <!-- <g-image alt="Example image" src="~/favicon.png" width="135" /> -->
    <div class="flex w-full flex-wrap pt-36 pb-32">
      <h1 class="font-extrabold text-5xl leading-tight mb-8">
        Simplicity. Aesthetics. Value.
      </h1>

      <section class="flex w-full text-xs leading-6">
        <div class="w-1/4">
          <p class="font-semibold">Categories</p>
          <p class="">
            {{ post.categories.map((c) => c.tag).join(",") }}
          </p>
        </div>
        <div class="w-1/4">
          <p class="font-semibold">Year</p>
          <p class="">{{ post.date.split("-")[0] }}</p>
        </div>
      </section>
    </div>
    <div
      class="leading-normal text-base mb-4"
      v-html="md2Html(post.content)"
    ></div>
    <img :src="`${GRIDSOME_API_URL}${post.photo.url}`" alt="" />
  </Layout>
</template>

<page-query>
query($id: ID!){
  strapiPost(id: $id){
    title
    categories {
      tag
    }
    time
    date
    photo{
      url
    }
    content
  }
}
</page-query>

<script>
import MarkdownIt from "markdown-it";
const md = new MarkdownIt();

export default {
  metaInfo: {
    title: "Hello, world!",
  },
  methods: {
    md2Html(mdText) {
      return md.render(mdText);
    },
  },
  computed: {
    post() {
      return this.$page.strapiPost;
    },
  },
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
