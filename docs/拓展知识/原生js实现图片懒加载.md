### 图片懒加载

#### 懒加载的优点
1. 改善用户体验
2. 优化代码
3. 减少网络请求数量
4. 减少服务器端压力
5. 服务器的按需加载

#### 实现思路
1. 在写`img`元素时，自定义一个属性`data-src`，用于存放图片的地址
2. 获取屏幕可视区域的尺寸
3. 获取元素到窗口边缘的距离
4. 判断元素是否在可视区域内，在则将`data-src`的值赋给`src`，否则不执行其他操作

?> 实质：当图片在可视区域内时才加载，否则不加载，也可以给个默认图片占位

#### 实现方法
```js
var imgs = document.querySelectorAll('img')

// 函数节流，定时器版本
function throttle(func,wait){
  let timer = null
  return function(...args){
    if(!timer){
      func(...args)
      timer = setTimeout(()=>{
        timer = null
      },wait)
    }
  }
}

// 窗口可视高度+滚动条高度 >
function lazyLoad(imgs){
  function isIn(el){ // 判断当前img是否在可视区域内
    let bound = el.getBoundingClientRect() // 获取相对浏览器可视区域的定位值
    let clentHeight = window.innerHeight // 浏览器窗口可视高度
    return bound.top <= clientHright+100 // 提前100px预加载
  }

  Array.from(imgs).forEach(img=>{
    if(isIn(img) && !img.src){
      img.src = img.dataset.src
    }
  })
}

const throttleLazyLoad = throttle(lazyLoad,200)

// 监听滚动事件
window.onload = window.scroll = function(){
  throttleLazyLoad(imgs)
}
```
