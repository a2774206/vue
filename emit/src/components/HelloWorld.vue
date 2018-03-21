<template>
  <div>
  	<h1>
    	{{msg}}
    </h1>
    <div>
    		<ul class="title">
    			<li v-for="(list,i) in listTitle" @click="clicklist(i)">{{list}}</li>
    		</ul>
    		<div>
    			<child :indexJ = 'index' v-on:reviseTitle="reviseFn"></child>
    		</div>
    </div>
  </div>
</template>

<script>
	//parent:hellorld.vue
	//child :child.vue
import child from './child/child'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'props/$emit',
      listTitle:['新闻','团购','论坛','活动','分类'],
      listCon:['新闻内容','奢侈品','今日头条','旅行计划','房屋/买车'],
      index:0
    }
  },
  methods:{
  	clicklist(i){
  		this.index = i; 
  	},
  	reviseFn(index){
  		this.msg = index;
  	}
  },
  components:{
  	child
  }
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
