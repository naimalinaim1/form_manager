<template>
  <section class="container">
    <form @submit.prevent="updateFormData">
      <!-- row  -->
      <div class="row mt-3">
        <!-- col -->
        <div class="col-md-6">
          <label for="code" class="form-label">
            Code <span class="text-danger">*</span>
          </label>
          <input
            type="text"
            id="code"
            class="form-control"
            v-model="formListAddField.code"
            required
          />
        </div>
        <!-- col -->
        <div class="col-md-6">
          <label for="fullName" class="form-label">
            Full Name <span class="text-danger">*</span>
          </label>
          <input
            type="text"
            id="fullName"
            class="form-control"
            v-model="formListAddField.fullName"
            required
          />
        </div>
      </div>

      <!-- row  -->
      <div class="row mt-3">
        <!-- col -->
        <div class="col-md-6">
          <label for="email" class="form-label">
            Email <span class="text-danger">*</span>
          </label>
          <input
            type="email"
            id="email"
            class="form-control"
            v-model="formListAddField.email"
            required
          />
        </div>
        <!-- col -->
        <div class="col-md-6">
          <label for="organization" class="form-label">
            Organization <span class="text-danger">*</span>
          </label>
          <input
            type="text"
            id="organization"
            class="form-control"
            v-model="formListAddField.organization"
            required
          />
        </div>
      </div>

      <!-- row  -->
      <div class="row mt-3">
        <!-- col -->
        <div class="col-md-6">
          <label for="designation" class="form-label">
            Designation <span class="text-danger">*</span>
          </label>
          <input
            type="text"
            id="designation"
            class="form-control"
            v-model="formListAddField.designation"
            required
          />
        </div>
        <!-- col -->
        <div class="col-md-6">
          <label for="country" class="form-label">
            Country <span class="text-danger">*</span>
          </label>
          <input
            type="text"
            id="country"
            class="form-control"
            v-model="formListAddField.country"
            required
          />
        </div>
      </div>

      <!-- row  -->
      <div class="row mt-3">
        <!-- col -->
        <div class="col">
          <label for="code" class="form-label"> Message </label>
          <textarea
            class="form-control"
            v-model="formListAddField.message"
          ></textarea>
        </div>
      </div>

      <!-- submit button -->
      <div class="mt-5">
        <input type="submit" class="btn btn-success me-3" value="Update" />
        <span>OR</span>
        <a href="../" class="ms-3 text-info text-decoration-none">Cancel</a>
      </div>
    </form>
  </section>
</template>
  
  <script>
export default {
  data() {
    return {
      formListAddField: {
        id: "",
        code: "",
        fullName: "",
        email: "",
        organization: "",
        designation: "",
        country: "",
        message: "",
      },
    };
  },
  mounted() {
    this.getEditData();
  },

  methods: {
    getEditData() {
      let query = location.href.split("?")[1];
      fetch(`http://localhost/php/api/data/singleData.php?${query}`)
        .then((res) => res.json())
        .then((data) => {
          if (data.status == "true") {
            const {
              id,
              submission_code,
              full_name,
              email,
              organization,
              designation,
              country,
            } = data.data[0];
            this.formListAddField.id = id;
            this.formListAddField.code = submission_code;
            this.formListAddField.fullName = full_name;
            this.formListAddField.email = email;
            this.formListAddField.organization = organization;
            this.formListAddField.designation = designation;
            this.formListAddField.country = country;
          } else {
            location.href = "/";
          }
        });
    },

    updateFormData() {
      const url = "http://localhost/php/api/data/updateData.php";
      const data = this.formListAddField;

      const headers = { "Content-Type": "application/json" };

      fetch(url, {
        method: "PUT",
        headers: headers,
        body: JSON.stringify(data),
      })
        .then((response) => {
          if (!response.ok) {
            throw new Error("Network response was not ok");
          }
          return response.json();
        })
        .then((responseData) => {
          if (responseData.status == "true") {
            alert("update successfull");
          }
        })
        .catch((error) => {
          alert("update problem");
          console.error("PUT request failed:", error);
        });
    },
  },
};
</script>