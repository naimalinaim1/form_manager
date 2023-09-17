<template>
  <div class="container">
    <h2 class="text-center my-5">View list</h2>
    <table class="table">
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
        <tr>
          <td scope="row">
            <select class="form-select">
              <option value="submitted/pending">Submitted/Pending</option>
              <option value="confirmed">Confirmed</option>
            </select>
          </td>
          <td>
            <p><span class="fw-bold">Code:</span> SB124045</p>
            <p><span class="fw-bold">Full Name:</span> Charles Selestin</p>
            <p><span class="fw-bold">Email:</span> naim@gmail.com</p>
          </td>
          <td>
            <p><span class="fw-bold">Organization:</span> It Company</p>
            <p><span class="fw-bold">Designation:</span> Adviser</p>
            <p><span class="fw-bold">Country:</span> United Kindom</p>
          </td>
          <td></td>
          <td>No</td>
          <td>
            <a class="btn btn-success me-2">Edit</a>
            <a class="btn btn-warning">View</a>
          </td>
        </tr>
        <tr>
          <td scope="row">
            <select class="form-select">
              <option value="submitted/pending">Submitted/Pending</option>
              <option value="confirmed">Confirmed</option>
            </select>
          </td>
          <td>
            <p><span class="fw-bold">Code:</span> SB124045</p>
            <p><span class="fw-bold">Full Name:</span> Charles Selestin</p>
            <p><span class="fw-bold">Email:</span> naim@gmail.com</p>
          </td>
          <td>
            <p><span class="fw-bold">Organization:</span> It Company</p>
            <p><span class="fw-bold">Designation:</span> Adviser</p>
            <p><span class="fw-bold">Country:</span> United Kindom</p>
          </td>
          <td></td>
          <td>No</td>
          <td>
            <a class="btn btn-success me-2">Edit</a>
            <a class="btn btn-warning">View</a>
          </td>
        </tr>
        <tr>
          <td scope="row">
            <select class="form-select">
              <option value="submitted/pending">Submitted/Pending</option>
              <option value="confirmed">Confirmed</option>
            </select>
          </td>
          <td>
            <p><span class="fw-bold">Code:</span> SB124045</p>
            <p><span class="fw-bold">Full Name:</span> Charles Selestin</p>
            <p><span class="fw-bold">Email:</span> naim@gmail.com</p>
          </td>
          <td>
            <p><span class="fw-bold">Organization:</span> It Company</p>
            <p><span class="fw-bold">Designation:</span> Adviser</p>
            <p><span class="fw-bold">Country:</span> United Kindom</p>
          </td>
          <td></td>
          <td>No</td>
          <td>
            <a class="btn btn-success me-2">Edit</a>
            <a class="btn btn-warning">View</a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {};
</script>

<style>
td p {
  margin: 0;
  font-size: 15px;
}
</style>