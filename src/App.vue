<template>
  <div id="app">
    <div v-show="isVisible">
      
      <!-- Body -->
      <Perk name="Body" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/body-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Athletics'">Athletics</button>
      <button @click="isVisible = !isVisible; tree='Annihilation'">Annihilation</button>
      <button @click="isVisible = !isVisible; tree='Street Brawler'">Street Brawler</button>

      <!-- Reflexes -->
      <Perk name="Reflexes" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/reflexes-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Blades'">Blades</button>
      <button @click="isVisible = !isVisible; tree='Handguns'">Handguns</button>
      <button @click="isVisible = !isVisible; tree='Assault'">Assault</button>

      <!-- Technical Ability -->
      <Perk name="Technical Ability" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/technical-ability-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Crafting'">Crafting</button>
      <button @click="isVisible = !isVisible; tree='Engineering'">Engineering</button>

      <!-- Intelligence -->
      <Perk name="Intelligence" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/intelligence-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Breach'">Breach</button>
      <button @click="isVisible = !isVisible; tree='Quickhacks'">Quickhacks</button>
      
      <!-- Cool -->
      <Perk name="Cool" :img-url="'https://cyberpunk2077.wiki.fextralife.com/file/Cyberpunk-2077/cool-attribute-cyberpunk-2077-wiki-guide.png'" max-value=20 />
      <button @click="isVisible = !isVisible; tree='Stealth'">Stealth</button>
      <button @click="isVisible = !isVisible; tree='Cold Blood'">Cold Blood</button>

    </div>

    <div v-if="tree === 'Athletics'">
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
    </div>

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
