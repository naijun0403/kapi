<h1 align="center">BotProject</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## getClient: `function(): BotClient`

해당 프로젝트의 BotClient를 반환합니다.

### example

```javascript
const client = BotProject.getClient();

// or

const client = BotProject.client;
```

## getAllProjectNames: `function(): string[]`

모든 프로젝트 이름을 들고옵니다.

### example

```javascript
BotProject.getAllProjectNames(); // -> ["test"]
```

## getCurrentProjectId: `function(): number`

프로젝트 아이디를 들고옵니다.

### example

```javascript
BotProject.getCurrentProjectId(); // -> 0
```

## getScriptContext: `function(): org.graalvm.polyglot.Context`

해당 프로젝트의 GraalVM Context를 들고옵니다

> **Warning**: 라이노 엔진의 경우 `org.mozilla.javascript.Context`를 반환합니다.

### example

```javascript
BotProject.getScriptContext();

// or

BotProject.scriptContext;
```

## on: `function(): boolean`

해당 프로젝트의 전원을 킵니다.

### example

```javascript
BotProject.on(); // -> true
```

## off(): `function(): boolean`

해당 프로젝트의 전원을 끕니다.

### example

```javascript
BotProject.off(); // -> true
```

## compile(): `function(): boolean`

해당 프로젝트를 재 컴파일합니다.

### example

```javascript
BotProject.compile(); // -> true
```