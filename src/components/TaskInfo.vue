<template>
<form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Edit Task Name</label>
      <input type="text" v-model="text" name="text" placeholder="Edit Task Name" />
    </div>
    <div class="form-control">
      <label>Edit Day & Time</label>
      <input type="text" v-model="day" name="day" placeholder="Edit Day & Time" />
    </div>
    <div class="form-control form-control-check">
      <label>Edit Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input type="submit" value="Save Edit" class="btn btn-block" />
  </form>
</template>

<script>
export default {
    name: 'TaskInfo',
    data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.text) {
        alert("Please Edit This task");
        return;
      }

      const editTask = {
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit('edit-task', editTask);

      this.text = "";
      this.day = "";
      this.reminder = false;
    },
  },
}
</script>

<style scoped>

.add-form {
  margin-bottom: -20px;
}
.form-control {
  margin: 10px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>