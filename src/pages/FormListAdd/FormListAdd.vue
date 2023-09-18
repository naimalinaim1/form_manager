<template>
  <section class="container">
    <form @submit.prevent="submitForm">
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
          <label for="code" class="form-label">
            Message <span class="text-danger">*</span>
          </label>
          <textarea
            class="form-control"
            v-model="formListAddField.message"
            required
          ></textarea>
        </div>
      </div>

      <!-- submit button -->
      <div class="mt-5">
        <input type="submit" class="btn btn-success me-3" value="Save" />
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
  methods: {
    submitForm() {
      const url = "http://localhost/php/api/";
      const jsonData = JSON.stringify(this.formListAddField);
      const headers = {
        "Content-Type": "application/json",
      };
      const requestOptions = {
        method: "POST",
        headers: headers,
        body: jsonData,
      };

      // Send the POST request using the fetch API
      fetch(url, requestOptions)
        .then((response) => {
          if (!response.ok) {
            throw new Error("Network response was not ok");
          }
          return response.json();
        })
        .then((data) => {
          if (data?.status == "true") {
            alert("Successful");
            // cear form data
            this.formListAddField = {
              code: "",
              fullName: "",
              email: "",
              organization: "",
              designation: "",
              country: "",
              message: "",
            };
          }
        })
        .catch((error) => {
          console.error("There was a problem with the fetch operation:", error);
          alert("Problem");
        });
    },
  },
};
</script>