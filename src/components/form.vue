<template>
  <div>
    <form action="">
      <div>วันที่ <input type="date" v-model="person.Date" required /></div>
      <div>
        ด้วยข้าพเจ้าสอบได้วุฒิ <input type="text" v-model="person.Quation" />
      </div>
      <div>
        จากสถานศึกษา <input type="text" v-model="person.University" /> เมื่อ พ.ศ
        <input type="number" v-model="person.Year" />
      </div>
      <div>
        <input type="text" v-model="person.Wish" />
      </div>
      <div>
        ของกระทรวงศึกษาธิการเพื่อ
        <input type="text" v-model="person.To" /> โปรดพิจารณาข้าพเจ้าด้วย
      </div>
      <div>
        ที่อยู่ปัจจุบันของข้าพเจ้า บ้านเลขที่
        <input type="text" v-model="person.Address" /> เบอร์โทรติดต่อ
        <input type="number" v-model="person.Phone" />
      </div>
      <div>ลงชื่อ <input type="text" v-model="person.Name" /> (ผู้ขอเทียบ)</div>
    </form>
    <div class="form-check">
      <input
        class="form-check-input"
        type="checkbox"
        value=""
        id="flexCheckChecked"
        checked
      />
      <label class="form-check-label" for="flexCheckChecked">
        ข้าพเจ้าได้ตรวจสอบข้อมูลเรียบร้อยแล้ว
      </label>
    </div>
    <div><button @click="awesome = !awesome">ส่ง</button></div>
    <div v-if="awesome">
      <div v-for="(value, key, index) in person" :key="index">
        {{ key }}: {{ value }}
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from "vue";
const awesome = ref(false);
var person = ref({
  Date: "",
  Quation: "",
  University: "",
  Year: "",
  Wish: "",
  To: "",
  Address: "",
  Phone: "",
  Name: "",
});
</script>
