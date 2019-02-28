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
- [ ] Auto columns, auto rows
- [ ] Template Areas
- [ ] fr unit, repeat
- [ ] minmax, max-content, min-content
- [ ] auto-fill, auto-fit
- [ ] Justify Content, Align Content and Place Content
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
               