<template>
  <div class="container">
    <table class="table table-hover">
      <thead>
        <tr>
          <th scope="col">ID</th>
          <th scope="col">タイトル</th>
          <th scope="col">やること</th>
          <th scope="col">担当者</th>
          <th scope="col"></th>
          <th scope="col"></th>
          <th scope="col"></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(task, index) in tasks" :key="index">
          <th scope="row">{{ task.id }}</th>
          <td>{{ task.title }}</td>
          <td>{{ task.content }}</td>
          <td>{{ task.person_in_charge }}</td>
          <td>
            <router-link :to="{name: 'task.show', params: {taskId: task.id}}">
              <button class="btn btn-info">詳細</button>
            </router-link>
          </td>
          <td>
            <router-link :to="{name: 'task.edit', params: {taskId: task.id}}">
              <button class="btn btn-info">編集</button>
            </router-link>
          </td>
          <td>
            <button class="btn btn-danger">削除</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    data: function() {
      return{
        tasks: []
      }
    },
    methods: {
      getTasks() {
        axios.get('/api/tasks').then((res) => {
          this.tasks = res.data;
        });
      }
    },
    mounted() {
      this.getTasks();
    }
  }
</script>
