<template>
  <div id="app">
    <div v-show="isVisible">
      
      <div v-for="(stat, idx) in statList" :key="idx">
        <Perk :name="stat.name" :img-url="stat.img" max-value=20 />
        <div v-for="(perkTree, idx) in stat.perkTrees" :key="idx">
          <button @click="isVisible = !isVisible; tree='perkTree'">{{ perkTree }}</button>
        </div>
      </div>

      <!-- <Perk name="Body" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/body-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Athletics'">Athletics</button>
      <button @click="isVisible = !isVisible; tree='Annihilation'">Annihilation</button>
      <button @click="isVisible = !isVisible; tree='Street Brawler'">Street Brawler</button>

      <Perk name="Reflexes" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/reflexes-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Blades'">Blades</button>
      <button @click="isVisible = !isVisible; tree='Handguns'">Handguns</button>
      <button @click="isVisible = !isVisible; tree='Assault'">Assault</button>

      <Perk name="Technical Ability" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/technical-ability-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Crafting'">Crafting</button>
      <button @click="isVisible = !isVisible; tree='Engineering'">Engineering</button>

      <Perk name="Intelligence" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/intelligence-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Breach'">Breach</button>
      <button @click="isVisible = !isVisible; tree='Quickhacks'">Quickhacks</button>
      
      <Perk name="Cool" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/cool-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Stealth'">Stealth</button>
      <button @click="isVisible = !isVisible; tree='Cold Blood'">Cold Blood</button> -->

    </div>

    <div v-for="(perkTree, idx) in perkTreeList" :key="idx">
      <div v-if="tree === perkTree">
        <PerksTree :name='perkTree' />
      </div>
    </div>

    <!-- <div v-if="tree === 'Athletics'">
        <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Annihilation'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Street Brawler'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Blades'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Handguns'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Assault'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Crafting'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Engineering'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Breach'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Quickhacks'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Stealth'">
      <PerksTree :name='tree' />
    </div>
    <div v-if="tree === 'Cold Blood'">
      <PerksTree :name='tree' />
    </div> -->

    <button v-show="!isVisible" @click="isVisible = !isVisible; tree=''">
      Back
    </button>

  </div>
</template>

<script>
import PerksTree from './components/PerksTree.vue'
import Perk from './components/Perk.vue'

export default {
  name: 'App',
  components: {
    PerksTree,
    Perk,
  },
  data: function() {
    return {
      isVisible: true,
      tree: "",
      perkTreeList: [
        "Athletics",
        "Annihilation",
        "Street Brawler",
        "Blades",
        "Handguns",
        "Assault",
        "Crafting",
        "Engineering",
        "Breach",
        "Quickhacks",
        "Stealth",
        "Cold Blood"
        ],
      statList: [
        {
          name: "Body",
          img: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/body-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            "Athletics",
            "Annihilation",
            "Street Brawler",
          ]
        },
        {
          name: "Reflexes",
          img: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/reflexes-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            "Blades",
            "Handguns",
            "Assault",
          ]
        },
        {
          name: "Technical Ability",
          img: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/technical-ability-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            "Crafting",
            "Engineering",
          ]
        },
        {
          name: "Intelligence",
          img: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/intelligence-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            "Breach",
            "Quickhacks",
          ]
        },
        {
          name: "Cool",
          img: "https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/cool-attribute-cyberpunk-2077-wiki-guide.png",
          perkTrees: [
            "Stealth",
            "Cold Blood",
          ]
        }
      ]
    }
  },
}
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
