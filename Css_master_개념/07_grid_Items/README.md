### justify-items
```css
  grid-template-columns: repeat(4, 100px);
  grid-template-rows: repeat(4, 100px);

  100 픽셀 만큼 4by4 까지는 해당 Css 가 적용이 되지만 , 
  내가 가진 정보 보다 더많은 element 를 가지게 되면, 적용이 안된다.
  그럴땐 grid-auto-rows 를 작성해주면 된다.

  grid-auto-flow 는 auto-rows 와 비슷하나 , column 으로 가게 되고 element 의 숫자가 바뀌게 된다.
  세로로 _-> 이건 마치 flex-direction: column 과 같다.
```
