<template>
  <div id="app">
    <div v-show="isVisible">
      <div v-for="(stat, idx) in statList" :key="idx">
        <Perk :name="stat.name" :img-url="stat.img" max-value="20" />

        <div v-for="(perkTree, idx) in stat.perkTrees" :key="idx">
          <button
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

    <button
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
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/body-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            {
              name: "Athletics",
              perks: [
                {
                  name: "perk1",
                  imgUrl:
                    "https://image.shutterstock.com/image-vector/three-gear-sign-simple-icon-260nw-417078436.jpg",
                  maxValue: 2,
                },
                {
                  name: "perk2",
                  imgUrl: "",
                  maxValue: 3,
                },
              ],
            },
            {
              name: "Annihilation",
              perks: [
                {
                  name: "perk1",
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
                  imgUrl: "",
                  maxValue: 2,
                },
              ],
            },
            {
              name: "Street Brawler",
              perks: [
                {
                  name: "perk1",
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
                  imgUrl: "",
                  maxValue: 2,
                },
              ],
            },
          ],
        },
        {
          name: "Reflexes",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/reflexes-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            {
              name: "Blades",
              perks: [
                {
                  name: "perk1",
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
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
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
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
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
                  imgUrl: "",
                  maxValue: 2,
                },
              ],
            },
          ],
        },
        {
          name: "Technical Ability",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/technical-ability-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            {
              name: "Crafting",
              perks: [
                {
                  name: "perk1",
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
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
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
                  imgUrl: "",
                  maxValue: 2,
                },
              ],
            },
          ],
        },
        {
          name: "Intelligence",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/intelligence-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            {
              name: "Breach",
              perks: [
                {
                  name: "perk1",
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
                  imgUrl: "",
                  maxValue: 2,
                },
              ],
            },
            {
              name: "Quickhacks",
              perks: [
                {
                  name: "perk1",
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
                  imgUrl: "",
                  maxValue: 2,
                },
              ],
            },
          ],
        },
        {
          name: "Cool",
          img:
            "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/cool-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            {
              name: "Stealth",
              perks: [
                {
                  name: "perk1",
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
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
                  imgUrl: "",
                  maxValue: 2,
                },
                {
                  name: "perk2",
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
