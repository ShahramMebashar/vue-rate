<template>
  <div id="app">
    <div class="container">
      <h1 style="margin-bottom: 20px;">Vue Rate Component</h1>
      <h2>Active Form</h2>
      <div class="grid">
        <div class="col-3">
          <p>
            <strong>Basic</strong>
            <rate v-model="myCurrentRate" :length="5" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Default value</strong>
            <rate :length="5" :value="3" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Show count</strong>
            <rate :length="5" :showcount="true" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Show count (Default value)</strong>
            <rate showcount :length="5" :value="3" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Rate Descriptions</strong>
            <rate :length="5" :ratedesc="desc" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Rate Descriptions (Default Value)</strong>
            <rate :length="5" :value="3" :ratedesc="desc" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Rate Descriptions (Read-only)</strong>
            <rate readonly :length="5" :value="3" :ratedesc="desc" />
          </p>
        </div>
      </div>
      <h2>Disabled Form</h2>
      <div class="grid">
        <div class="col-3">
          <p>
            <strong>Basic</strong>
            <rate showcount disabled :length="5" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Default value</strong>
            <rate disabled :length="5" :value="3" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Show count</strong>
            <rate disabled showcount :length="5" :value="3" />
          </p>
        </div>
        <div class="col-3">
          <p>
            <strong>Rate Descriptions</strong>
            <rate disabled :length="5" :value="3" :ratedesc="desc" />
          </p>
        </div>
      </div>

      <h2>Customization</h2>
      <div class="grid">
        <div class="flex-primary">
          <symbol id="icon-heart" class="icon" viewBox="0 0 32 32">
            <path d="M23.6 2c-3.363 0-6.258 2.736-7.599 5.594-1.342-2.858-4.237-5.594-7.601-5.594-4.637 0-8.4 3.764-8.4 8.401 0 9.433 9.516 11.906 16.001 21.232 6.13-9.268 15.999-12.1 15.999-21.232 0-4.637-3.763-8.401-8.4-8.401z"></path>
          </symbol>
          <rate class="RateCustom" :length="5" :value="3" :ratedesc="desc" iconref="icon-heart" />
          <details>
            <summary>Example</summary>
            <div class="code">
              <pre>&lt;template&gt;
  &lt;symbol id="icon-heart" class="icon" viewBox="0 0 32 32"&gt;
    &lt;path d="M23.6 2c-3.363 0-6.258 2.736-7.599 5.594-1.342-2.858-4.237-5.594-7.601-5.594-4.637 0-8.4 3.764-8.4 8.401 0 9.433 9.516 11.906 16.001 21.232 6.13-9.268 15.999-12.1 15.999-21.232 0-4.637-3.763-8.401-8.4-8.401z"&gt;&lt;/path&gt;
  &lt;/symbol&gt;

  &lt;rate class="RateCustom" :length="5" :value="3" :ratedesc="desc" iconref="icon-heart"&gt;
&lt;/template&gt;

&lt;style&gt;
  .RateCustom.Rate .icon {
    width: 25px;
    height: 25px;
  }
  .RateCustom.Rate .Rate__star.filled { color: blue; }
  .RateCustom.Rate .Rate__star.hover { color: red; }
&lt;/style&gt;</pre>
            </div>
          </details>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import rate from '../src/Rate'

export default {
  name: 'App',
  data () {
    return {
      myCurrentRate: 3,
      desc: ['Very Bad', 'Bad', 'Normal', 'Good', 'Very Good']
    }
  },
  components: {
    rate
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
}

#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px
}

.container {
  max-width: 1200px;
  padding: 0 20px;
  margin: 0 auto
}

.grid {
  display: flex;
  flex-wrap: wrap;
}

.code{
  text-align: left;
  background-color: #efefef;
  border-radius: 10px;
  padding: 20px;
  overflow: auto;
  max-width: 100%;
}

.code pre{margin: 0}

.Rate.RateCustom .icon {
  width: 25px;
  height: 25px;
}

.Rate.RateCustom .Rate__star.filled{color: teal;}
.Rate.RateCustom .Rate__star.hover{color: red;}

.flex-primary{ flex: 1; width: 100%; }
.grid [class*=col-]{padding: 0 20px;}
.grid .col-3{width: 100%}

@media screen and (min-width: 768px) {
  .grid .col-3{width: 50%;}
  .grid .col-2{width: 50%;}
}

@media screen and (min-width: 992px) {
  .grid .col-3{width: 25%;}
}
</style>

