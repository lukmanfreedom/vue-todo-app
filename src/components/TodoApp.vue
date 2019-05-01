<template>
  <div>
    <!-- jumbotron -->
    <div class="jumbotron jumbotron-fluid text-center">
      <div class="container">
        <h1 class="display-4">Vue To-Do</h1>
        <p class="lead">To-Do App with VueJS</p>
      </div>
    </div>

    <div class="container">
      <div class="row">
        <!-- card input -->
        <div class="col-md-6 offset-md-1">
          <div class="card" style="margin: 10px">
            <div class="card-body">
              <h5 class="card-title">Buat To-Do</h5>
              <form>
                <div class="form-group">
                  <label for="title">Judul</label>
                  <input
                    type="text"
                    class="form-control"
                    placeholder="Masukan Judul"
                  >
                </div>

                <div class="form-group">
                  <label for="desc">Deskripsi</label>
                  <textarea
                    rows="3"
                    class="form-control"
                    placeholder="Masukan Deskripsi"
                  ></textarea>
                </div>

                <button
                  type="submit"
                  class="btn btn-success float-right"
                >
                  Tambah
                </button>
              </form>
            </div>
          </div>
        </div>

        <!-- card list -->
        <div class="col-md-4">
          <div v-for="todo in todos">
            <div class="card text-center" style="margin: 10px;">
              <div class="card-body">
                <h5 class="card-title">{{ todo.title }}</h5>
                <h6 class="card-subtitle mb-2 text-muted">{{ todo.desc }}</h6>
              </div>

              <div class="btn-group btn-block" role="group">
                <button type="button" class="btn btn-success">Beres</button>
                <button type="button" class="btn btn-danger">Hapus</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
  export default {
    props: ['todos'],
  };
</script>
