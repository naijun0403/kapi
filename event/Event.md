<h1 align="center">Event</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## 개요

모든 `Event`로 이름이 끝나는 클래스가 상속하는 Event클래스입니다.

## example

```javascript
const customEvent = new Event('myEvent', {
    data: {
        hey: 'this is my custom event!'
    },
    scope: 'globalTrusted'
});
// 이벤트의 이름은 대소문자를 구분하지 않음
client.addListener('myevent', (event) => {
    event.isTrusted //false
    event.data.hey //this is my custom event!
});
client.dispatchEvent(customEvent);
```

## 생성자

### Event: `function(type: string, config: object)`

`type`라는 이름을 가지는 Event를 생성합니다.

`config`의 제외한 값들은 속성의 값을 지정합니다.

다만 속성의 값을 지정하는데 쓰인 값들은 제거됩니다.

## 속성

## preventDefault: `function()`

이벤트가 취소 가능한 경우 더 이상의 이벤트 리스너 호출을 중지합니다.

이미 호출된 이벤트 리스너의 작업은 취소하거나 중지하지 않습니다.

### defaultPrevented: `boolean`

이벤트가 취소될 수 있는지 여부를 나타냅니다.

기본값은 `true`입니다.

### timeStamp: `const number`

이벤트가 생성된 시간을 타임스템프로 담고있습니다.

### type: `const string`

대소문자를 구분하지 않는 이벤트의 이름입니다.

### scope: `string`

이벤트를 전파하는 범위입니다.

기본값은 `scope`입니다.

| 이름            | 설명                            |
|:------------- |:----------------------------- |
| global        | 모든 프로젝트의 이벤트 리스너 호출           |
| scope         | 현재 프로젝트의 이벤트 리스너 호출           |
| trusted       | 컴파일시에 등록된 현재 프로젝트의 이벤트 리스너 호출 |
| globalTrusted | 컴파일시에 등록된 모든 프로젝트의 이벤트 리스너 호출 |

### isTrusted: `const boolean`

해당 이벤트를 봇 앱 내부에서 직접 생성한 경우 `true`, 기타 방법으로 생성한 경우 `false`입니다.
