<template>
  <div id="app">
    <button
      id="back-btn"
      v-show="!isVisible"
      @click="
        isVisible = !isVisible;
        tree = '';
      "
    >
      Back
    </button>

    <div v-show="isVisible">
      <strong>Main Page</strong>

      <div v-for="(stat, statIdx) in statList" :key="statIdx">
        <Perk
          @changeValue="stat.value = $event"
          :type="'stat'"
          :name="stat.name"
          :img-url="stat.img"
          :max-value="20"
          :value="stat.value"
        />
        <div
          v-for="(perkTree, perkTreeIdx) in stat.perkTrees"
          :key="perkTreeIdx"
        >
          <button
            id="perk-title"
            @click="
              isVisible = !isVisible;
              tree = perkTree.name;
              perkTreeIndex = perkTreeIdx;
              statIndex = statIdx;
            "
          >
            {{ perkTree.name }}
          </button>
        </div>
      </div>
    </div>

    <div v-if="tree !== ''">
      <div v-show="!isVisible">
        <strong>{{ tree }}</strong>
        <div
          v-for="(perk, idx) in statList[statIndex].perkTrees[perkTreeIndex]
            .perks"
          :key="idx"
        >
          <Perk
            @changeValue="perk.value = $event"
            :name="perk.name"
            :type="'perk'"
            :img-url="perk.imgUrl"
            :max-value="perk.maxValue"
            :value="perk.value"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Perk from "./components/Perk.vue";

export default {
  name: "App",
  components: {
    Perk,
  },
  data: function() {
    return {
      isVisible: true,
      tree: "",
      statIndex: 0,
      perkTreeIndex: 0,
      statList: [
        {
          name: "Body",
          info: "",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/body-attribute-cyberpunk-2077-wiki-guide.png",
          value: 0,
          perkTrees: [
            {
              name: "Athletics",
              perks: [
                {
                  name: "Gladiator",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/gladiator-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "Pack Mule",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/pack-mula-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
                {
                  name: "Epimorphisis",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/edimorphosis-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                  value: 0,
                },
                {
                  name: "Like a Butterfly",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/like-a-butterfly-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
                {
                  name: "Dog of War",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/dog-of-war-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "Marathoner",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/marathoner-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
                {
                  name: "Multitasker",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/multitasker-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
                {
                  name: "Steel and Chrome",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/steel-and-chrome-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "Divided Attention",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/divided-attention-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
                {
                  name: "Invincible",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/invincible-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                  value: 0,
                },
                {
                  name: "Soft on your feet",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/soft-on-your-feet-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                  value: 0,
                },
              ],
            },
            {
              name: "Annihilation",
              perks: [
                {
                  name: "Pump it, louder!",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/pump-it-louder-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "Momentum Shift",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/momentum-shift-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                  value: 0,
                },
              ],
            },
            {
              name: "Street Brawler",
              perks: [
                {
                  name: "Crushing Blows",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/crushing-blows-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                  value: 0,
                },
                {
                  name: "Opportune Strike",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/opportune-strike-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
              ],
            },
          ],
        },
        {
          name: "Reflexes",
          info: "",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/reflexes-attribute-cyberpunk-2077-wiki-guide.png",
          value: 0,
          perkTrees: [
            {
              name: "Blades",
              perks: [
                {
                  name: "perk1",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
            {
              name: "Handguns",
              perks: [
                {
                  name: "perk1",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
            {
              name: "Assault",
              perks: [
                {
                  name: "perk1",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
          ],
        },
        {
          name: "Technical Ability",
          info: "",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/technical-ability-attribute-cyberpunk-2077-wiki-guide.png",
          value: 0,
          perkTrees: [
            {
              name: "Crafting",
              perks: [
                {
                  name: "perk1",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
            {
              name: "Engineering",
              perks: [
                {
                  name: "perk1",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
          ],
        },
        {
          name: "Intelligence",
          info: "",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/intelligence-attribute-cyberpunk-2077-wiki-guide.png",
          value: 0,
          perkTrees: [
            {
              name: "Breach Protocol",
              perks: [
                {
                  name: "Total Recall",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/total-recall-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
                {
                  name: "Datamine Mastermind",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/datamine-mastermind-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
            {
              name: "Quickhacks",
              perks: [
                {
                  name: "Critical Error",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/critical-error-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                  value: 0,
                },
                {
                  name: "Plague",
                  requirement: "",
                  effects: [],
                  imgUrl:
                    "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/plauge-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                  value: 0,
                },
              ],
            },
          ],
        },
        {
          name: "Cool",
          info: "",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/cool-attribute-cyberpunk-2077-wiki-guide.png",
          value: 0,
          perkTrees: [
            {
              name: "Stealth",
              perks: [
                {
                  name: "perk1",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
            {
              name: "Cold Blood",
              perks: [
                {
                  name: "perk1",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
                  value: 0,
                },
              ],
            },
          ],
        },
      ],
    };
  },
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
#perk-title {
  width: 122px;
}
#perk-title:hover {
  background: midnightblue;
  color: rgb(10, 235, 216);
  border-radius: 5px;
}
#perk {
  background: midnightblue;
  color: yellow;
  border-radius: 5px;
}
#stat {
  background: midnightblue;
  color: rgb(10, 235, 216);
  border-radius: 5px;
}
#back-btn {
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
