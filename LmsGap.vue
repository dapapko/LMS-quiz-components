<template>
 
     <draggable :move = "onMove" :single="0" class = "dragArea" v-model="list" :group="this.group" @start="drag=true" @end="drag=false">
   <div v-for="element in list" :key="element.id">{{element.name}}</div>
</draggable>
     
  
</template>

<script>
import draggable from "vuedraggable";
export default {
  name: "LmsGap",
  display: "LmsGap",
props:['qid'],
  components: {
    draggable,
  },
  data() {
    return {
"group": 'Q'+this.qid,
"single":1,
      list: [],
    };
  },
  methods: {
    
    log: function (evt) {
      window.console.log(evt);
    },
onMove: function (evt, originalEvent){
window.console.log(evt.relatedContext.component.$attrs.single);
  window.console.log(evt.relatedContext.component.$attrs.single === 0 || evt.relatedContext.list.length < 1)
  return (evt.relatedContext.list.length  < 1 || evt.relatedContext.component.$attrs.single  === 1);
},
  },
};
</script>
<style scoped>
.dragArea {
  min-height: 35px;
  max-width:1200px;
  border:2px solid #449fe7;
}
</style>