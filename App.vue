<template>
<div id = "app">
<b-row>
   <b-card no-body>
    <b-tabs pills card vertical>
      <b-tab title="Match Question" active>
        <b-card-text>
        <match-question :text = "text" :keys="keys" :values="values" :qid="4"></match-question>
        </b-card-text>
        </b-tab>

         <b-tab title="Fill gaps question" active>
        <b-card-text>
       <fill-gaps-question :options="keys" :content="text" :qid="132"></fill-gaps-question>
        </b-card-text>
        </b-tab>

         <b-tab title="Sequence question" active>
        <b-card-text>
    <sequence-question :list="keys" :qid="7" :text="text1"></sequence-question>
        </b-card-text>
        </b-tab>

      <b-tab title="Dropdown gaps">
        <b-card-text>
          <dropdown-gaps :content="text2" :dropdown="dropdown" qid="45"></dropdown-gaps>
        </b-card-text>
        </b-tab>

      <b-tab title="Multiple choice question"><b-card-text>
        <multiple-choice-question :text="text3" :options="options"></multiple-choice-question>
        </b-card-text></b-tab>

        <b-tab title="Single choice question"><b-card-text>
        <single-choice-question :text="text3" :options="options"></single-choice-question>
        </b-card-text></b-tab>

         <b-tab title="Short answer question"><b-card-text>
        <short-answer-question text="В каком году умер Николай II ?" qid="59" type="number"></short-answer-question>
        <short-answer-question text="Дополните фразу: ... жил, жив, ... будет жить" qid="59" type="text"></short-answer-question>
        </b-card-text></b-tab>
    </b-tabs>
  </b-card>
  </b-row>
  <b-row>
  </b-row>
  <b-row>
    


  </b-row>
  <b-row>
    

  </b-row>
  </div>
</template>

<script>
import MatchQuestion from "./components/MatchQuestion";
import FillGapsQuestion from "./components/FillGapsQuestion";
import DropdownGaps from "./components/DropdownGaps";
import SequenceQuestion from "./components/SequenceQuestion";
import MultipleChoiceQuestion from "./components/MultipleChoiceQuestion";
import SingleChoiceQuestion from "./components/SingleChoiceQuestion";
import ShortAnswerQuestion from "./components/ShortAnswerQuestion";


export default {
  data() {
    return {
text3:"<b>Выберите несколько вариантов ответа из предложенных</b>",
      options: ['водород', 'кислород', 'углерод'],
      dropdown:[['водород', 'кислород', 'углерод', 'ебал твой рот' ], 
      ['водород', 'кислород', 'углерод', 'ебал твой рот' ],
      ['водород', 'кислород', 'углерод', 'ебал твой рот' ],
      ['водород', 'кислород', 'углерод', 'ебал твой рот' ],
      ],
      text1:"Расположите события в хронологическом порядке",
text2: ` <b>Заполните пропуски в тексте, выбирая пропущенные слова из выпадающего спика</b>
<p>H - $$$, O - $$$ C - $$$ Я - $$$</p>`,
text: `
<div> <b>Fill in the gaps. Use NO MORE THAN THREE WORDS from the text</b>  </div>

When uranium was discovered to be radioactive, Marie Curie found that the element
called ### had the same property.
Huxley formulated his theory while studying a dinosaur belonging to a group
called ###.
Heilmann rejected Huxley’s theory because of the apparent absence of ### in
dinosaurs.
Feduccia and Martin believe that the ancestor of today’s birds was a kind of
early @@@ .
In cladistics, the ### between organisms’ characteristics are of major
importance.
The dangerous ### on a primitive bird from Madagascar adds weight to the
‘dino-bird’ argument.
`,
keys: [
  {"id":0, "name":"создание Государственного банка"}, 
  {"id":1, "name":"Отравление в Великом Новгороде Дмитрия Шемяки"},
{"id":2, "name": "введение рекрутской повинности"},
{"id":3, "name":"денежная реформа, установившая золотой червонец",
"id":4, "name": "бегство в Польшу Святополка Окаянного"},
{"id":5, "name":"создание стрелецкого войска"
}
],
values: [
  {"id":0, "name":"A) экономические реформы Александра II"}, 
  {"id":1, "name":"Б) новая экономическая политика"},
{"id":2, "name": "В) междоусобица сыновей Владимира Святославича"},
{"id":3, "name": "Г) реформы Избранной рады"}
],
    }
  },
  name: "App",
  components: {MatchQuestion, ShortAnswerQuestion, SingleChoiceQuestion,FillGapsQuestion, DropdownGaps, SequenceQuestion, MultipleChoiceQuestion}
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
