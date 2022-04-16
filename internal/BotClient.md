<h1 align="center">BotClient</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## [BotClient](https://github.com/SkyLineLab/kapi/blob/main/internal/BotClient.md) on(String event, Function callback)
이벤트 리스너를 등록합니다. 이벤트 명은 Event를 참고해주세요
### example
```javascript
client.on('message', (data) => {
    
});
```

## [BotClient](https://github.com/SkyLineLab/kapi/blob/main/internal/BotClient.md) addListener(String event, Function callback)
이벤트 리스너를 등록합니다. 이벤트 명은 Event를 참고해주세요
### example
```javascript
client.addListener('message', (data) => {
    
});
```

## [BotClient](https://github.com/SkyLineLab/kapi/blob/main/internal/BotClient.md) off(String event)
이벤트 리스너를 해제합니다.
### example
```javascript
client.off('message');
```

## `Boolean` emit(String event, Object... args)
등록한 이벤트를 호출합니다.
### example
```javascript
client.addListener('plus', (a, b) => {
    console.log(a + b);
});

client.emit('plus', 2, 3); // -> 5
```