<h1 align="center">PowerEvent</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## 개요
봇의 전원과 관련된 이벤트입니다.

## `boton`
봇의 전원이 켜질때 발생하는 이벤트입니다.
### example
```javascript
client.on('boton', () => {
    console.log('bot on!');
})
```

## `botoff`
봇의 전원이 꺼질때 발생하는 이벤트입니다.
### example
```javascript
client.on('botoff', () => {
    console.log('bot off!');
})
```