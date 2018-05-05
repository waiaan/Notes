# problems-encountered
### 1、ie7 a标签后面的span元素向右浮动后错位：
#### 把span元素放在a标签之前。

### 2、display为none的tr，在ie7 rowspan的时候会计算在内。

### 3、只有设置了 name 属性的表单元素才能在提交表单时传递它们的值。

### 4、使display:inline-block兼容所有浏览器的方法是：
#### display:inline-block;
#### *display:inline;
#### *zoom:1;

### 5、修改输入框placeholder文字默认颜色：
#### :-moz-placeholder { /* Mozilla Firefox 4 to 18 */
####     color: #000; opacity:1; 
#### }
#### ::-moz-placeholder { /* Mozilla Firefox 19+ */
####     color: #000;opacity:1;
#### }
#### input:-ms-input-placeholder{
####     color: #000;opacity:1;
#### }
#### input::-webkit-input-placeholder{
####     color: #000;opacity:1;
#### }

### 6、ie8下margin失效：
#### 给父级元素添加display:inline-block; 

### 7、input元素type为image时，提交表单会默认增加x和y字段，是image 输入类型会发送的点击图像按钮时的 X 和 Y 坐标。

### 8、p标签里面不能包含块级元素，否则会被推出来。

### 9、Scripts may close only the windows that were opened by it
#### window.location.href="about:blank";window.close();
  
