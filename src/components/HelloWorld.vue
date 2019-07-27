<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <div class="ex">
      <label>Example</label>
      <md-chips v-model="fruits" class="fruits">
        <!-- <div> <md-icon>search</md-icon></div> -->
      </md-chips>
    </div> 
    <div class="ex1">
       <label>Example</label>
      <md-field>
          <!-- <label for="country">Country</label> -->
      <md-select v-model="country" name="country" id="country" placeholder="Country">
        <md-option value="australia">Australia</md-option>
        <md-option value="brazil">Brazil</md-option>
        <md-option value="japan">Japan</md-option>
        <md-option value="united-states">United States</md-option>
      </md-select>
      </md-field>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import VueMaterial from "vue-material";
import "vue-material/dist/vue-material.min.css";
import "vue-material/dist/theme/default.css";
Vue.use(VueMaterial);

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data: () => ({
    fruits: ["Orange", "Apple", "Pineapple"],
    country: null
  })
};
</script>

<style >
.md-chip {
  border-radius: 0px;
}
.md-chip.md-theme-default {
  background: aliceblue;
}
.md-field {
  position: fixed;
  min-height: 29px;
  border-right: 1px solid;
  width: 500px;
  border-left: 1px solid;
  border-top: 1px solid;
  margin-left: 73px;
}
.md-chips.md-field {
  flex-wrap: nowrap;
}
.md-chips.md-field .md-chip {
  margin-left: 5px;
}
label {
  display: flex;
  margin-top: 20px;
  margin-left: 5px;
}
.ex {
  display: flex;
  flex-direction: row;
}
.md-menu.md-select {
  width: 500px;
  margin-left: 73px;
  flex: inherit;
}
.ex1 {
  display: flex;
  flex-direction: row;
  margin-top: 20px;
}
</style>
