<script>
import Navbar from "./components/header/Navbar.vue";
import FormListAdd from "./pages/FormListAdd/FormListAdd.vue";
import ViewList from "./pages/ViewList/ViewList.vue";
import EditItem from "./pages/EditItem/EditItem.vue";

export default {
  components: {
    Navbar,
    FormListAdd,
    ViewList,
    EditItem,
  },

  data() {
    return {
      page: location.href.includes("add")
        ? "add"
        : location.href.includes("edit")
        ? "edit"
        : location.href.includes("view")
        ? "view"
        : "home",
    };
  },
};
</script>

<template>
  <header class="bg-info">
    <Navbar />
  </header>
  <main>
    <div v-if="page === 'home'">
      <div>
        <h2 class="text-center mt-5 text-primary">Form Managers</h2>
      </div>
    </div>
    <FormListAdd v-if="page === 'add'" />
    <ViewList v-if="page === 'view'" />
    <EditItem v-if="page === 'edit'" />
  </main>
</template>

<style>
</style>
