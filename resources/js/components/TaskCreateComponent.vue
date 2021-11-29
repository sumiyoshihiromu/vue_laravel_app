<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-sm-6">
        <form>
          <div class="form-group row">
            <label for="title" class="col-sm-3 col-form-label">タイトル</label>
            <input type="text" class="col-sm-9" id="title">
          </div>
          <div class="form-group row">
            <label for="content" class="col-sm-3 col-form-label">やること</label>
            <input type="text" class="col-sm-9" id="content">
          </div>
          <div class="form-group row">
            <label for="person-in-charge" class="col-sm-3 col-form-label">担当者</label>
            <input type="text" class="col-sm-9" id="person-in-charge">
          </div>
          <button type="submit" class="btn btn-info">送信</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
  export default{
    data: function () {
      return {
        task: {}
      }
    },
    methods: {
      submit() {
        axios.post('/api/tasks', this.task).then((res) => {
          this.$router.push({name: 'task.list'});
        });
      }
    }
  }
</script>
