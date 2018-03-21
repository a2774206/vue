<template>
  <div>
  	<ul class="list_con">
  		<li v-for="(list,i) in listCon" v-if="i===indexJ" @click="revise(list)">
  			{{list}}
  		</li>
  	</ul>
  </div>
</template>

<script>
export default {
  name: 'child',
  data () {
    return {
     listCon:['新闻内容','奢侈品','今日头条','旅行计划','房屋/买车']
    }
  },
  methods:{
  	revise(index){
  		this.$emit('reviseTitle',index);
  	}
  },
  props:['indexJ']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
  
  overflow: hidden;
  width: 480px;
  margin: 0 auto;
  display: flex;
  text-align: center;
}
li {
  display: inline-block;
  flex: 5;
  
}
a {
  color: #42b983;
}
.title li{
	float: left;
	list-style: none;

	cursor: pointer;
}
.list_con{
	clear: both
}
</style>
