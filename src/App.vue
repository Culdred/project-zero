<template>
  <div id="app">
    <div v-show="isVisible">
      <strong>Main Page</strong>
      
      <div v-for="(stat, idx) in statList" :key="idx">

        <Perk :type="'stat'" :name="stat.name" :img-url="stat.img" max-value="20" />
        <div v-for="(perkTree, idx) in stat.perkTrees" :key="idx">
          <button id="perk-title"
            @click="
              isVisible = !isVisible;
              tree = perkTree.name;
              perks = perkTree.perks;
            "
          >
            {{ perkTree.name }}
          </button>
        </div>
      </div>
    </div>

    <div v-show="!isVisible">
      <PerksTree :name="tree" :perks="perks" />
    </div>
    
    <!-- TEST -->
    <!-- <div v-if="tree !== ''">
      <div v-show="!isVisible">
        <PerksTree :name="tree" :perks="perks" />
        -----------------------------------
        <div v-for="(perk, idx) in perks" :key="idx">
          <Perk
            :name="perk.name"
            :type="'perk'"
            :img-url="perk.imgUrl"
            :max-value="perk.maxValue"
          />
        </div>

      </div>
    </div> -->

    <button id="back-btn"
      v-show="!isVisible"
      @click="
        isVisible = !isVisible;
        tree = '';
      "
    >
      Back
    </button>
  </div>
</template>

<script>
import PerksTree from "./components/PerksTree.vue";
import Perk from "./components/Perk.vue";

export default {
  name: "App",
  components: {
    PerksTree,
    Perk,
  },
  data: function() {
    return {
      isVisible: true,
      tree: "",
      perks: [],
      statList: [
        {
          name: "Body",
          info: "",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/body-attribute-cyberpunk-2077-wiki-guide.png",
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
                },
                {
                  name: "Pack Mule",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/pack-mula-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                },
                {
                  name: "Epimorphisis",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/edimorphosis-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                },
                {
                  name: "Like a Butterfly",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/like-a-butterfly-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                },
                {
                  name: "Dog of War",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/dog-of-war-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
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
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/pump-it-louder-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
                },
                {
                  name: "Momentum Shift",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/momentum-shift-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
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
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/crushing-blows-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
                },
                {
                  name: "Opportune Strike",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/opportune-strike-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
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
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
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
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
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
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
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
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
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
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
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
          perkTrees: [
            {
              name: "Breach Protocol",
              perks: [
                {
                  name: "Total Recall",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/total-recall-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                },
                {
                  name: "Datamine Mastermind",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/datamine-mastermind-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 2,
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
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/critical-error-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 1,
                },
                {
                  name: "Plague",
                  requirement: "",
                  effects: [],
                  imgUrl: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/plauge-perk-cyberpunk-2077-wiki-guide.png",
                  maxValue: 3,
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
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
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
                },
                {
                  name: "perk2",
                  requirement: "",
                  effects: [],
                  imgUrl: "",
                  maxValue: 2,
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
