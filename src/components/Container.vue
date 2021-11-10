<template>
  <div class="container">
    <h1>Vasoterapia</h1>
    <div class="row">
      <div class="column" style="background-color:#aaa;">
        <FlipCard>
          <template slot="front">
            <span>Hey loser</span>
          </template>
          <template slot="back">
            <span>Thought u could get rid of me loser?</span>
          </template>
        </FlipCard>
      </div>
      <div class="column" style="background-color:#bbb;">
        <h2>Column 2</h2>
        <p>Some text..</p>
      </div>
      <div class="column" style="background-color:#ccc;">
        <h2>Column 3</h2>
        <p>Some text..</p>
      </div>
    </div>
  </div>
</template>

<script>
  import FlipCard from './FlipCard.vue';

  export default {
    name: 'Container',
    components: {
      FlipCard
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
  }
</style>