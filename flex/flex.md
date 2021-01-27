# [CSS] Flex(Flexible Box)

###  ◾️ Flex란?
Flex는 뷰포트나 요소의 크기가 명확하지 않고, 동적으로 변하는 요소들을 효율적으로 배치, 정렬 등 유연하게 조절할 수 있는 방법을 제공하는 CSS이다.

Flex의 구조는 부모요소 Flex Container 와 자식요소 Flex Item로 구성되어있다.
container는 flex가 영향을 받는 전체 공간이고, 설정된 속성에 따라서 item들이 배치되는 것이다.

### ◾️ display

```css
 .flex-container {
    display: flex;
    display: inline-flex;  
 }
```

### ◾️ Flex-direction

```css
 .flex-container {
    display: flex;
    flex-direction: row;
    flex-direction: row-reverse;
    flex-direction: column;
    flex-direction: column-reverse;
 }
```

### ◾️ Flex-wrap

```css
 .flex-container {
    display: flex;
    flex-wrap: nowrap;
    flex-wrap: wrap;
    flex-wrap: wrap-reverse;
 }
```

### ◾️ Justify-content

```css
 .flex-container {
    display: flex;
    justify-content: flex-start;
    justify-content: flex-end;
    justify-content: center;
    justify-content: space-between;
    justify-content: space-around;
    justify-content: space-evenly;
 }
```
### ◾️ align-items 

```css
 .flex-container {
    align-items: stretch;
    align-items: flex-start;
    align-items: flex-end;
    align-items: center;
    align-items: baseline;
 }
```

### ◾️ align-content

```css
 .flex-container {
    align-content: stretch;
    align-content: flex-start;
    align-content: flex-end;
    align-content: center;
    align-content: space-between;
    align-content: space-around;
    align-content: space-evenly;
 }
```

### ◾️ flex-grow

```css
 .flex-item {
    flex-grow: 0; // 초기값
 }
```

### ◾️ flex-shrink

```css
 .flex-item {
    flex-grow: 1; // 초기값
 }
```

### ◾️ flex

```css
 .flex-item {
   /* Keyword values */
   flex: auto;
   flex: initial;
   flex: none;

   /* One value, unitless number: flex-grow */
   flex: 2;

   /* One value, length or percentage: flex-basis */
   flex: 10em;
   flex: 30%;

   /* Two values: flex-grow | flex-basis */
   flex: 1 30px;

   /* Two values: flex-grow | flex-shrink */
   flex: 2 2;

   /* Three values: flex-grow | flex-shrink | flex-basis */
   flex: 2 2 10%;
 }
```

### ◾️ align-self

```css
 .flex-container {
   display: flex;
   height: 100vh;
   align-items: center;
 }

 .flex-item {
   align-self: auto;
   align-self: stretch;
   align-self: flex-start;
   align-self: flex-end;
   align-self: center;
   align-self: baseline;
 }
```

### ◾️ oder
- 접근성을 위함은 아니니 되도록 사용은 안함

```css
 .flex-container {
   display: flex;
 }

 .flex-item:nth-child(1) {
   order: 3;
  }
.flex-item:nth-child(2) {
   order: 1;
 }
.flex-item:nth-child(3) {
   order: 2;
 }
```

### ◾️ z-index
- 접근성을 위함은 아니니 되도록 사용은 안함

```css
  .flex-container {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 300px;
  }
  .flex-item {
    opacity: 0.8;
  }
  .flex-item:nth-child(1) {
    transform: scale(1.5);
    z-index: 1;
  }
  .flex-item:nth-child(2) {
    transform: scale(2);
    z-index: 2;
  }
  .flex-item:nth-child(3) {
    transform: scale(2.2);
  }
```




### ℹ️ 브라우저별 지원 확인
> https://caniuse.com/?search=CSS%20Flexible%20Box

### ℹ️ Reference
> https://studiomeal.com/archives/197
