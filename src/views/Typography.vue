<template>
  <div class="typography">
    <v-breadcrumbs :items="items" large class="pa-0 mb-3"></v-breadcrumbs>
    <h1>Typography Page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Typography",
  components: {},
  data: () => ({
    items: [
      {
        text: "Dashboard",
        disabled: false,
        href: "/",
      },
      {
        text: "Typography Page",
        disabled: true,
        href: "/typography",
      },
    ],
  }),
};
</script>
