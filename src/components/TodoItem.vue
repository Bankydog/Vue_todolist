<template>
    <li>
      {{ todo }}
      <button @click="$emit('remove-todo')">ลบ</button>
    </li>
  </template>
  
  <script>
  export default {
    props: {
      todo: String, // รับข้อความรายการ
    },
  };
  </script>
  
  <style scoped>
  /* สไตล์เฉพาะของแต่ละรายการ */
  </style>
  