## [보충] 내장함수로 최솟값, 최댓값 구하기

### _문제 풀이_

- Math 객체 이용
  - min/max 함수
  - 인자값으로 배열 같은 객체를 넘기면 안됨 <br/>
    (인자로만 넘어감)

1. Spread Operator `...` 이용! <br/>
   - Math.max/min(arr[0], arr[1], arr[2], ... arr[n])
2. apply 메서드 이용 <br/>
   - 전개 연산자 사용 안할 시
   - 두번째 인자에 배열 넘기기 (첫번째 인자는 this로 컨트롤 할 수 있는 객체)
   - Math.max/min.apply(null, arr)
