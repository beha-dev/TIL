# Python 정리

- 2개 이상의 입력값을 한번에 입력하기
```
a, b = map(int, input().split())
```
- 반복문 안에서 입력값 입력하기
```
import sys

while True:
    a, b = map(int, sys.stdin.readline().split())
```
- 반복문
```
# 특정 숫자까지 반복(0부터 n까지)
for i in range(n):

# 특정 숫자부터 특정 숫자까지 반복
for i in range(1, 10):

# 문자열의 길이만큼 반복
for i in range(len(s)):
```
- 출력하기
```
# d(digit 숫자)
print("Case #%d: %d" %(i+1, a+b))

# .format
print("{:.3f}".format((over_score_list_len/count)*100)+"%")

# 줄바꿈 없이 출력하기
print("s", end='')
```
- dictonary
```
# 선언
dn = {}

# 키, 값 활용하기
for key, value in dn.tems():
```
- 문자열
```
# 단어 중 일부만 자르기
s[0:4]

# 문자 -> 아스키 코드
ord(s)
```
- 최빈값 구하기
```
# collections 모듈의 Counter 클래스 - 리스트나 튜플에서 각 데이터가 등장한 횟수를 사전 형식으로 반환
from collections import Counter

num_list = []
num_count = Counter(num_list).most_common()
```