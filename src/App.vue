<template>
  <div id="app">
    <button
      class="back-btn"
      v-if="!isChildPage"
      @click="isChildPage = !isChildPage"
    >
      Back
    </button>

    <div v-if="isChildPage">
      <strong>Main Page</strong>

      <div v-for="(stat, statIdx) in statList" :key="statIdx">
        <Perk
          type="stat"
          :name="stat.name"
          :img-url="stat.img"
          :max-value="20"
          v-model="allocatedPoints[stat.name]"
        />
        <div
          v-for="(perkTree, perkTreeIdx) in stat.perkTrees"
          :key="perkTreeIdx"
        >
          <button
            class="perk-title"
            @click="
              isChildPage = !isChildPage;
              perkTreeIndex = perkTreeIdx;
              statIndex = statIdx;
            "
          >
            {{ perkTree.name }}
          </button>
        </div>
      </div>
    </div>

    <div v-if="!isChildPage">
      <strong>{{ statList[statIndex].perkTrees[perkTreeIndex].name }}</strong>
      <div
        v-for="(perk, idx) in statList[statIndex].perkTrees[perkTreeIndex]
          .perks"
        :key="idx"
      >
        <Perk
          :name="perk.name"
          :type="'perk'"
          :img-url="perk.imgUrl"
          :max-value="perk.maxValue"
          v-model="allocatedPoints[perk.name]"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Perk from "./components/Perk.vue";
import {
  coolStats,
  intelligenceStats,
  technicalAbilityStats,
  reflexesStats,
  bodyStat,
} from "./data";

export default {
  name: "App",
  components: {
    Perk,
  },
  data() {
    return {
      isChildPage: true,
      statIndex: 0,
      perkTreeIndex: 0,
      allocatedPoints: {},
      statList: [
        coolStats,
        intelligenceStats,
        technicalAbilityStats,
        reflexesStats,
        bodyStat,
      ],
    };
  },
  watch: {
    allocatedPoints: {
      immediate: false,
      deep: true,
      handler(value) {
        const stringifiedBuild = JSON.stringify(value);
        var newurl = `${window.location.protocol}//${window.location.host}${window.location.pathname}?saved=${stringifiedBuild}`;
        window.history.pushState({ path: newurl }, "", newurl);
      },
    },
  },
  mounted() {
    const params = new URLSearchParams(window.location.search);
    this.allocatedPoints = JSON.parse(params.get("saved"));
  },
  methods: {},
};
</script>

<style>
body {
  background: rgb(204, 147, 40);
}
img {
  height: 70px;
  width: 70px;
}
.container {
  display: flex;
}
.perk-title {
  width: 122px;
}
.perk-title:hover {
  background: midnightblue;
  color: rgb(10, 235, 216);
  border-radius: 5px;
}
.perk {
  background: midnightblue;
  color: yellow;
  border-radius: 5px;
}
.stat {
  background: midnightblue;
  color: rgb(10, 235, 216);
  border-radius: 5px;
}
.back-btn {
  width: 115px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>
