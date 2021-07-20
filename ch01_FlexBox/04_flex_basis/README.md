### flex box 
```txt
flex box 에서는 chidren 과 얘기 하지 않는다.
이게 무슨말이냐 , nth-child 구문은 듣지 않는다.

내부 요소들을 건들고 싶다면, flex-box container 를 만들면 된다.

- 항상 붙어있는 부모 가 자식의 위치를 움직일 수 있다.

-flex container 의 flex 기본 값은 row 다 (가로)
그럼 세로로 바꾸는건 ? : (justify-content) 로 바꾼다.
justify-content는 수평축에 있는 flex chidren 위치를 변경한다.
ex ) justify-contents 를 center 로 하면 무슨일이 벌어질까 ? ( children 들이 중앙으로 배치된다 ) 계산을 할 필요가 없다 browser 가 알아서 계산해준다 ( 멋진녀석 )

기본 방향이 row 면 main axis 는 가로다.
반대로 colum 이면 ? 세로다.

justify-contents, main axis
align-items cross-axis

Q ) flex container 의 기본 방향은 뭘까 ? ()=> row
direction 이 row 일때 main axis 는 어느방향일까 ? row (가로 [ horizontal])

direction 이 row 일때 cross axis 는 
어느방향일까 ? vertical

이론 정리 : justify-contents = 메인 axis
          align-items = cross axis

```
```
align-self 는 align-items 와 비슷한 일을 하는데

이말은 cross axis 다 .
align-self 는 align-item 처럼 행동하고, 
align-item 은 오직 cross axis 방향에 있는 item 을 바꾼다. 
``` 

```
row 라인 사이 공백을 줄일수 있다
사이공백을 align-content 라고 한다.
align-content 는 line 을 변경한다.
```
```
flex 가 nowrap 이면 width 가 설정되어 있어도 
쥐어짜지듯이 줄어든다.

flex-shrink 는 특정 element 만 쥐어짜질수 있게 조작할 수 있다.

flex-grow 는 box 주변의 공간을 가진다.
if (만약 공간이 남아있다면) 

flex-basis 는 element 에게 처음 크기를 준다
모든게 찌그러지거나 늘어나기 전에 flex-basis 를 설정한다.
```

```
grid flex 에서 간혹 grid 를 만들어볼려는 경우가 있을것이다.
grid 를 사용하면 더이상 바보같은 짓을 않 할 수 있다.

display: grid 만 해주면된다.
width height 크기는 각각 

ex ) 
grid-row: 100px
grid-column: 100px 를 주면 된다.
간격은 grid-gap: 10px 를 주면된다.

table 작업처럼 css 로 grid 가 먹는 땅을 지정해 줄 수 있다.
column : grid-column-start: 1;
         grid-column-end: 5;
row: grid-row-start: 2;
     grid-row-end: 4; 

이를 좀더 쉽게 해줄수 있다.
grid-column: 1 / 5;
grid-row: 2 / 4; 

이를 좀더더 쉽게 해줄수 있다.
끝부터 계산인데 마지막은 항상 -1 이다
늘어날수록 -2 .... 음수로 늘어난다.
5 by 5 행렬일때
1 / -1 == 1 / 5 와 같다.

이를 끝판왕 급으로 더 쉽게 해줄 수 있다.
바로 span 이다. span 은 시작점과 끝점을 적는것을 대신한다.

1 / -1 === span 5 .

line 에 이름을 줘서 계산을 할 수도 있다.
ex ) 
grid-template-columns: [first-line] 100px [second-line] 100px [third-line] 100px [fourth-line] 100px ;

grid-template-rows: repeat(4, 100px [sexy-line]);

[선택은 자유]
```

### fr
```
 fr 뜻은 fraction(부분) 이다.
 pixel 이나 % 같은 건데, 측정단위다.
 grid 가 100px x 100px
```

```
grid 에서 
justify-items 는 수평 ( 가로 ) 이고, 모든 grid 를 수평적으로 움직이는 거고. 
align-items 는 수직 ( 세로 ) 이다.
모든 grid 를 수직적으로 움직인다.

place-content 는 모든 사각형 다같이 함께 에 대한것이고,place-items 는 각 사각형 하나하나에 어떤 걸 적용하는지에 관한것이다.
```

```
justify-self , align-self
각 개별 child 에 요소를 추가하고싶을때다.
지름길은 
place-self 첫번째 는 수직 두번째는 수평 이다.

justify-items 는 수평으로,
align-items 는 수직으로 ,
```

```
fr 은 멋지다.
몇번째 인지 적어만 주면 끝난다.
탄력적이다.
```

```
grid 의 content 를 정렬하는 (align) 하는 방법

[ column ]
justify-content: space-around, space-evenly, space-between

[ row ]

```


```
place-content 는 place-items 와 비슷한 기능을 가지고 있다.

place-items 는 {
    각 사각형 하나하나에 어떤 걸 적용하는지에 관한것이다.
}

place-content 는 모든 사각형 다같이 함께에 대한것이다.


```