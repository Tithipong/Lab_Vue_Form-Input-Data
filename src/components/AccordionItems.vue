<template>
  <div id="accordion" v-for="(data, i) in formDataArray" v-bind:key="i">
    <div class="card">
      <div class="card-header" :id="'heading' + i">
        <h5 class="mb-0">
          <button
            class="btn btn-link collapsed"
            data-toggle="collapse"
            :data-target="'#collapse' + i"
            aria-expanded="true"
            :aria-controls="'collapse' + i"
          >
            [ {{ data.date }} ] {{ data.studentID }}
          </button>
        </h5>
      </div>

      <div
        :id="'collapse' + i"
        class="collapse show"
        aria-labelledby="headingOne"
        data-parent="#accordion"
      >
        <div class="card-body">
          <p class="mb-0"><strong>วันที่: </strong>{{ data.date }}</p>
          <p class="mb-0">
            <strong>คณะ (คณะใหม่): </strong>{{ data.faculty1 }}
          </p>

          <p class="mb-0"><strong>ชื่อ: </strong>{{ data.name }}</p>
          <p class="mb-0">
            <strong>รหัสนักศึกษา: </strong>{{ data.studentID }}
          </p>
          <p class="mb-0"><strong>สาขาวิชา: </strong>{{ data.major1 }}</p>
          <p class="mb-0"><strong>คณะ: </strong>{{ data.faculty2 }}</p>
          <p class="mb-0"><strong>โทรศัพท์: </strong>{{ data.telephone }}</p>
          <p class="mb-0"><strong>เครือข่าย: </strong>{{ data.network }}</p>
          <p class="mb-0">
            <strong>หลักสูตร: </strong>{{ data.course1 }}{{ data.course2 }}
          </p>
          <p class="mb-0">
            <strong>โอนย้ายไปสาขาวิชา: </strong>{{ data.major2 }}
          </p>
          <p class="mb-0"><strong>เหตุผลประกอบ: </strong>{{ data.reason }}</p>
          <p class="mb-0">
            <strong>วันที่ยื่นคำร้องโอนย้ายสาขาวิชาภายในคณะ: </strong
            >{{ data.reason }}
          </p>
          <p class="mb-0"><strong>อีเมล: </strong>{{ data.email }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
defineProps({
  formDataArray: Array,
});
</script>
<style scoped></style>
