<template>
  <div class="container">
    <template v-for="(item, index) in this.questions">
      <div :key="index" class="column" :style="getColumnColor(index)">
        <FlipCard>
          <template slot="front">
            <span class="card-title">Vasoterapia</span>
            <h2>#{{index+1}}</h2>
          </template>
          <template slot="back">
            <h2>#{{index+1}}</h2>
            <span class="question">{{item}}</span>
          </template>
        </FlipCard>
      </div>
    </template>
  </div>
</template>

<script>
  import FlipCard from './FlipCard.vue';

  export default {
    name: 'Container',
    components: {
      FlipCard
    },
    data() {
      return {
        questions: [
          "¿Qué buen consejo te ha dado tu mamá?",
          "¿Cuál es tu mayor temor?",
          "Cuéntame algo de lo que estés orgullos@",
          "Cuéntanos el testimonio de cómo conociste a Jesús",
          "¿Para vos cuál es la canción más romántica?",
          "¿Que consideras fundamental en una relación de pareja?",
          "¿Qué te ayuda a entrar en calma?",
          "¿Cuál es tu mejor cualidad?",
          "Contamos una historia de tu infancia",
          "¿Qué piensas de tu apariencia física?",
          "Comodín: pregunta libre a alguien",
          "¿Qué te enamora de Jesús?",
          "Cuál es la mejor solución para una discusión pesada?",
          "¿Qué te hace feliz?",
          "¿Qué es lo primero que ves en otra persona?",
          "Cuéntanos cómo te sientes",
          "Cuéntanos algo de tu niñez que pocas personas saben",
          "Menciona 5 cualidades que tienes",
          "¿Qué necesitas perdonar?",
          "¿Que crees que debes recordarte todos los días?",
          "Algo que te de miedo que te pregunten",
          "¿Que es lo más valioso que has aprendido?",
          "Cuéntamos un secreto",
          "Cuéntanos de tus sueños",
          "¿Cuál es el problema más complejo que has logrado solucionar en los últimos meses?",
          "¿Cuál película te hace llorar?",
          "Termina la oración: Me encanta cuando ___",
          "Sientes orgullo de tu vida?",
          "Hablemos de tu mamá",
          "Comodín: pregunta libre a alguien"
        ]
      }
    },
    methods: {
      getColumnColor(index) {
        if (index % 2 === 0) {
          return "background-color:#ccc;";
        } else {
          return "background-color:#bbb;";
        }
      },
    }
  }
</script>

<style>
  * {
    box-sizing: border-box;
  }

  .column {
    float: left;
    width: 33.33%;
    padding: 10px;
  }

  /* Clear floats after the columns */
  .row:after {
    content: "";
    display: table;
    clear: both;
    margin: 5px;
  }
  .card-title {
    display: inline;
    position: relative;
    font: 50px Helvetica, Sans-Serif;
    letter-spacing: -5px;
    color: rgba(0,0,255,0.5);
  }

  .card-title:after {
    content: "Vasoterapia";
    position: absolute; left: 3px; top: 1px;
    color: rgba(255,0,0,0.5);
  }
  .center {
    margin: 0;
    position: absolute;
    top: 50%;
    left: 50%;
    -ms-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
  }
  @media screen and (max-width: 710px) {
    .card-title {
      font: 23px Helvetica, Sans-Serif;
      letter-spacing: -2px;
    }
    .card-title:after {
      position: absolute; left: 2px; top: 1px;
      color: rgba(255,0,0,0.5);
    }
    .question {
      font-size: 12px;
    }
  }
</style>