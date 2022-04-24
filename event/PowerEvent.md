<h1 align="center">PowerEvent()</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## 개요
봇의 전원과 관련된 이벤트입니다.

## Event
### `boton`
봇의 전원이 켜질때 발생하는 이벤트입니다.
#### example
```javascript
client.on('boton', (data) => {
    console.log('bot on!');
    console.log(data.target);
    if(data.target == 'script') {
        console.log('name: ' + data.reason.name + ' line: ' + data.reason.line);
    }
})
```

### `botoff`
봇의 전원이 꺼질때 발생하는 이벤트입니다.
#### example
```javascript
client.on('botoff', (data) => {
    console.log('bot off!');
    console.log(data.target);
    if(data.target == 'script') {
        console.log('name: ' + data.reason.name + ' line: ' + data.reason.line);
    }
})
```
## 속성
### target
이벤트 발생 원인에 대한 정보를 담고있습니다.
|target|설명|
|------|-----------------------------|
|globalSwitch|사용자가 봇 앱 전원 조작|
|powerSwitch|사용자가 스크립트 전원 조작|
|script|오류또는 API 호출로 전원 조작|

### detail
`target`이 `script`일 때 존재하며 좀 더 상세한 이유를 담고있습니다.

#### line
해당 이벤트가 발생한 스크립트 줄을 담고있습니다.

#### name
해당 이벤트가 발생한 스크립트 이름을 담고있습니다.

### reason
|reason|설명|
|------|---|
|runtimeError|스크립트 오류로 인한 스크립트 종료|
|compileError|스크립트 컴파일시 오류로 인한 스크립트 종료. 마지막으로 컴파일에 성공한 Context의 listener가 호출|
|API|봇앱에 내장된 API로 전원 조작|

## 참고
* [Event](/event/Event.md) 클래스
