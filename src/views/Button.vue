<template>
  <div class="button-page">
    <v-breadcrumbs :items="items" large class="pa-0 mb-3"></v-breadcrumbs>
    <h1>Button Page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Button",
  components: {},
  data: () => ({
    items: [
      {
        text: "Dashboard",
        disabled: false,
        href: "/",
      },
      {
        text: "Button Page",
        disabled: true,
        href: "/button",
      },
    ],
  }),
};
</script>
