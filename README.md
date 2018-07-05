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

### 11、对象的键总为字符串,因此obj[10]相当于obj["10"],obj[[1,0]]相当于obj["1,0"]
