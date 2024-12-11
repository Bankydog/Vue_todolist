<template>
    <div>
      <input
        type="text"
        v-model="newTodo"
        placeholder="เพิ่มงาน..."
        @keyup.enter="submitTodo"
      />
      <button @click="submitTodo">เพิ่ม</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTodo: '', // ข้อความรายการใหม่
      };
    },
    methods: {
      submitTodo() {
        if (this.newTodo.trim()) {
          this.$emit('add-todo', this.newTodo);
          this.newTodo = ''; // รีเซ็ตฟอร์ม
        }
      },
    },
  };
  </script>
  
  <style scoped>
  /* เพิ่มสไตล์เฉพาะส่วนนี้ */
  </style>
  