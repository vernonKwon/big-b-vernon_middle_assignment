# 정규표현식이란

정규표현식(이하 정규식)은 문자열에서 특정 문자 조합을 찾기 위한 패턴이다.

보통 RegEx 혹은 RegExp라고도 부르며, 프로그래밍에서 문자열을 다룰 때 많이 사용된다. 정규식을 사용하면 문자열에서 특정 문자열을 찾거나, 문자열을 특정 패턴으로 변환할 수 있다.

정규식은 다양한 프로그래밍 언어에서 제공한다.

정규식을 사용하는 이유는 다양하다.

1. Data Validation

정규 표현식을 사용하면 입력된 데이터가 특정 형식에 맞는지 확인할 수 있다.
```
import re

email_pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
email = "example@example.com"

if re.match(email_pattern, email):
    print("유효한 이메일 주소입니다.")
else:
    print("유효하지 않은 이메일 주소입니다.")

```

![image](https://github.com/vernonKwon/big-b-vernon_middle_assignment/assets/29453831/77e8eae5-a994-465f-a783-0cf02551e373)


2. 문자열 찾기

웹 스크래핑, 로그 분석 등에서 원하는 문자열을 찾거나 추출하는 작업을 수행할 때 정규 표현식을 사용할 수 있다.

```
import re

text = "제 전화번호는 010-1234-5678 혹은 010-1123-3321 입니다. 연락주세요!"
phone_pattern = r'\d{3}-\d{4}-\d{4}'
phone_number = re.findall(phone_pattern, text)

print("전화번호:", phone_number)
# 전화번호: ['010-1234-5678', '010-1123-3321']
```

3. 문자열 치환
```
import re

text = "원문에서 이메일 주소를 모두 *** 로 바꾸려고 합니다. 이메일 주소는 example@example.com 입니다."

email_pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
masked_text = re.sub(email_pattern, '***', text)

print(masked_text)
# 원문에서 이메일 주소를 모두 *** 로 바꾸려고 합니다. 이메일 주소는 *** 입니다.
```

정규식을 사용하는 케이스는 다양하지만 특히 Validation 성격의 동작에서 많이 쓰인다. 

was middleware 에서 값에 대한 검증을 진행하면 비즈니스 로직 작성시 예외 처리에 대한 부담이 줄어들고 비즈니스 로직에 대한 집중이 가능하기 때문이다.

