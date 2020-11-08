<template>
<div>
<b-row>
<b-col sm="6" style = "font-weight:bold" md="8" class = "content" v-html="text"></b-col>
</b-row>
<b-row>
<b-col sm="4">
   <match-options :list = "keys" :qid="qid"></match-options>
   </b-col>
<b-col sm="4">
  <div v-for = "value in values" :key = "value.id">
<p>{{value.name}}</p>
   <lms-gap :qid="qid"></lms-gap>
   </div>
   </b-col>
  </b-row>
  </div>
</template>

<script>
import MatchOptions from "/src/components/MatchOptions";
import LmsGap from "/src/components/LmsGap";

export default {
  name: "MatchQuestion",
  display: "MatchQuestion",
  components: {
     MatchOptions, LmsGap
  },
props:['keys', 'values', 'text', 'qid'],
  data() {
    return {};
  },
  methods: {
    
    log: function (evt) {
      window.console.log(evt);
    },

  },
};
</script>
<style scoped>
.content {
  font-weight:400;
  line-height:1.3;
  margin-left:5%;
}
.dragArea {
  min-height: 35px;
  width:50%;
  max-width:1200px;
  border:1px dashed #449fe7;
}
</style>