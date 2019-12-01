<template>
  <transition :name="!hidden ? 'slideUp' : 'slideDown'">
    <div v-if="!hidden" class="panel">
      <div class="body pt-3 info mx-5 px-5" style="justify-content: center;">
        <p style="width: 40%; max-width: 620px;" class="text">
          By accessing and using this website, you acknowledge that you have
          read and understand our <span class="hyperlink">Cookie Policy</span>,
          <span class="hyperlink">Privacy Policy</span>, and our
          <span class="hyperlink">Terms of Service</span>.
        </p>
        <mdbBtn
          class="button"
          style="width: 20%; max-width: 100px; max-height: 50px; font-size: 15px"
          @click="this.hide"
          >Got it</mdbBtn
        >
      </div>
    </div>
  </transition>
</template>

<script>
import { mdbBtn } from "mdbvue";

export default {
  name: "Panel",
  components: {
    mdbBtn
  },
  data() {
    return {
      hidden: false
    };
  },
  methods: {
    hide() {
      this.hidden = true;
    }
  }
};
</script>

<style scoped>
.panel {
  background-color: #e5e5e5;
  position: sticky;
  width: 100%;
  z-index: 100;
  top: 0;
}
.info {
  display: flex;
  flex-direction: row;
}
.hyperlink {
  color: #47f !important;
}
.button {
  background-color: #18c !important;
  text-transform: none;
  font-size: 1vw;
  padding: 0;
}
@media (max-width: 935px) {
  .info {
    width: 80vw;
  }
}
@media (max-width: 1170px) {
  .info {
    flex-direction: column;
    width: 85vw;
    align-items: center;
    padding: 0 !important;
    padding-top: 1rem !important;
    display: inline-grid;
  }
  .text {
    justify-content: center;
    margin-bottom: 0px !important;
    width: 80% !important;
  }
  .button {
    height: 50px;
    margin-bottom: 1rem !important;
  }
}
@media (min-width: 1260px) {
  .info {
    display: flex;
    text-align: justify;
  }
}
</style>
