# [CSS] Flex(Flexible Box)

###  ◾️ Flex란?
Flex는 뷰포트나 요소의 크기가 명확하지 않고, 동적으로 변하는 요소들을 효율적으로 배치, 정렬 등 유연하게 조절할 수 있는 방법을 제공하는 CSS이다.

Flex의 구조는 부모요소 Flex Container 와 자식요소 Flex Item로 구성되어있다.
container는 flex가 영향을 받는 전체 공간이고, 설정된 속성에 따라서 item들이 배치되는 것이다.

### ◾️ display

```css
  // display 속성
 .flex-container {
  display: flex;
  display: inline-flex;  
 }
```

### ◾️  Flex-direction

```css
 .flex-container {
    display: flex;
    flex-direction: row;
    flex-direction: row-reverse;
    flex-direction: column;
    flex-direction: column-reverse;
 }
```

### ℹ️ 브라우저별 지원 확인
> https://caniuse.com/?search=CSS%20Flexible%20Box

### ℹ️ Reference
> https://studiomeal.com/archives/197
