<template>
  <div>
    <img
      style="height: 150px"
      src="https://upload.wikimedia.org/wikipedia/th/thumb/b/b7/MJU_LOGO.svg/1200px-MJU_LOGO.svg.png"
      alt=""
    />
  </div>
  <div>
    <form action="">
      <div>วันที่ <input type="date" v-model="person.date" /></div>
      <div>
        ด้วยข้าพเจ้าสอบได้วุฒิ <input type="text" v-model="person.quation" />
      </div>
      <div>
        จากสถานศึกษา <input type="text" v-model="person.Univers" /> เมื่อ พ.ศ
        <input type="number" v-model="person.year" />
      </div>
      <div>
        มีความประสงค์จะขอใบเทียบวุฒิการศึกษาเท่า
        <input type="text" v-model="person.want" />
      </div>
      <div>
        ของกระทรวงศึกษาธิการเพื่อ
        <input type="text" v-model="person.T" /> โปรดพิจารณาข้าพเจ้าด้วย
      </div>
      <div>
        ที่อยู่ปัจจุบันของข้าพเจ้า บ้านเลขที่
        <input type="text" v-model="person.As" /> เบอร์โทรติดต่อ
        <input type="number" v-model="person.phone" />
      </div>
      <div>ลงชื่อ <input type="text" v-model="person.name" /> (ผู้ขอเทียบ)</div>
    </form>
    <div><button @click="awesome = !awesome">ส่ง</button></div>

    <div v-if="awesome" >
      <div v-for="(value, key, index) in person" :key="index">
        {{ key }}: {{ value }}
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from "vue";
const awesome = ref(false)
var person = ref({
  date: "",
  quation: "",
  Univers: "",
  year: "",
  want: "",
  T: "",
  As: "",
  phone: "",
});

var show = ref([]);
for (const key in person) {
    if (Object.hasOwnProperty.call(person, key)) {
        show = person[key];
    }
}
console.log(show);
function submit() {
  cshow = false;
}
</script>
