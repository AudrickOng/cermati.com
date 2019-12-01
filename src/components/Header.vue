<template>
  <mdbCard class="card-image bg">
    <div class="logo">
      <div class="text-white text-center py-5 px-4 my-5 info">
        <h2 class="card-title h1-responsive pt-3 font-bold">
          <strong>Hello! I'm Audrick</strong><br />
          <h4 class="pt-3 subtitle">
            Consult, Design and Develop Websites
          </h4>
        </h2>
        <p class="mx-5 mb-3">
          Have something great in mind? Feel free to contact me.<br />
          I'll help you to make it happen.
        </p>
        <mdbBtn outline="white" size="md" class="contact_btn"
          >LET'S MAKE CONTACT</mdbBtn
        >
      </div>
    </div>
  </mdbCard>
</template>

<script>
import { mdbCard, mdbBtn } from "mdbvue";
let height;
export default {
  name: "Header",
  components: {
    mdbCard,
    mdbBtn
  }
};
</script>

<style scoped>
.bg {
  background: url("../assets/bg.jpg");
  background-color: #007bc1;
  background-blend-mode: multiply;
  background-size: cover;
  height: auto;
  display: flex;
  flex-direction: row;
}
.logo {
  background-image: url("../assets/logo.png");
  background-repeat: no-repeat;
  background-size: 5vw 5vw;
  background-position: left top;
  margin: 1vw;
}
.info {
  width: 98vw;
}
.subtitle {
  font-weight: 600;
}
.contact_btn:hover {
  background-color: #fff !important;
  color: #007bc1 !important;
}
</style>
