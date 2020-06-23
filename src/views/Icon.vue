<template>
  <div class="icon-page">
    <v-breadcrumbs :items="items" large class="pa-0 mb-3"></v-breadcrumbs>
    <h1>Icon Page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Icon",
  components: {},
  data: () => ({
    items: [
      {
        text: "Dashboard",
        disabled: false,
        href: "/",
      },
      {
        text: "Icon Page",
        disabled: true,
        href: "/icon",
      },
    ],
  }),
};
</script>
