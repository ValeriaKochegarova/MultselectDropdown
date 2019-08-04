<template>
  <div class="hello">
    <p>{{msg}}</p>
   <div >
     <select class="form-control" @change="change">
            <option value="">Choose</option>
            <option v-for="(fruit, index) in fruits" 
                    :key="index" :value="fruit.id"
                    :selected="selectedOption(fruit)">
                    {{ fruit.name }}
            </option>
        </select>
   </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      selected: null,
      fruits: [{ id: "1", name: "Banana" }, { id: "2", name: "Orange" }]
    };
  },
  methods: {
    selectedOption: function(option) {
      if (this.value) {
        return option.id === this.value.id;
      }
      return false;
    },
    change: function(e) {
      const selectedCode = e.target.value;
      const option = this.fruits.find(option => {
        return selectedCode === option.id;
      });
      this.$emit("input", option);
    }
  }
};
</script>

<style >
.form-control {
	position: relative;
	width: 200px;
	margin: 0 auto;
	padding: 10px;
	background: #fff;
	border-radius: 7px;
	border: 1px solid rgba(0,0,0,0.15);
	box-shadow: 0 1px 1px rgba(50,50,50,0.1);
	cursor: pointer;
	outline: none;
	font-weight: bold;
	color: #8AA8BD;
}
.form-control:after {
	content: "";
	width: 0;
	height: 0;
	position: absolute;
	right: 15px;
	top: 50%;
	margin-top: -3px;
	border-width: 6px 6px 0 6px;
	border-style: solid;
	border-color: #8aa8bd transparent;
}

</style>
