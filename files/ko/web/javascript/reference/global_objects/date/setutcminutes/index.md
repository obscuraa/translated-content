---
title: Date.prototype.setUTCMinutes()
slug: Web/JavaScript/Reference/Global_Objects/Date/setUTCMinutes
translation_of: Web/JavaScript/Reference/Global_Objects/Date/setUTCMinutes
browser-compat: javascript.builtins.Date.setUTCMinutes
---

{{JSRef}}

**setUTCMinutes()** 메서드는 표준시에 따라 지정된 날짜의 분을 설정합니다.

## Syntax

```js
    dateObj.setUTCMinutes(minutesValue[, secondsValue[, msValue]])
```

### Parameters

- `minutesValue`
  - : 분을 나타내는 0에서 59 사이의 정수입니다.
- `secondsValue`
  - : 선택 과목. 초를 나타내는 0에서 59 사이의 정수입니다. secondsValue 매개 변수를 지정하면 minutesValue도 지정해야합니다.
- `msValue`
  - : 선택 과목. 밀리 초를 나타내는 0에서 999 사이의 숫자입니다. msValue 매개 변수를 지정하는 경우 minutesValue 및 secondsValue도 지정해야합니다.

### Return value

1970 년 1 월 1 일 00:00:00 UTC와 업데이트 된 날짜 사이의 밀리 초 숫자입니다.

## Description

secondsValue 및 msValue 매개 변수를 지정하지 않으면 {{jsxref ( "Date.prototype.getUTCSeconds()", "getUTCSeconds()")}} 및 {{jsxref ("Date.prototype.getUTCMilliseconds","getUTCMilliseconds()")}} 메소드가 사용됩니다.

지정한 매개 변수가 예상 범위를 벗어나면 setUTCMinutes ()는 그에 따라 {{jsxref("Date")}} 객체의 날짜 정보를 업데이트하려고 시도합니다. 예를 들어 secondsValue에 100을 사용하면 분은 1 (minutesValue + 1)만큼 증가하고 40은 초 단위로 사용됩니다.

## Examples

### Using `setUTCMinutes()`

```js
var theBigDay = new Date();
theBigDay.setUTCMinutes(43);
```

## 명세

{{Specifications}}

## 브라우저 호환성

{{Compat}}

## See also

- {{jsxref("Date.prototype.getUTCMinutes()")}}
- {{jsxref("Date.prototype.setMinutes()")}}
