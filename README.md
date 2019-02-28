# CSS

CSS (Flexbox, Grid, PostCSS, CSSNext)

### CSS Flex

- [x] CSS Flex Basics
- [x] Main Axis and Cross Axis
- [x] Flex Direction
- [x] Flex Wrap
- [x] Align Self

### CSS Grid

- [x] CSS Grid Basics ( Row, columns and gaps)
- [x] Auto columns, auto rows
- [x] Template Areas
- [x] fr unit, repeat
- [x] minmax, max-content, min-content
- [x] auto-fill, auto-fit
- [x] Justify Content, Align Content and Place Content
- [ ] Justify Items, Align Items and Place Items
- [ ] Grid Column, Column Start and End
- [ ] Line Naming
- [ ] Grid Row, Row Start and End
- [ ] Grid Area
- [ ] Justify, Align, Place Self

### Using CSS4

- [ ] Installing Parcel
- [ ] Configuring PostCSS
- [ ] Testing

### CSS4 Awesomeness

- [ ] :matches , :not
- [ ] CSS Variables
- [ ] @custom-selector
- [ ] @custom-media
- [ ] Media Query Ranges
- [ ] color-mod, gray(), system-ui
- [ ] Nesting Rules

### Conclusions

- [ ] CSS Grid Kiss
- [ ] Practice Flexbox
- [ ] Practice Grid

### Exercices








##FLEX

### Flex의 기본 개념 두가지
    Flex-container와 Flex-item

###MEMO   
    첫번째, 상위 태그를 flex container로 만든다.
    => display:flex;
    두번째, flex-items은 픽셀값을줘도 반응형에선 무시된다.
    

### display:flex
    display:flex를 준 순간부터 이미 방향은 row로 결정되어있다.
    => flex-direction: ( column / row )으로 바꿀 수 있다. => cross axis <=> main axis가 서로 뒤바뀜
            
### justify-content
    justify-content: space-between;
    /*
    flex-end : 끝쪽에 정렬
    flex-start : 처음부분에 정렬
    space-around : item 주변에 간격을 동일하게 준다.
    space-between : item 주변에 간격을 동일하게준다 . (but left,right(벽과 맞닿은부분은 적용되지않는다.))
    */
###align-items
    align-items: center;
    /*
    - cross axis에 있는 아이템을 움직이려면, align-items
    - main axix에 있는 아이템을 움직이려면 justify-content
     */
     
###flex-wrap
    Flex는 아이템들끼리 공간이 부족할때는 기본적으로 찌그러진다.
    어쩔때는 좋지만 별로 좋지않을때도 있다..
    케바케!
    이럴때 사용하는것이 flex-wrap
    - flex-wrap: wrap -> 찌그러지지않고, 밑으로 내려간다 ( inline-block효과? )
    - flex-wrap : nowrap -> 디폴트값
    
    정리 : 아이템들 사이에 더이상 공간이 없을 때 flexbox가 해야할 행동들을 정의할 수 있다.

###flex-direction
    float : left, right의 기능..?
    flex-direction : row, row-reverse, column, column-reverse 등이 있다.
    겁나좋은데..?
    
    
### align-self
    father(박스의 상위태그)에게 주는 옵션이 아닌, box와 같은 아이템들에 직접 옵션을 주는놈
    => flex-container 대신에 flex-item들에게 주는 것.
    
    
    
    
    
    
    
##GRID

###grid-template-rows
    가로
    ex: grid-template-rows : 12px 40px;
    => 가로로 각각 12px, 40px 블록이 2개
    
###grid-template-columns
    세로
    ex: grid-template-columns : 30px 30px; 
    => 세로로 각각 30px 블록이 2개

    
###grid-gap
    ex: grid-gap:10px 그리드 사이사이 간격값
    
###grid-auto-columns,rows
    나머지 요소값들에 자동으로 적용.


###grid-template-areas grid-area 
    
    상위 태그에 스케치를 하고....
    grid-template-areas:
            "header header header"
            "content content sidebar"
            "content content sidebar"
            "footer footer footer"
    하위 박스태그에 영역을 지정해준다.
    grid-area:footer; 
    
    
### fr : fraction
    .father{
        display:grid;
        grid-auto-rows: 200px;
        grid-gap: 5px;
        /* fr : fraction */
        grid-template-columns: 2fr 1fr 2fr 1fr;
        -> 상대적으로 다른놈들이 조정됨..
    }
    
    grid-template-columns: repeat(4, 1fr);
    1fr 의 너비로 4번 반복한다 ( 4개의 그리드? 영역?을 만든다)
    
### grid-template-columns
    grid-template-columns: minmax(400px, 2fr) repeat(3, 1fr);
    
    minmax( 최소값 , 보통값 )
    min-content : 박스안에 내용이 있다면 최소한으로줄여서 (너비를) 보여줌
    max-content : 박스안에 내용만큼 너비를 늘려줌 (타이틀만들때유용하겠네!)
            
### auto-fill, auto-fit
    auto-fit : 가능한 많이 채워 넣어라. 양쪽에 딱 달라붙는다.
    => grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); 
    => autofit을 쓸 때, minmax를 사용하느냐 안하냐에 따라 많은 차이가 있다.
    ghost grid를 만들지 않고 content를 받아와서 width100%만큼 펼쳐준다.
    
    auto-fill : 공간을 미리 배정해둔 grid를 만든 뒤에 , 해당하는  cell이 입력되는 방식으로 작동
    => grid-template-columns: repeat(auto-fill, minmax(50px, 1fr));
    일단 ghost grid를 만들고 가능한 많은 cell로 container를 꽉 채우는 놈.. cell은 비어있을 수 있다. (box가 없으면)
    
    
### align-content
    align-content : center;
    height: 100vh 일때 상하로 왔다갔다.. center, start, end ...
### justify-content
    하위 박스 전부 ! 통째로 ! {}좌우로 왔다갔다 .. center, start, end...
    justify-content: center;
### place-content
    place-content:center(상하 align-content) end(좌우 justify-content);