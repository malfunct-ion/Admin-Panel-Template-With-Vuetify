<template>
  <div class="table-page">
    <v-breadcrumbs :items="items" large class="pa-0 mb-3"></v-breadcrumbs>
    <h1>Table Page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Table",
  components: {},
  data: () => ({
    items: [
      {
        text: "Dashboard",
        disabled: false,
        href: "/",
      },
      {
        text: "Table Page",
        disabled: true,
        href: "/table",
      },
    ],
  }),
};
</script>
