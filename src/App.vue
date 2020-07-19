<template>
  <div id="app">
    <div class="control_wrapper" style="margin:50px auto 0; width:350px;">
        <h2>Multiselection dropdown</h2>
        <ejs-multiselect id='multiselect'  :dataSource='sportsData' :fields='fields' placeholder="Select a game"
        mode="CheckBox" :showSelectAll='showSelectAll' selectAllText="Select All" unSelectAllText="unSelect All"
        :close='closeEvent' :showDropDownIcon='showDropDownIcon' :filterBarPlaceholder='searchGame'
        ></ejs-multiselect>
    </div>
  </div>
</template>
<script>
import Vue from 'vue';
import { MultiSelectPlugin } from "@syncfusion/ej2-vue-dropdowns";
import { MultiSelect, CheckBoxSelection } from '@syncfusion/ej2-dropdowns';
MultiSelect.Inject(CheckBoxSelection);
Vue.use(MultiSelectPlugin);

export default Vue.extend({
  data: function() {
    return {
      sportsData: [
        { Id: 'game1', Game: 'Badminton' },
        { Id: 'game2', Game: 'Football' },
        { Id: 'game3', Game: 'Tennis' },
        { Id: 'game4', Game: 'Basketball' }
      ],
      fields : { text: 'Game', value: 'Id' },
       showSelectAll : true,
       showDropDownIcon: true,
       searchGame: "Search game"
    };
  },
  methods: {
       closeEvent: function(args) {
         const multiselectObj = document.getElementById('multiselect').ej2_instances[0];
         console.log("close")
       }
    }
});
</script>
<style lang="scss">
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-dropdowns/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
</style>
