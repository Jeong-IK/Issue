![](https://velog.velcdn.com/images/han1368/post/0bce5971-6192-4ad1-a2d7-534f3cca79fa/image.png)

## 발생한 이유?
React 프로젝트에 처음으로 ESLint를 적용하던 중 생긴 오류로 화살표 함수로 생성된 함수형 컴포넌트에 발생한 오류이다.

## 해결과정
eslint의 공식문서를 보던 중 eslint-plugin-react의 rules가 없어 [github페이지](https://github.com/jsx-eslint/eslint-plugin-react)에서 function의 rules를 찾아보던 중 [react/function-component-definition](https://github.com/jsx-eslint/eslint-plugin-react/blob/master/docs/rules/function-component-definition.md)을 찾게 되었다. 리액트의 함수형 컴포넌트를 정의하는 방식을 지정하는 rule이며 아래와 같이 속성을 넣을 수 있다.
```json
"react/function-component-definition": 
[<enabled>,
{"namedComponents": "function-declaration" | "function-expression" | "arrow-function" | Array<"function-declaration" | "function-expression" | "arrow-function">,
"unnamedComponents": "function-expression" | "arrow-function" | Array<"function-expression" | "arrow-function">
}]
```

## 해결법
### eslintrc 설정파일의 rules에 react/function-component-definition을 추가하여 함수형 컴포넌트의 정의 방식을 지정해주면 해결된다.
![](https://velog.velcdn.com/images/han1368/post/680c5b04-2109-4a77-b454-324e716b826b/image.png)


