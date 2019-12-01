<template>
  <transition :name="hidden ? 'slideUp' : 'slideDown'">
    <div v-if="!hidden" class="box">
      <div class="head">
        <h4 class="title">{{ title }}</h4>
        <button
          type="button"
          class="close"
          aria-label="Close"
          @click="this.hide"
        >
          <span aria-hidden="true">×</span>
        </button>
      </div>
      <p>{{ text }}</p>
      <div class="form">
        <input
          type="text"
          class="form-control text"
          placeholder="Email address"
        />
        <mdbBtn color="amber" class="accept" @click="this.hide"
          >Count me in!</mdbBtn
        >
      </div>
    </div>
  </transition>
</template>

<script>
import { mdbBtn } from "mdbvue";
export default {
  name: "News",
  components: {
    mdbBtn
  },
  data() {
    return {
      title: "Get latest updates in web technologies",
      text:
        "I write articles related to web technologies, such as design trends, development tools, UI/UX case studies and reviews, and more. Sign up to my newsletter to get them all.",
      hidden: false
    };
  },
  methods: {
    hide() {
      this.hidden = true;
      localStorage.setItem("deadline", Date.now() + 600000);
    },
    verifyTime() {
      const deadline = localStorage.getItem("deadline");
      const seconds = Math.floor((deadline - Date.now()) / 1000);
      if (seconds <= 0) {
        this.hidden = false;
        localStorage.removeItem("deadline");
      } else {
        this.hidden = true;
      }
    }
  },
  beforeCreate() {
    if (localStorage.getItem("deadline")) {
      window.setInterval(() => {
        this.verifyTime();
      }, 1000);
    } else {
      window.clearInterval();
    }
  }
};
</script>

<style scoped>
.box {
  max-width: 640px;
  background-color: #007bc1;
  position: fixed;
  z-index: 100;
  bottom: 0;
  margin: 10px;
  padding: 2%;
  color: #fff;
}
.head {
  display: flex;
  flex-direction: row;
}
.title {
  flex-wrap: wrap;
}
h4 {
  font-weight: 900;
}
.form {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}
.text {
  width: 65%;
}
.accept {
  width: 30%;
}
.close {
  margin-left: auto;
  align-self: start;
  color: #fff;
}
@media (max-width: 570px) {
  .form {
    flex-direction: column;
    align-content: center;
  }
  .text {
    width: 100%;
  }
  .accept {
    width: 100%;
    text-transform: none;
  }
}
</style>
