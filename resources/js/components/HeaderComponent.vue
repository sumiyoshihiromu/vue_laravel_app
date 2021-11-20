<template>
  <div class="container-fluid bg-dark mb-3">
    <div class="container">
      <nav class="navbar navbar-dark">
        <span class="navbar-brand mb-0 h1">TO DO APPだよ</span>
        <div>
          <router-link v-bind:to="{name: 'task.list'}">
            <button class="btn btn-info">一覧</button>
          </router-link>
          <button class="btn btn-info">タスク追加</button>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
  export default {}
</script>
