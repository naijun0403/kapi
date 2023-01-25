<h1 align="center">BotClient</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## channelList: `ChannelList`

현재까지 알림이 온 채널 목록을 반환합니다.

## on: `function(event: string, callback: function): BotClient`

이벤트 리스너를 등록합니다. 이벤트 명은 Event를 참고해주세요

### example

```javascript
client.on('message', (data) => {

});
```

## addListener: `function(event: string, callback: function): BotClient`

이벤트 리스너를 등록합니다. 이벤트 명은 [Event](/event/Event.md)를 참고해주세요

### example

```javascript
client.addListener('message', (data) => {

});
```

## off: `function(event: string): BotClient`

이벤트 리스너를 해제합니다.

### example

```javascript
client.off('message');
```

## dispatchEvent: `function(event: Event)`

등록한 이벤트를 호출합니다.

### example

```javascript
client.addListener('plus', (data) => {
    console.log(data.a + data.b); // -> 5
});
const event = new Event('plus', {
    a: 1,
    b: 4
});
client.dispatchEvent(event);
```
