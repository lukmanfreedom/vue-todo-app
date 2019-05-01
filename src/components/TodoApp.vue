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

              <div class="form-group">
                <label for="title">Judul</label>
                <input
                  type="text"
                  class="form-control"
                  placeholder="Masukan Judul"
                  v-model="title"
                >
              </div>

              <div class="form-group">
                <label for="desc">Deskripsi</label>
                <textarea
                  rows="3"
                  class="form-control"
                  placeholder="Masukan Deskripsi"
                  v-model="desc"
                ></textarea>
              </div>

              <button
                class="btn btn-success float-right"
                v-on:click="addTodo()"
              >
                Tambah
              </button>
            </div>
          </div>
        </div>

        <!-- card list -->
        <div class="col-md-4">
          <div v-for="todo in todos">
            <div
              class="card text-center"
              style="margin: 10px;"
              :class="todo.done ? greenCard : ''"
            >
              <div class="card-body">
                <h5
                  class="card-title"
                  v-bind:style="todo.done ? textLine : ''"
                >
                  {{ todo.title }}
                </h5>

                <h6
                  class="card-subtitle mb-2"
                  :class="todo.done ? '' : 'text-muted'"
                >
                  {{ todo.desc }}
                </h6>
              </div>

              <div class="btn-group btn-block" role="group">
                <button
                  type="button"
                  class="btn btn-success"
                  v-on:click="doneTodo(todo)"
                  :class="todo.done ? 'disabled' : ''"
                >
                  Beres
                </button>

                <button
                  type="button"
                  class="btn btn-danger"
                  v-on:click="deleteTodo(todo)"
                >
                  Hapus
                </button>
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
    data() {
      return {
        title: '',
        desc: '',
        textLine: 'text-decoration:line-through',
        greenCard: 'text-white bg-success',
      }
    },
    methods: {
      deleteTodo(todo) {
        const todoIndex = this.todos.indexOf(todo);
        this.todos.splice(todoIndex, 1);
      },
      addTodo() {
        this.todos.push({
          title: this.title,
          desc: this.desc,
          done: false,
        });

        this.title = '';
        this.desc = '';
      },
      doneTodo(todo) {
        const todoIndex = this.todos.indexOf(todo);
        this.todos[todoIndex].done = true;
      },
    },
  };
</script>
