<template>
  <div>
      <ul>
	      <li v-for="(hero, index) in  heros" :key="index"
	      :class="{'A': 'red', 'B': 'green', 'C': 'blue', 'D': 'cyan', 'E': 'pink'}[hero.score]">
		      id:{{hero.id}}--->name:{{hero.name}}--->score:{{hero.score}}-->index:{{index}}
		      <button @click="delHeros(index)">删除</button>
	      </li><hr/>
	      英雄姓名：<input type="text" name="" v-model="name"><br/>
	      英雄成绩：<input type="text" name="" v-model="score"><br/>
	      <button @click="addHeros">添加英雄</button>
      </ul>
  </div>
</template>

<script>
	export default {
	    data() {
	        return {
	            name: null,
		        score: null,
	            heros:[{
	                id: 1,
		            name: '奥利安娜',
		            score: 'A'
	            },{
	                id: 2,
		            name: '崔斯特',
		            score: 'B'
	            },{
	                id: 3,
		            name: '李白',
		            score: 'C'
	            },{
	                id: 4,
		            name: '阿拉斯加',
		            score: 'D'
	            },{
	                id: 5,
		            name: '妲己',
		            score: 'E'
	            }]
	        }
	    },
	    methods: {
	        // 获取页面输入的值的时候，用v-model
	        addHeros() {
	            this.heros.push({
			        name: this.name,
		            score: this.score
		        });
                this.name = null;
                this.score = null;
	        },
		    delHeros(index) {
	            this.heros.splice(index);
		    }
	    }
	}
</script>

<style>
	.red {
		background-color: palevioletred;
	}
	.green {
		background-color: lightgreen;
	}
	.blue {
		background-color: skyblue;
	}
	.cyan {
		background-color: cyan;
	}
	.pink {
		background-color: pink;
	}
</style>