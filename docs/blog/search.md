#### Vue 模糊查询功能
原理：原生js的search() 方法，用于检索字符串中指定的子字符串，或检索与正则表达式相匹配的子字符串。如果没有找到任何匹配的子串，则返回 -1。



###### 1. input输入框
```cpp
<el-input placeholder="请您输入地址" v-model="value"></el-input>
<i class="el-icon-search" @click="searchAdress"></i>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200923185638121.png#pic_center)


###### 2. 循环的数据

```cpp
<ul>
   <li v-for="(item,index) in NewItems" :key="index" v-text="item.name"></li>
</ul>
```

```cpp
<script>

export default {

	data() {
	
		return {
		
			value: "",
			
			NewItems: [
			
				{ name: "上海" },
				
				{ name: "北京" },
				
				{ name: "重庆" }
				
			]
		
		};

 	},
	methods: {
		searchAdress () {
			var _this = this;
	        var NewItems = [];
	        this.NewItems.map(function (item) {
	          if (item.name.search(_this.value.trim()) != -1) {
	            NewItems.push(item);
	            console.log(NewItems);
	          }
	        });
	        this.NewItems = [];
	        this.NewItems = NewItems;
	        return NewItems;
		}
	},

};

</script>
```
