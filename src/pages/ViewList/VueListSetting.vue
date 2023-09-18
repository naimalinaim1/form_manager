<template>
  <div class="d-flex justify-content-between border py-3 px-2 rounded">
    <!-- date view item -->
    <div>
      <select class="form-select" aria-label="Default select example">
        <option value="10">10</option>
        <option value="25">25</option>
        <option value="50">50</option>
      </select>
    </div>
    <!-- search by item -->
    <div>
      <select class="form-select" aria-label="Default select example">
        <option value="10">Search By</option>
        <option value="10">Search By</option>
      </select>
    </div>
    <!-- Search keyword -->
    <div class="d-flex">
      <input class="form-control" type="text" placeholder="Keyword...">
      <button class="btn btn-info mx-2">Search</button>
      <button class="btn text-info text-decoration-none">Clear</button>
    </div>
    <!-- Add -->
    <div>
      <a href="/add" class="btn btn-success">Add</a>
      <button class="btn btn-warning mx-2">Import</button>
      <button class="btn btn-info">Export/Print</button>
    </div>
  </div>
</template>
<script>
</script>