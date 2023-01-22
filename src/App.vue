<template>
  <div class="container">
    <div
      style="align-items: center; flex-direction: column"
      class="row mt-5 my-5"
    >
      <div class="col-md-6">
        <div class="card">
          <div class="card-header" style="font-size: 22px; text-align: center">
            ขอโอนย้ายสาขา
          </div>
          <div class="card-body">
            <form class="form">
              <div class="form-group">
                <label for="date1">วันที่:</label>
                <input
                  class="form-control"
                  type="date"
                  required
                  v-model="formData.date1"
                  id="date1"
                />
              </div>

              <div class="form-group">
                <label for="faculty1">คณะ (คณะใหม่):</label>
                <select
                  class="form-control"
                  type="text"
                  v-model="formData.faculty1"
                  id="faculty1"
                  required
                >
                  <option>คณะผลิตกรรมการเกษตร</option>
                  <option>คณะวิศวกรรมและอุตสาหกรรมเกษตร</option>
                  <option>คณะวิทยาศาสตร์</option>
                  <option>คณะบริหารธุรกิจ</option>
                  <option>คณะศิลปศาสตร์</option>
                  <option>คณะพัฒนาการท่องเที่ยว</option>
                  <option>คณะเทคโนโลยีการประมงและทรัพยากรทางน้ำ</option>
                  <option>คณะพัฒนาการท่องเที่ยว</option>
                  <option>คณะเศรษฐศาสตร์</option>
                  <option>คณะศิลปศาสตร์</option>
                  <option>วิทยาลัยพลังงานทดแทน</option>
                  <option>คณะสารสนเทศและการสื่อสาร</option>
                  <option>คณะสถาปัตยกรรมศาสตร์และการออกแบบสิ่งแวดล้อม</option>
                  <option>คณะสัตวศาสตร์และเทคโนโลยี</option>
                </select>
              </div>
              <div class="form-group">
                <label for="name">ชื่อ-นามสกุล:</label>
                <input
                  name="stdName"
                  class="form-control"
                  type="text"
                  required
                  maxlength="2000"
                  v-model="formData.name"
                />
              </div>
              <div class="form-group">
                <label for="studentID">รหัสนักศึกษา:</label>
                <input
                  class="form-control"
                  type="text"
                  required
                  v-model="formData.studentID"
                  id="studentID"
                />
              </div>

              <div class="form-group">
                <label for="telephone">เบอร์โทร:</label>
                <input
                  id="telephone"
                  class="form-control"
                  type="tel"
                  required
                  maxlength="10"
                  v-model="formData.telephone"
                />
              </div>
              <div class="form-group">
                <label for="network">เครือข่าย:</label>
                <select
                  class="form-control"
                  type="text"
                  v-model="formData.network"
                  id="network"
                >
                  กรุณาเลือก
                  <option>AIS</option>
                  <option>TRUE</option>
                  <option>DTAC</option>
                  <option>อื่นๆ</option>
                </select>
              </div>
              <div class="form-group">
                <label for="course">หลักสูตร:</label>
                <select
                  class="form-control"
                  type="text"
                  v-model="formData.course1"
                  id="course1"
                >
                  กรุณาเลือก
                  <option>4-5ปี</option>
                  <option>4ปีเทียบเข้าเรียน(2ปี)</option>
                </select>
                <select
                  class="form-control"
                  type="text"
                  v-model="formData.course2"
                  id="course2"
                >
                  กรุณาเลือก
                  <option>ภาคปกติ</option>
                  <option>ภาคสมทบ</option>
                </select>
              </div>
              <div class="form-group">
                <label for="major1">สาขาวิชา:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.major1"
                  id="major1"
                />
              </div>
              <div class="form-group">
                <label for="faculty2">คณะ (คณะเก่า):</label>
                <select
                  class="form-control"
                  type="text"
                  v-model="formData.faculty2"
                  id="faculty2"
                >
                  <option>คณะผลิตกรรมการเกษตร</option>
                  <option>คณะวิศวกรรมและอุตสาหกรรมเกษตร</option>
                  <option>คณะวิทยาศาสตร์</option>
                  <option>คณะบริหารธุรกิจ</option>
                  <option>คณะศิลปศาสตร์</option>
                  <option>คณะพัฒนาการท่องเที่ยว</option>
                  <option>คณะเทคโนโลยีการประมงและทรัพยากรทางน้ำ</option>
                  <option>คณะพัฒนาการท่องเที่ยว</option>
                  <option>คณะเศรษฐศาสตร์</option>
                  <option>คณะศิลปศาสตร์</option>
                  <option>วิทยาลัยพลังงานทดแทน</option>
                  <option>คณะสารสนเทศและการสื่อสาร</option>
                  <option>คณะสถาปัตยกรรมศาสตร์และการออกแบบสิ่งแวดล้อม</option>
                  <option>คณะสัตวศาสตร์และเทคโนโลยี</option>
                </select>
              </div>
              <div class="form-group">
                <label for="major2">โอนย้ายไปสาขาวิชา:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.major2"
                  id="major2"
                  maxlength="500"
                />
                <div class="form-group">
                  <label for="reason">สาเหตุ:</label>
                  <textarea
                    class="form-control"
                    v-model="formData.reason"
                    id="reason"
                  ></textarea>
                </div>
              </div>
              <div class="form-group">
                <label for="date2"
                  >วันที่ยื่นคำร้องโอนย้ายสาขาวิชาภายในคณะ (หลักสูตร4ปี):</label
                >
                <input
                  class="form-control"
                  type="date"
                  v-model="formData.date"
                  id="date2"
                />
              </div>
              <div class="form-group">
                <label for="email">อีเมล:</label>
                <input
                  class="form-control"
                  type="email"
                  v-model="formData.email"
                  id="email"
                />
              </div>

              <button
                type="submit"
                class="btn btn-primary"
                @click.prevent="submitForm"
              >
                Submit
              </button>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-8">
        <AccordionItems :formDataArray="formDataArray" />
      </div>
    </div>
  </div>
</template>

<script>
import AccordionItems from "./components/AccordionItems.vue";
export default {
  data() {
    return {
      formData: {
        date1: null,
        faculty1: "",
        name: "",
        studentID: "",
        telephone: "",
        network: "",
        course1: "",
        course2: "",
        major1: "",
        faculty2: "",
        major2: "",
        reason: "",
        date2: null,
        email: "",
      },
      formDataArray: [],
    };
  },
  components: {
    AccordionItems,
  },
  methods: {
    submitForm() {
      // Add the form data to the formDataArray
      this.formDataArray.push(this.formData);

      // Reset the formData object
      this.formData = {
        date1: null,
        faculty1: "",
        name: "",
        studentID: "",
        telephone: "",
        network: "",
        course1: "",
        course2: "",
        major1: "",
        faculty2: "",
        major2: "",
        reason: "",
        date2: null,
        email: "",
      };
    },
  },
};
</script>
<style scoped>
.center-div {
  display: flex;
  align-items: center;
}
.center-form {
  margin: 0 auto;
}
</style>
