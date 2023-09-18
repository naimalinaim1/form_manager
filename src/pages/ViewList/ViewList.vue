<template>
  <div class="container mt-5">
    <VueListSetting />
    <table class="table mt-5">
      <thead>
        <tr>
          <th scope="col">Current Status</th>
          <th scope="col">Name & Email</th>
          <th scope="col">Summary</th>
          <th scope="col">Tags</th>
          <th scope="col">Is Ready</th>
          <th scope="col">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(data, index) in viewData" :key="index">
          <td scope="row">
            <select class="form-select">
              <option value="submitted/pending">Submitted/Pending</option>
              <option value="confirmed">Confirmed</option>
            </select>
          </td>
          <td>
            <p><span class="fw-bold">Code:</span> {{ data.submission_code }}</p>
            <p><span class="fw-bold">Full Name:</span> {{ data.full_name }}</p>
            <p><span class="fw-bold">Email:</span> {{ data.email }}</p>
          </td>
          <td>
            <p>
              <span class="fw-bold">Organization:</span> {{ data.organization }}
            </p>
            <p>
              <span class="fw-bold">Designation:</span> {{ data.designation }}
            </p>
            <p><span class="fw-bold">Country:</span> {{ data.country }}</p>
          </td>
          <td></td>
          <td>No</td>
          <td>
            <a :href="'/edit?status=edit&id=' + data.id" class="btn btn-success me-2">Edit</a>
            <a class="btn btn-warning">View</a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import VueListSetting from "./VueListSetting.vue";
export default {
  components: {
    VueListSetting,
  },

  data() {
    return {
      viewData: [],
    };
  },

  methods: {
    getData() {
      fetch("http://localhost/php/api/")
        .then((res) => res.json())
        .then((data) => {
          if (data?.status == "true") {
            this.viewData = data.data;
          }
        });
    },
  },

  mounted() {
    this.getData();
  },
};
</script>

<style>
th {
  background: rgb(238, 232, 232) !important;
}
td p {
  margin: 0;
  font-size: 15px;
}
</style>