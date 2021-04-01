<template>
  <Layout>
    <h1 class="text-6xl pt-36 pb-16 font-bold">Say hi!</h1>
    <p>
      Leave me a note with any questions you might have, I'll get back to you as
      soon as possible.
    </p>
    <form action="" method="post">
      <label for="name">name<input name="name" type="text"/></label>
      <label for="email">email<input name="email" type="email"/></label>
      <label class="w-full" for="message"
        >message<textarea name="message" type="text"
      /></label>
      <button
        @click.prevent="onSubmit"
        class="bg-black text-white p-4 leading-none"
        type="submit"
      >
        Submit form
      </button>
    </form>
  </Layout>
</template>

<script>
import axios from "axios";

export default {
  metaInfo: {
    title: "Contact",
  },
  methods: {
    onSubmit() {
      window.alert("发送成功");
    },
  },
};
</script>
<style>
form {
  @apply flex flex-wrap;
}
form label {
  @apply w-1/2 font-bold;
}

input,
textarea {
  @apply block border border-gray-100 w-full;
}
</style>
