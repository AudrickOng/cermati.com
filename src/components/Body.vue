<template>
  <div>
    <div class="body text-center py-5">
      <h2 class="card-title h1-responsive pt-3 font-bold" id="info">
        <strong>How Can I Help You?</strong><br />
      </h2>
      <p class="mx-5 mb-3" id="info">
        Our work then targeted, best practices outcomes social innovation
        synergy.<br />
        Venture philanthropy, revolutionary inclusive policymaker relief.
        User-centered program areas scale.
      </p>
    </div>
    <mdbCardGroup deck class="lists">
      <mdbCard
        v-for="(item, index) in items"
        :key="index"
        class="formattable_card"
      >
        <mdbCardBody>
          <div class="title">
            <mdbCardTitle>{{ item.title }}</mdbCardTitle>
            <div style="margin-left: auto;">
              <i :class="item.icon" class="icon" />
            </div>
          </div>
          <mdbCardText>{{ item.text }}</mdbCardText>
        </mdbCardBody>
      </mdbCard>
    </mdbCardGroup>
  </div>
</template>

<script>
import {
  mdbCardGroup,
  mdbCard,
  mdbCardBody,
  mdbCardTitle,
  mdbCardText
} from "mdbvue";
export default {
  name: "Body",
  components: {
    mdbCardGroup,
    mdbCard,
    mdbCardBody,
    mdbCardTitle,
    mdbCardText
  },
  data() {
    return {
      items: [
        {
          title: "Consult",
          text:
            "Co-create, design thinking; strengthen infrastructure resist granular. Revolution circular, movements or framework social impact low-hanging fruit. Save the world compelling revolutionary progress.",
          icon: "far fa-comments"
        },
        {
          title: "Design",
          text:
            "Policymaker collaborates collective impact humanitarian shared value vocabulary inspire issue outcomes agile. Overcome injustice deep dive agile issue outcomes vibrant boots on the ground sustainable.",
          icon: "fas fa-paint-brush"
        },
        {
          title: "Develop",
          text:
            "Revolutionary circular, movements a or impact framework social impact low-hanging. Save the compelling revolutionary inspire progress. Collective impacts and challenges for opportunities of thought provoking.",
          icon: "fas fa-cubes"
        },

        {
          title: "Marketing",
          text:
            "Peaceful; vibrant paradigm, collaborative cities. Shared vocabulary agile, replicable, effective altruism youth. Mobilize commitment to overcome injustice resilient, uplift social transparent effective.",
          icon: "fas fa-bullhorn"
        },

        {
          title: "Manage",
          text:
            "Change-makers innovation or shared unit of analysis. Overcome injustice outcomes strategize vibrant boots on the ground sustainable. Optimism, effective altruism invest optimism corporate social.",
          icon: "fas fa-tasks"
        },
        {
          title: "Evolve",
          text:
            "Activate catalyze and impact contextualize humanitarian. Unit of analysis overcome injustice storytelling altruism. Thought leadership mass incarceration. Outcomes big data, fairness, social game-changer.",
          icon: "fas fa-chart-line"
        }
      ]
    };
  }
};
</script>

<style scoped>
.body {
  background-color: #e5e5e5;
  padding: 0 30vw;
  color: #000;
}
.title {
  display: flex;
}
.lists {
  flex-direction: row !important;
  flex-wrap: wrap !important;
  padding-bottom: 5vh;
  background-color: #e5e5e5;
}
.formattable_card {
  background-color: #e5e5e5;
  min-width: 25vw;
  margin: 5vh;
  border: 1px solid #ccc;
  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
  border-radius: 0px;
}
.icon {
  font-size: 25px;
}
#info {
  max-width: 1366px;
}
@media (max-width: 1300px) {
  .body {
    padding: 0 10vw;
  }
}
</style>
