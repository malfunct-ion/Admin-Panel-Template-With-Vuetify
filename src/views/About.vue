<template>
  <div class="about-page">
    <v-breadcrumbs :items="items" large class="pa-0 mb-3"></v-breadcrumbs>
    <h1>About Page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "About",
  components: {},
  data: () => ({
    items: [
      {
        text: "Dashboard",
        disabled: false,
        href: "/",
      },
      {
        text: "About Page",
        disabled: true,
        href: "/about",
      },
    ],
  }),
};
</script>
