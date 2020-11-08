<template>
<div>
<b-row>
<b-col sm="6" style = "font-weight:bold" md="8" class = "content" v-html="text"></b-col>
</b-row>
<b-row>

  <draggable :single="1" :list="lst" :group="this.group" @start="drag=true" @end="drag=false">
   <div class ="col-7 options" v-for="element in lst"  :key="element.id">{{element.name}}</div>
</draggable>
 
  </b-row>
  </div>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: "SequenceQuestion",
  display: "SequenceQuestion",
  components: {draggable},
props:['list', 'text', 'qid'],
  data() {
    return {
      "lst": this.list,
      "group": 'Q'+this.qid,
    };
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
.options {
  border: 1px solid;
  min-width:10px;
  min-height:20px;
    border-color: #48a1e6;
    color: #48a1e6;
}
</style>