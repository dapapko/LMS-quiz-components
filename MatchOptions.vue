<template>
 
   <div class = "container">
     <draggable :move = "onMove" :single="1" v-model="lst" :group="this.group" @start="drag=true" @end="drag=false">
   <div v-for="element in lst" class = "options" :key="element.id">{{element.name}}</div>
</draggable>
</div>
    
  
</template>

<script>
import draggable from "vuedraggable";
export default {
  name: "Options",
  props:['list', 'qid'],
  display: "Options",
  order: 3,
  components: {
    draggable,
  },
  data() {
    
    return {
      "single": "0",
      "lst": this.list,
"group": 'Q'+ this.qid,
    };
  },
  methods: {
    log: function (evt) {
      window.console.log(evt);
    },
onMove: function (evt, originalEvent){
  return (evt.relatedContext.list.length  < 1);
},
  },
};
</script>
<style scoped>
.dragArea {
  min-width: 0px;
  min-height: 0px;
}
.options {
  border: 1px solid;
  min-width:10px;
  min-height:20px;
    border-color: #48a1e6;
    color: #48a1e6;
}
</style>