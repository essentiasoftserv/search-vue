<template>
  <div class="searchengine">
    <label for="searchengine">Search here </label>
    <input type="text" name="searchengine" v-model="query">
    <div class="results" v-if="querydata">
      <ul>
        <li v-for="response in querydata">
          <b>DX Code :</b> {{response.DxCode}}
          <b> Hcc Category :</b> {{response.HCC_Category}}
          <b> Descritption :</b>{{response.Description}}
          <br>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Data from '../base.js';
import Fuse from 'fuse.js';
export default {
  name: 'SearchEngine',
  data() {
    return {
      query: '',
    }
  },
  computed: {
    querydata() {
      const fuseConfig = {
        threshold: 0.5,
        location: 0,
        distance: 100,
        maxPatternLength: 32,
        minMatchCharLength: 1,
        keys: [
          'DxCode','HCC_Category','Description'
        ],
      };
      const fuse = new Fuse(Data, fuseConfig);
      return fuse.search(this.query);
    },
  },
}
</script>

<style scoped>

</style>
