<h1 align="center">Api</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## getContext: `function(): android.context.Context`

MainActivity의 Context를 반환합니다.

### example

```javascript
Api.getContext(); // -> MainActivity Context

// but you can use this way

Api.context;
```

## compileAll: `function(): boolean`

모든 프로젝트를 재 컴파일합니다.

### example

```javascript
Api.compileAll(); // compile!
```

## canReply: `function(room: string): boolean`

세션 목록에 해당 방이 있고, 전송 가능한 상태인지 반환합니다.

### example

```javascript
// room = ["test"]
Api.canReply("test"); // -> true

Api.canReply("asd"); // -> false
```