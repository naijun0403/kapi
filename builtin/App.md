<h1 align="center">App</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## getContext: `function(): android.context.Context`

MainActivity의 Context를 반환합니다.

### example

```javascript
App.getContext(); // -> MainActivity Context

// but you can use this way

App.context;
```