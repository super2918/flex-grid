# Grid 

### ◾️ Grid 용어
* grid container - display: grid 속성을 적용하고, grid의 전체 영역이다.
* grid item - grid 컨테이너의 자식요소를 말한다. 
* grid cell - grid 한 칸을 말한는데, gird 한칸에 들어가는 '가상이 칸(틀)이라고 한다.
* grid line - grid 셀을 구분하는 선을 말한다.
* grid number - grid 라인의 각 번호를 말한다.
* grid gap - grid 셀 사이의 간격을 말한다.
* grid area - grid 라인으로 둘러싸인 사각형 영역으로, 그리드 셀의 집합을 말한다.

### ◾️ Grid 속성
* 컨테이너에 적용하는 속성
* 아이템에 적용하는 속성

### ◾️ display: grid
```css
 .container {
   display: grid;
   display: line-grid;
 }
```

### ◾️ grid-template-rows(행 배치), gird-template-columns(열 배치)

```css
 .container {
   display: grid;
   /* repeat(4, 1fr 2fr 100px auto) */
   grid-template-columns: repeat(3, 1fr); /* 1: 1: 1 비율인 3개의 column을 만든다. */
   grid-template-rows: repeat(3, 1fr)
 }
```

### ◾️ minmax

```css
 .container {
   display: grid;
   grid-template-rows: repeat(3, minmax(100px, auto)); /* 최소한 100px, 최대는 자동(auto) 알아서 늘어나는 것을 말한다.  */
   grid-template-columns: repeat(auto-fill, minmax(20%, auto));
   grid-template-columns: repeat(auto-fit, minmax(100px, auto));

   /*
    auto-fill & auto-fit 
    column의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채운다.
    auto-fill과 auto-fit은 너비를 넘치는 아이템 갯수면 상관은 없지만 셀이 너비 보다 적게될 경우 차이가 있다.
    auto-fill은 공간이 남게 되고 
    auto-fit은 넘칠 경우는 똑같지만 fit은 남은 공간을 꽉 채운다. 
   */
 }

```
### ◾️ row-gap, column-gap

```css
.container {
  display: gird;
  grid-gap: 20px; /* 구 버전 호횐을 위하여 */
  gap: 20px;
  row-gap: 20px; 
  column-gap: 20px;
} 

/*
  익스에서는 간격은 다른 방법으로 고민을 해야 한다. 공백용 셀, 또는 margin으로 해결을 생각해야 한다.
*/

```

### ◾️ grid-auto-rows, grid-auto-columns

```css
.container {
  display: gird;
  grid-auto-rows: minmax(100px, auto);

} 

/*
개수를 미리 알 수 없는 경우면 몇개 인지 정하지 않아도 자동으로 될 때, auto로 되기 때문에 repeat를 써주지 않아도 된다.
미리 셋팅을 하고 후에 생기는 컨텐츠는 알아서 처리가되길 원하는 경우 사용한다.
*/
```


### ◾️ grid-column

```css
  .container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: minmax(100px, auto);
    gap: 1rem;
  }

  .grid-item:nth-child(1) {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 4;
    background: blue;
  }

  .grid-item:nth-child(4) {
    grid-column: 3; /* 기본은 한칸이기 때문에 한 칸일 경우는 뒤에 생략이 가능하다.*/
    grid-row: 3 / 5;
    background: red;
  }

  .grid-item:nth-child(7) {
    grid-column: 1 / span 3; /* 3칸을 채워라 */
    background: blueviolet;
  }


```
### ◾️ grid-template-colums 

```html
  <div class="grid-container">
    <div class="header grid-item">Header</div>
    <div class="sidebar-a grid-item">SideBar A</div>
    <div class="sidebar-b grid-item">SideBar B</div>
    <div class="main-content grid-item">Main</div>
    <div class="footer grid-item">Footer</div>
  </div>
```

```css
.grid-container {
      display: grid;
      gap: 1rem;
      grid-template-columns: 1fr 3fr 1fr;
      /* 각각의 영역에 매칭을 한다. grid-area 속성으로 이름을 지정해주면 된다. 익스에서는 지원을 해주는 속성이 아니기 때문에 숫자, span을 해서 작성을 해야한다. */
      grid-template-areas: 
      ". header header"
      "a main b"
      ". . ."
      /* "none none none" 빈칸일  경우, none 또는 .을 사용한다. */
      "footer footer footer"
    }
    
    .header {  grid-area: header; }
    .sidebar-a { grid-area: a; }
    .main-content { grid-area: main; }
    .sidebar-b { grid-area: b; }
    .footer { grid-area: footer; }
    
```






### ℹ️ Reference
> https://studiomeal.com/archives/533