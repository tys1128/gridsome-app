<template>
  <Layout>
    <h1>Say hi!</h1>
    <p>
      Leave me a note with any questions you might have, I'll get back to you as
      soon as possible.
    </p>
    <form action="" method="post">
      <label for="name">name</label><input name="name" type="text" />
      <label for="email">email</label><input name="email" type="email" />
      <label for="message"></label><textarea name="message" type="text" />
      <button type="submit">Submit form</button>
    </form>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Contact",
  },
};
</script>
