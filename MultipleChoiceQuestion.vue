<template>
<div>
<b-row>
<b-col sm="6" style = "font-weight:bold" md="8" class = "content" v-html="text"></b-col>
</b-row>
<b-row>
    <b-form-group>
      <b-form-checkbox-group
        :options="options"
        :name="name"
        stacked
      ></b-form-checkbox-group>
    </b-form-group>
  </b-row>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

export default {
  name: "MultipleChoiceQuestion",
  display: "MultipleChoiceQuestion",
  components: {},
props:['options', 'qid', 'text'],
  data() {
    return {
      "lst": this.list,
      "name": 'Q'+this.qid,
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