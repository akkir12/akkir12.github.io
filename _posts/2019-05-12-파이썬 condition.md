---
layout: article

title: 파이썬 조건

tags: python

sidebar:

  nav: layout

mathjax: false
---

# 파이썬 조건 및 반복

## 조건

파이썬의 if는 `if 조건:` 으로  씁니다.

```python
x = int(input("Please enter an integer: "))

if x < 0:
    x = 0
    print('Negative changed to zero')
elif x == 0:
    print('Zero')
elif x == 1:
    print('Single')
else:
    print('More')
```

- `elif 조건:`  : if가 아니면 실행(optional)
- `else 조건:`  : if,elif 가 아니면 실행(optional)



## 반복

### while

파이썬의 while은 `while 조건:` 으로 씁니다.

```python
while True: #무한루프
```

### for

파이썬의 for는 c나 java와 다르게 임의의 [sequence](https://akkir12.github.io/2019/05/11/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88.html ) 의 항목을 그 시퀀스에 들어있는 순서대로 iteration 합니다. 파이썬의 for는 `for item in sequence:`  의 형태로 사용합니다.

```python
words = ['cat', 'window', 'defenestrate']
for w in words:
    print(w, len(w))
# cat 3
# window 6
# defenestrate 12
```

#### for의 여러 사용법

- for에서 iterate하는 sequence를 수정할 필요가 있을때

  ```python
  for w in words[:]:  # Loop over a slice copy of the entire list.
      if len(w) > 6:
          words.insert(0, w)
  ```

  words의 복사본인 words[:] 를 사용하여 무한루프를 방지

   

- dictionary를 루핑할때 items()로 키와 값을 동시에 얻기

    ```python
    knights = {'gallahad': 'the pure', 'robin': 'the brave'}
    for k, v in knights.items():
        print(k, v)
    ```

- `enumerate()` 함수를 이용하면 위치 인덱스와 값을 동시에 얻을 수 있습니다.

  ```python
  for i, v in enumerate(['tic', 'tac', 'toe']):
      print(i, v)
  ```
  

- 두개 이상의 sequence를 동시에 루핑하려면, `zip()` 함수를 이용하세요

    ```python
    questions = ['name', 'quest', 'favorite color']
    answers = ['lancelot', 'the holy grail', 'blue']
    for q, a in zip(questions, answers):
        print('What is your {0}?  It is {1}.'.format(q, a))
    ```

## break, continue, else

- `break` : 루프에서 탈출
- `continue` : 다음 이터레이션으로 넘어가기
- `else` : 루프가 완전히 다 돌고 난뒤 출력.