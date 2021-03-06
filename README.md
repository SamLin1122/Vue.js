# Vue.js

>### 入門
#### v-bind 縮寫為：
#### v-on 縮寫為＠
#### v-once
#### v-html

>### computed
有資料緩存的功能，若內部資料無更動則不會更新，無法帶參數進去，主要用來做計算

>### filter
n為|前面的參數

    <div>{{ item.cash | dollarSign}}</div>
    
    Vue.filter("dollorSign",function(n){
     return `$ ${n}`
    })

>### mixin

可混和多個元件的行為
    
    var mixinFilter={ template:'#row-compnent',filters:{...}}
    var mixinMounted={mounted(){...}}
    Vue.component('row.component',{
    props:['item'],
    data(){return{data:{}}},
    mixins:[]
    })
    
    

>### template
會顯示此內容但不會輸出此標籤

>### <slot>
<slot></slot>能在component中插入物件
 
若直接在定義component時在<slot>中插入文字則為預設值，之後加入的<slot>則會取代此預設值
 
<any slot="這裡"> 搭配 <slot name="這裡">
>### 將資料寫入Vue的方法

    Vue.set(target,key,value) 
    true-value false-value

>### v-model

#### v-model.lazy 
類似on changed
#### v-model.number 
將輸出值轉為數字
#### v-model.trim 
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

### 按鍵修飾符
`@keyCode` ex: `@keyup.13` 按下KeyCode相對應於13的按鈕才會觸發事件

`@keyup.enter` 按下enter時觸發事件

`@keyup.alt.enter` alt+enter要同時按才能觸發事件

### 滑鼠修飾符
`@click.right` 右鍵觸發

還有 .midlde .left



       
## Others
#### option disabled
讓選單選像無法選取

#### trim() 
清除空白鍵

>### V-for對於物件與陣列給回傳的值不一樣
陣列(a,b) in array// a=items, b=index 

物件(a,b) in obj  // a=items b=prop

>### 篩選－移除陣列中重複的選項
      vm.location = vm.location.filter(function(element, index, arr){
           return arr.indexOf(element) === index;
indexOf 會回傳第一個被找到的索引
利用此特性匹配index進行篩選

>### localStorage

       //在localStorage寫入資料
       localStorage.setItem('Data', JSON.stringify(vm.stared));
       //從localStorage取出資料
       stared:JSON.parse(localStorage.getItem('Data'))

## ES6

如果function() 誇號中無定義輸入的內容，會自動放入在arguments
       
    function hello(){
       let arg=[...arguments]
       console.log(arg) // [1,2,3,4]
       }
       hello(1,2,3,4)
或者利用其餘參數

    function hello(person,...num){
       console.log(person,...num) // "小美" ㄝ [1,2,3,4]
       }
       hello("小美",1,2,3,4)
>### 解構賦值

    let arr=[1,2,3,4]
    let[a,b,c,d]=arr 
    console.log(a,b,c,d)// a=1 b=2 c=3 d=4
    
    let a=boy
    let b=girl
    [a,b]=[b,a]
    console.log(a,b)// a=girl b=boy
    
    let str="哈囉你好"
    [a,b,c,d]=str
    console.log(a,b,c,d)// a="哈" b="囉" c="你" d="好" 
    
    let color={apple:red, sky:blue ,egg:white}
    let {apple:blood}=color
    console.log(blood)

>### 輸出li技巧
    
    <div id="app"></div>
    let newUl=`
    <ul>
      ${people.map(person=>`<li>我叫${person.name}</li>`).join("")}
    </ul>`
    $("#app").html(newUl)
    
>### .every .some

#### .every
需所有結果符合才回傳true

#### .some
部分結果符合即回傳true
    
>### reduce

    let num=people.reduce(function(prev,item,index){},0)// 0 為起始值,prev的第一個值
    
