<h1 align="center">BotClient</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## on(String event, Function callback): [BotClient](/internal/BotClient.md)
이벤트 리스너를 등록합니다. 이벤트 명은 Event를 참고해주세요
### example
```javascript
client.on('message', (data) => {
    
});
```

## addListener(String event, Function callback): [BotClient](/internal/BotClient.md)
이벤트 리스너를 등록합니다. 이벤트 명은 Event를 참고해주세요
### example
```javascript
client.addListener('message', (data) => {
    
});
```

## off(String event): [BotClient](/internal/BotClient.md)
이벤트 리스너를 해제합니다.
### example
```javascript
client.off('message');
```

## dispatchEvent(String event, Object... args): `boolean`
등록한 이벤트를 호출합니다.
### example
```javascript
client.addListener('plus', (a, b) => {
    console.log(a + b);
});

client.emit('plus', 2, 3); // -> 5
```
