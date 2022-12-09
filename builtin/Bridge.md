<h1 align="center">Bridge</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## getGlobalByName: `function(projectName:string): org.graalvm.polyglot.Value`

해당 프로젝트의 `globalThis`값을 줍니다.

해당 프로젝트 명이 존재하지 않는다면 에러를 내보냅니다.

### example

```javascript
Bridge.getGlobalByName("test"); // -> [object global]

Bridge.getGlobalByName("abc"); // LinkError: Not Found Project Name: abc
```

## canAccessByName: `function(projectName: string): boolean`

해당 프로젝트의 접근 여부를 알려줍니다.

### example

```javascript
Bridge.canAccessByName("test"); // -> true

Bridge.canAccessByName("abc"); // -> false
```