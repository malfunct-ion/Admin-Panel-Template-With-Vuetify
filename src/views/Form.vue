<template>
  <div class="form-page">
    <v-breadcrumbs :items="items" large class="pa-0 mb-3"></v-breadcrumbs>
    <h1>Form Page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Form",
  components: {},
  data: () => ({
    items: [
      {
        text: "Dashboard",
        disabled: false,
        href: "/",
      },
      {
        text: "Form Page",
        disabled: true,
        href: "/form",
      },
    ],
  }),
};
</script>
