<template>
  <div>
    <input type="text" name="pokemon-search" v-on:keyup="searchPokemon" v-model="search">
    <ul class="pokedex-container">
      <li class="pokemon-box" v-bind:key="pokemon.id" v-for="pokemon in Pokedex" v-show="!pokemon.hidden">
        <img height="72" v-bind:src="pokemon.img" v-bind:alt="pokemon.name">
        <h1>{{ pokemon.name }}</h1>
        <ul>
          <li v-bind:class="'type-' + type.toLowerCase()" v-bind:key="type" v-for="type in pokemon.type">{{ type }}</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
import Pokedex from '../assets/data/pokedex.json';

export default {
  name: 'Pokedex',
  props: {
    msg: String
  },
  data() {
    return {
      Pokedex,
      search: ''
    };
  },
  methods: {
    searchPokemon: function() {
      let inputValue = this.search;

      Pokedex.forEach(pokemon => {
        if (pokemon.name.toLowerCase().includes(inputValue.toLowerCase())) {
          pokemon.hidden = false;
        } else {
          pokemon.hidden = true;
        }
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.pokedex-container {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.pokemon-box {
  width: 218px;
  height: 100%;
  border-radius: 16px;
  background: white;
  box-shadow: 0 32px 128px -64px black;
  padding: 30px 15px;
  margin: 15px;
}

h1 {
  margin: 0 0 10px;
  font-size: 28px;
  color: #2e2e2e;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, .2);
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

[class^="type"] {
  padding: 0 8px;
  line-height: 20px;
  box-shadow: inset 0 0 0 1px rgba(0, 0, 0, .1);
  color: white;
  border-radius: 10px;
  font-weight: bold;
  font-size: 12px;
  margin: 0 5px;
  background-image: linear-gradient(0deg, rgba(0, 0, 0, .1) 0%, rgba(0, 0, 0, 0) 100%);
  text-shadow: 1px 1px 0 rgba(0, 0, 0, .4);
  display: inline-block;
}

.type-normal {
  background-color: #bdbdae;
}

.type-grass {
  background-color: #88d049;
}

.type-fire {
  background-color: #fa5643;
}

.type-water {
  background-color: #56adff;
}

.type-fighting {
  background-color: #a85643;
}

.type-flying {
  background-color: #79a2ff;
}

.type-poison {
  background-color: #aa5da2;
}

.type-ground {
  background-color: #edcc56;
}

.type-rock {
  background-color: #cdbc72;
}

.type-bug {
  background-color: #c2d21f;
}

.type-ghost {
  background-color: #7975d7;
}

.type-electric {
  background-color: #fee63c;
}

.type-psychic {
  background-color: #fa64b4;
}

.type-ice {
  background-color: #96f2ff;
}

.type-dragon {
  background-color: #8a75ff;
}

.type-dark {
  background-color: #8f6a56;
}

.type-steel {
  background-color: #c3c1da;
}

.type-fairy {
  background-color: #f9adff;
}
</style>
