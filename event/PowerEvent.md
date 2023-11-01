<h1 align="center">PowerEvent()</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## 개요

봇의 전원과 관련된 이벤트입니다.

## Event

### `bot_on`

봇의 전원이 켜질때 발생하는 이벤트입니다.

#### example

```javascript
client.on('bot_on', (data) => {
    console.log('bot on!');
    console.log(data.target);
    if(data.target == 'script') {
        console.log('name: ' + data.detail.name + ' line: ' + data.detail.line);
    }
})
```

### `bot_off`

봇의 전원이 꺼질때 발생하는 이벤트입니다.

#### example

```javascript
client.on('bot_off', (data) => {
    console.log('bot off!');
    console.log(data.target);
    if(data.target == 'script') {
        console.log('name: ' + data.detail.name + ' line: ' + data.detail.line);
    }
})
```

## 속성

### target: `string`

이벤트 발생 원인에 대한 정보를 담고있습니다.

| target       | 설명                  |
|--------------|---------------------|
| globalSwitch | 사용자가 봇 앱 전원 조작      |
| powerSwitch  | 사용자가 스크립트 전원 조작     |
| script       | 오류또는 API 호출로 전원 조작  |

### detail: `object`

`target`이 `script`일 때 존재하며 좀 더 상세한 이유를 담고있습니다.

#### line: `number`

해당 이벤트가 발생한 스크립트 줄을 담고있습니다.

`BOT_ON`이벤트이거나, 오류가 나서 꺼진경우가 아니라면 `null`이 반환됩니다.

#### name: `string`

해당 이벤트가 발생한 스크립트 이름을 담고있습니다.

### reason: `string`

| reason       | 설명                                                             |
|--------------|----------------------------------------------------------------|
| runtimeError | 스크립트 오류로 인한 스크립트 종료                                            |
| compileError | 스크립트 컴파일시 오류로 인한 스크립트 종료. 마지막으로 컴파일에 성공한 Context의 listener가 호출 |
| API          | 봇앱에 내장된 API로 전원 조작                                             |

## 참고

* [Event](/event/Event.md) 클래스
