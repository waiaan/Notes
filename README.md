# problems-encountered
### 1、ie7 a标签后面的span元素向右浮动后错位：
#### 把span元素放在a标签之前。

### 2、display为none的tr，在ie7 rowspan的时候会计算在内。

### 3、只有设置了 name 属性的表单元素才能在提交表单时传递它们的值。

### 4、使display:inline-block兼容所有浏览器的方法是：
```css
display:inline-block;
*display:inline;
*zoom:1;
```

### 5、修改输入框placeholder文字默认颜色：
```css
:-moz-placeholder { /* Mozilla Firefox 4 to 18 */
     color: #000; opacity:1; 
 }
 ::-moz-placeholder { /* Mozilla Firefox 19+ */
     color: #000;opacity:1;
 }
 input:-ms-input-placeholder{
     color: #000;opacity:1;
 }
 input::-webkit-input-placeholder{
     color: #000;opacity:1;
 }
```
### 6、ie8下margin失效：
#### 给父级元素添加display:inline-block; 

### 7、input元素type为image时，提交表单会默认增加x和y字段，是image 输入类型会发送的点击图像按钮时的 X 和 Y 坐标。

### 8、p标签里面不能包含块级元素，否则会被推出来。

### 9、Scripts may close only the windows that were opened by it
```javascript
window.location.href="about:blank";
window.close();
``` 
### 10、HTML5全屏API
#### JavaScript
```javascript
/**
* [requestFullScreen 设置全屏]
*/
function requestFullScreen() {
	var de = document.documentElement;
	if (de.requestFullscreen) {
		de.requestFullscreen();
	} else if (de.mozRequestFullScreen) {
		de.mozRequestFullScreen();
	} else if (de.webkitRequestFullScreen) {
		de.webkitRequestFullScreen();
	}
}

/**
* [exitFullscreen 退出全屏]
*/
function exitFullscreen() {
	var de = document;
	if (de.exitFullscreen) {
		de.exitFullscreen();
	} else if (de.mozCancelFullScreen) {
		de.mozCancelFullScreen();
	} else if (de.webkitCancelFullScreen) {
		de.webkitCancelFullScreen();
	}
}

/**
* 返回正处于全屏状态的Element节点，如果当前没有节点处于全屏状态，则返回null。
*/
var fullscreenElement = document.fullscreenElement||
                        document.mozFullScreenElement||
                        document.webkitFullscreenElement;

/**
* 返回一个布尔值，表示当前文档是否可以切换到全屏状态。
*/
var fullscreenEnabled=document.fullscreenEnabled||
                      document.mozFullScreenEnabled||
                      document.webkitFullscreenEnabled||
                      document.msFullscreenEnabled;

/**
* 浏览器进入或离开全屏时触发。
*/
        document.addEventListener('fullscreenchange', function(){});
 
        document.addEventListener('webkitfullscreenchange', function(){});
 
        document.addEventListener('mozfullscreenchange', function(){});
 
        document.addEventListener('MSFullscreenChange', function(){});
        
/**
* 浏览器无法进入全屏时触发。
*/
        document.addEventListener('fullscreenerror', function(){});
 
        document.addEventListener('webkitfullscreenerror', function(){});
 
        document.addEventListener('mozfullscreenerror', function(){});
 
        document.addEventListener('MSFullscreenError', function(){});
```
#### CSS
```css
        :-webkit-full-screen {
          /* properties */
        }
 
        :-moz-full-screen {
          /* properties */
        }
 
        :-ms-fullscreen {
          /* properties */
        }
 
        :full-screen { /*pre-spec */
          /* properties */
        }
 
        :fullscreen { /* spec */
          /* properties */
        }
 
        /* deeper elements */
        video:-webkit-full-screen {
            width: 100%;
            height: 100%;
        }
```

### 11、对象的键总为字符串,因此obj[10]相当于obj["10"],obj[[1,0]]相当于obj["1,0"]。

### 12、命名函数表达式的函数名只对函数体内可见。

### 13、javascript循环性能
#### while循环比for循环快。
#### 倒序循环比顺序循环快。
#### 缓存length属性比不缓存快。
#### 请不要用arr[i]来判断是否中止循环。
#### 请不要在循环内声明变量，用它来引用数组元素，若真的想省几个字符，请在循环外声明。
#### 除非是循环对象的属性，请不要用for...in循环。
#### 请不要用JavaScript 1.6 的forEach迭代器，特慢！如果一定要用forEach，那么建议自己打造一个。

### 14、
|方法	                 |适用范围	                               |描述                                                    |
|------------------------- |----------------------------------------|-------------------------------------------------------|
|for..in	           |数组，对象	                        |获取可枚举的实例和原型属性名                              |
|Object.keys()	           |数组，对象	                        |返回可枚举的实例属性名组成的数组                           |
|Object.getOwnPropertyNames() |数组，对象	                        |返回除原型属性以外的所有属性（包括不可枚举的属性）名组成的数组|
|for..of	           |可迭代对象(Array, Map, Set, arguments等) |返回属性值                                                |

### 15、POST REQUEST BODY
```js
Content-Type:multipart/form-data; boundary=----WebKitFormBoundaryrGKCBY7qhFd3TrwA

------WebKitFormBoundaryrGKCBY7qhFd3TrwA
Content-Disposition: form-data; name="text"

title
------WebKitFormBoundaryrGKCBY7qhFd3TrwA
Content-Disposition: form-data; name="file"; filename="chrome.png"
Content-Type: image/png

PNG ... content of chrome.png ...
------WebKitFormBoundaryrGKCBY7qhFd3TrwA--
```

### 16、子元素的margin-top会传递给父元素
#### 修改父元素的高度，增加padding-top样式模拟
#### 为父元素添加overflow：hidden；样式即可
#### 为父元素或者子元素声明浮动
#### 为父元素添加border
#### 为父元素或者子元素声明绝对定位
