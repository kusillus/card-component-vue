<template>
    <div id="app">
        <img src="./assets/logo.png">
        <h3>
            {{tittle}}
        </h3>
        <div class="container_cards">
            <card-item
                v-for="item in posts"
                :title="item.title"
                :content="item.content"
                :img="item.img"
                :id="item.id">
            </card-item>
        </div>
    </div>
</template>

<script>
import card from './components/cCardItem.vue'
export default {
    name: 'app',
    data () {
        return {
            tittle: 'JCC POKÉMON',
            posts: [
                {
                    id: 1,
                    title: 'Silvally-GX',
                    content: 'Este ataque hace 50 puntos de daño por cada Pokémon en Banca de tu rival. (No puedes usar más de 1 ataque GX en una partida).',
                    img: 'SM4_ES_119.png',
                },
                {
                    id: 2,
                    title: 'Leafeon-GX',
                    content: 'Cuando un Pokémon-GX queda Fuera de Combate, el rival toma 2 cartas de Premio.',
                    img: 'SM5_ES_13.png',
                },
                {
                    id: 3,
                    title: 'Pikachu-EX',
                    content: 'Descarta todas las Energías Lightning unidas a este Pokémon. Este ataque hace 50 puntos de daño por cada carta de Energía que hayas descartado',
                    img: 'XYP_ES_XY124.png',
                },
                {
                    id: 4,
                    title: 'Piechu-GX',
                    content: 'Cada vez que un Pikachu se encuentra con algo nuevo, le lanza una descarga eléctrica. Cuando se ve alguna baya chamuscada',
                    img: 'XYP_ES_XY84.png',
                },
            ]
        }
    },
    components:{
        'card-item': card
    }
}
</script>

<style lang="scss">
body{
  background-color: #f4da00;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
.container_cards{
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
}
</style>
