## [추가영상] forEach, map, filter, reduce 메서드 작동원리

### _forEach_

```js
// forEach
// function forEach(predicate, thisArg) {}
// predicate <- 함수
// thisArg는 생략 가능

const arr = [10, 11, 12, 13, 14, 15];

// for 반복문 대체용
// 인자로 (콜백) 함수 넘김
// 콜백 함수 this -> forEach() 2번째 인자값
arr.forEach(
  function (value, index) {
    console.log(value, index, this);
  },
  [1, 2]
);
```

### _map_

```js
// map
// function map(predicate, thisArg) {}

const arr = [10, 11, 12, 13, 14, 15];

// 새로운 배열 생성 (원본 배열과 같은 길이)
// 새로운 배열 길이는 원본 배열 길이와 같음!!!
// 누락된 곳은 undefined로 채워짐
let answer = arr.map(
  function (value, index) {
    if (value % 2 === 0) return value;
  },
  [1, 2]
);
console.log(answer);
```

### _filter_

```js
// filter
// function filter(predicate, thisArg) {}

const arr = [10, 11, 12, 13, 14, 15];

// 새로운 배열 생성
// 하지만 원본 배열과 길이 동일할 필요 없음
// 콜백함수가 true를 return 했을 때의 그 요소만 새로운 배열의 원소로 저장
// 원본 배열 요소들 중에서만 특정 값 필터링 (map 처럼 새로운 요소 값 생성 X)
let answer = arr.filter(
  function (value, index) {
    return value % 2 === 0;
  },
  [1, 2]
);
console.log(answer);
```

### _reduce_

```js
// reduce
// function reduce(predicate, val) {}

const arr = [10, 11, 12, 13, 14, 15];

// 배열을 생성해서 return 하는 것이 아니라
// 값을 생성해서 return 함
// 콜백함수 return 값이 콜백함수의 첫번째 매개값으로 계속 누적되서 전달됨
// 콜백함수 두번째 매개값은 원본 배열의 요소 값
// reduce 함수의 두번째 인자값은 초기값임 (acc 변수의 초기값)
// 원본 배열 합 구할때 보통 사용
let answer = arr.reduce(function (acc, val) {
  return acc + val;
}, 0);
console.log(answer);
```

#

### [Note]

- 위 4개 함수 모두 고차 함수 <br/>
  자신의 매개변수에 함수 전달 받음 (콜백 함수 받음)
- 콜백함수는 항상 반복 호출됨
