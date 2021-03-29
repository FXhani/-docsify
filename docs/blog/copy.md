#####	在业务需求中，需要实现点击复制链接的功能
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201026150856927.png#pic_center)

话不多说，直接上代码

```cpp
// 这是在template中的代码
<div class="profile_inner_middlelink">
   <div class="profile_inner_middlelink_http">
     {{httpLink}}
   </div>
   <el-button type="primary" @click="handleCopy()" plain>复制链接</el-button>
 </div>
```

```cpp
//data 中声明变量
data() {
	return {
      httpLink: "https://www.baidu.com/",
    }
}
```
methods方法：

```cpp
handleCopy() {
  this.copy(this.httpLink)
},
copy(data) {
  let url = data;
  let oInput = document.createElement('input');
  oInput.value = url;
  document.body.appendChild(oInput);
  oInput.select(); // 选择对象;
  console.log(oInput.value)
  document.execCommand("Copy"); // 执行浏览器复制命令
  this.$message({
    message: '复制成功',
    type: 'success'
  });
  oInput.remove()
},
```
