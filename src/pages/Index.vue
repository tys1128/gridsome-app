<template>
  <Layout class="">
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <!-- <g-image alt="Example image" src="~/favicon.png" width="135" /> -->
    <div
      class="flex flex-wrap justify-center max-w-lg pt-36 mx-auto text-center pb-32"
    >
      <h1 class="font-extrabold text-5xl leading-tight mb-8">
        Simplicity. Aesthetics. Value.
      </h1>

      <p class="font-sans font-normal text-lg opacity-60 leading-relaxed">
        Hi there, I'm an independent Digital Designer & Art Director focused on
        digital design for brands that like to have fun.
      </p>
    </div>
    <g-link
      :to="`post/` + edge.node.id"
      class="flex flex-col text-center justify-center cursor-pointer"
      v-for="edge in $page.posts.edges"
      :key="edge.node.id"
    >
      <img
        class="transition transform hover:scale-105 hover:shadow-xl"
        :src="`${GRIDSOME_API_URL}${edge.node.photo.url}`"
        alt=""
      />
      <div class="mb-14 mt-8">
        <div class="my-4 font-semibold">{{ edge.node.title }}</div>
        <span
          class="mx-2 text-xs"
          v-for="tag in edge.node.categories"
          :key="tag"
          >{{ tag.tag }}</span
        >
      </div>
    </g-link>
    <div>
      <span class="block text-xs py-4 font-bold">LATEST AND GREATEST</span>
      <div class="flex">
        <g-link
          :to="`post/` + edge.node.id"
          class="font-semibold border border-separate border-gray-100 p-8 cursor-pointer hover:bg-gray-100 transition-all duration-300"
          v-for="edge in $page.posts.edges"
          :key="edge.node.id"
        >
          {{ edge.node.title }}
        </g-link>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query{
  posts: allStrapiPost{
    edges{
      node{
        id
        title
        author
        time
        content
        date
        photo{
          url
        }
        categories{
          tag
        }
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Hello, world!",
  },
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
