<template>
<b-row>
    
    <b-col>
<match-options :list="options" :qid="qid"></match-options>
    </b-col>
  <b-col>
<fill-gaps :content = "content" :qid="name"></fill-gaps>
</b-col>
</b-row>
  
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import FillGaps from "/src/components/FillGaps"
import MatchOptions from "/src/components/MatchOptions"
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

export default {
  name: "FillGapsQuestion",
  display: "FillGapsQuestion",
  components: {FillGaps, MatchOptions},
  props:['content', 'qid', 'options'],
  data() {
    return {
      name:'Q'+ this.qid+'[]',
    };
  },
  methods: {},
 
};
</script>
<style scoped></style>