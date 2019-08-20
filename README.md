# Vue.js

v-bind 縮寫為：

v-on 縮寫為＠

v-once

v-html

>### computed 
有資料緩存的功能，若內部資料無更動則不會更新，無法帶參數進去，主要用來做計算

>### <template>
會顯示此內容但不會輸出此標籤
 
>### option value="disabled"
讓選單選像無法選取

>### trim() 清除空白鍵

>### V-for對於物件與陣列給回傳的值不一樣
陣列(a,b) in array// a=items, b=index 

物件(a,b) in obj  // a=items b=prop

>### Vue.set(target,key,value) 將資料寫入Vue的方法
true-value false-value

>### v-model

##### v-model.lazy 
類似on changed
##### v-model.number 
將輸出值轉為數字
##### v-model.trim 
消除多於空白建 


>### 修飾符號
#### .preventDefault()
事件修飾符號
#### .prevent
按鍵修飾符號

### 事件修飾符號
#### .stop

停止冒泡stopPropagation

#### .capture 

由外而內觸發

#### .self 

此物件觸發時只觸發此物件

#### .once 

只觸發一次

>### 修飾符號
##### 按鍵修飾符
`@keyCode` ex: `@keyup.13` 按下KeyCode相對應於13的按鈕才會觸發事件

`@keyup.enter` 按下enter時觸發事件

`@keyup.alt.enter` alt+enter要同時按才能觸發事件

##### 滑鼠修飾符
`@click.right` 右鍵觸發

還有 .midlde .left

>### <slot>
<slot></slot>能在component中插入物件
 
若直接在定義component時在<slot>中插入文字則為預設值，之後加入的<slot>則會取代此預設值
 
<any slot="這裡"> 搭配 <slot name="這裡">
