<h1 align="center">MessageEvent</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## 개요

메세지가 올때 발생하는 이벤트입니다.

## example

```javascript
client.on('message', (data) => {
   if (data.message === '!ping') {
       data.room.send('pong!');
   } 
});
```

## 속성

## message: `string`

메세지의 내용

## sender: `object`

보낸 사람 정보

### name `string`

보낸 사람의 이름

### profileBase64: `string`

보낸 사람의 프로필 사진을 base64로 인코딩한 문자열

### profileHash: `number`

profileBase64를 `java.lang.String.hashCode()`한 값

### userHash: `string`

안드로이드 11이상 + 카카오톡 버전이 9.7.0이상 이라면 모든 환경에서 고정적인 유저아이디 해쉬값을 리턴합니다.

만일, 조건에 부합하지 못하면 다음과 같은 에러가 나옵니다.
> `Error: userHash is not available on this environment`

## room: `object`

방 정보

### name: `string`

방의 이름

### isGroupChat: `function()`[^BUG]

단체 채팅방이면 `true`, 아니라면 `false`를 반환
[^BUG]: 봇 앱의 버그로 인해 원래라면 `boolean`이 맞지만 `function`입니다.

### send: `function(message: string): Promise<boolean>`

메시지를 받은 방에 `message`라는 내용의 메시지를 전송

### sendAllRoom: `function(message: string): Promise<boolean>`

전송 가능한 모든 방에 `message`라는 내용의 메시지를 보냅니다.

### markAsRead: `function(): Promise<boolean>`

메시지를 받은 방을 읽음처리합니다.

## packageName: `string`

메시지를 감지한 앱의 패키지 이름

## chat: `android.os.Bundle`

봇 앱이 받은 알림에 있는 데이터

## 참고

- [Event](/event/Event.md) 클래스
