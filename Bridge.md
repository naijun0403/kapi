<h1 align="center">Bridge</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## `org.graalvm.polyglot.Value` getGlobalByName(String projectName)
해당 프로젝트의 `globalThis`값을 줍니다.

해당 프로젝트 명이 존재하지 않는다면 에러를 내보냅니다.
### example
```javascript
Bridge.getGlobalByName("test"); // -> [object global]

Bridge.getGlobalByName("abc"); // LinkError: Not Found Project Name: abc
```

## `org.graalvm.polyglot.Value` getGlobalById(Integer id)
해당 프로젝트의 `globalThis`값을 줍니다.

해당 프로젝트 아이디이 존재하지 않는다면 에러를 내보냅니다.
### example
```javascript
Bridge.getGlobalById(0); // -> [object global]

Bridge.getGlobalByName(1); // LinkError: Not Found Project ID: 12
```

## `Boolean` canAccessByName(String projectName)
해당 프로젝트의 접근 여부를 알려줍니다.
### example
```javascript
Bridge.canAccessByName("test"); // -> true

Bridge.canAccessByName("abc"); // -> false
```

## `Boolean` canAccessById(Integer id)
해당 프로젝트의 접근 여부를 알려줍니다.
### example
```javascript
Bridge.canAccessById(0); // -> true

Bridge.canAccessByName(1); // -> false
```