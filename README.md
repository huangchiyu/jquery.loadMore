##  loadMore v1.01
边滚动边加载数据( Load the data while scrolling)



## 插件介绍
### 1. 使用环境
   * pc端

   * 移动端

   * 依赖jquery,版本没有特别的限制.

     

### 2. 基本功能



  #### &emsp;功能1: 滚动条到达底部时,执行用户指定的方法
    默认开启ajax请求数据
    也可以关闭ajax请求, 再指定一个回调函数做其他的事情

#### 

####  &emsp;功能2: 滚动条到达底部,启用ajax请求数据

  * 加载方式1: (手动) 点击 "加载更多" 加载内容

  * 加载方式2: (自动) 滚动条到达底部时自动加载新内容  
     两种功能可以自由选择
    
  * 选择加载方式1时,有默认的 "加载更多" 按钮,样式可以覆盖重写  
   
  * 支持某个元素的加载方式 和 整个页面的加载方式  
    
    
    
    01 单个元素自动加载效果   
   
    ![单个元素自动加载效果](images/autoLoad.png)   
     [点击查看demo演示](https://vincent2117.github.io/jquery.loadMore/demo/demo2-element-auto.html)  
    
    
    
    
    02 单个元素手动点击加载效果:  
    
    ![单个元素手动点击加载效果](images/clickLoad.png)        
    [点击查看手动点击加载demo演示](https://vincent2117.github.io/jquery.loadMore/demo/demo3-element-click.html)  
    
    
    
    03 给document绑定滚动事件    
    
    [点击查看document绑定效果](https://vincent2117.github.io/jquery.loadMore/demo/demo1-document-auto.html)  
    
    
### 3. 使用说明  



   * #### 参数介绍  

    // 关注
    loadType: 'auto', // 加载方式,自动加载或点击加载 auto || click
    ajaxSwitch: true, // 是否启用ajax请求, 可以选择不启用,到达底部执行一个回调函数
    url: '',
    data: {},
    type: 'get',
    success: function () {},  // 请求成功的回调
    error: function () {},    // 请求错误时的回调
    callback: function () {}, // 不启用ajax时,单纯的到达底部执行回调
    
    // 可选参数
    async: true,
    dataType: 'json', // 请求方式
    conLocation: "", // 加载更多 按钮追加到哪个元素下面, 默认为: body 或 当前元素
    scrollBottom: 100, // 距离底部100时执行回调
    imgLoading: loading, // 请求数据时显示的loading
    clickLoading: clickLoading, // "加载更多" 按钮



   * #### 在页面上调用jquery.loadMore
   >**单个元素,滚动事件的调用方式**  

     伪代码: 
     $('#box').loadMore({
     
        url: 'http://test.com',
        success: function (res) {
            console.log(res);
            render(res.data);
        } 
     });



   >**整个页面,滚动事件的调用方式**  

    伪代码: 
    $(document).loadMore({
    
       url: 'http://test.com',
       success: function (res) {
           console.log(res);
           render(res.data);
       } 
    });



### 4. 后面可能会添加的功能

   * ajax 跨域请求数据
   * 其他的没有想到,你要是有好主意可以给俺留言
