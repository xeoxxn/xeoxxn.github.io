---
layout: post
title: "MarkDown_Practice"
info: "MarkDown_Practice in Eureka"
tech: "MarkDown"
type: Kookmin
comments: true
---

# 마크다운 연습하기

# 1. 마크다운에 관하여

## 1.1. 마크다운이란?

## 1.2. 마크다운의 장-단점

### 1.2.1. 장점

```
1. 간결하다.
2. 별도의 도구없이 작성 가능하다.
3. 다양한 형태로 변환이 가능하다.
4. 텍스트(Text)로 저장되기 때문에 용량이 적어 보관이 용이하다.
5. 텍스트파일이기 때문에 버전관리시스템을 이용하여 변경이력을 관리할 수 있다.
6. 지원하는 프로그램과 플랫폼이 다양하다.
```

# 2. 마크다운 사용법(문법)

## 2.1. 헤더 (Headers)

- 큰 제목: 문서 제목

```
This is an H1
=============
```

# This is an H1

- 작은 제목: 문서 부제목

```
This is an H2
-------------
```

## This is an H2

- 글머리: 1~6까지만 지원

```
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
```

# This is a H1

## This is a H2

### This is a H3

#### This is a H4

##### This is a H5

###### This is a H6

####### This is a H7 (지원하지 않음)

## 2.2. BlockQuote

이메일에서 사용하는 `>` 블럭 인용 문자를 이용한다.

```
> This is a first blockquote.
>> This is a second blockquote.
>>> This is a third blockquote.
```

> This is a first blockquote.
>
> > This is a second blockquote.
> >
> > > This is a third blockquote.
> > > 이 안에서는 다른 마크다운 요소를 포함할 수 있다.
> > > This is a H3
>
> - List
>   ```
>   code
>   ```

## 2.3 목록

### ● 순서 있는 목록 (번호)

순서있는 목록은 숫자와 점을 사용한다.

```
1. 첫 번째
2. 두 번째
3. 세 번째
```

1. 첫 번째
2. 두 번째
3. 세 번째

#### 현재까지는 어떤 번호를 입력해도 순서는 내림차순으로 정의된다.

```
1. 첫 번째
3. 세 번째
2. 두 번째
```

1. 첫 번째
2. 세 번째
3. 두 번째

딱히 개선될 것 같지는 않다.

### ● 순서없는 목록(글머리 기호: `*`, `+`, `-` 지원)

```
* 빨강
  *녹색
    *파랑
+ 빨강
  + 녹색
    + 파랑
-빨강
  -녹색
    -파랑
```

- 빨강
  - 녹색
    - 파랑

* 빨강
  - 녹색
    - 파랑

- 빨강
  - 녹색 - 파랑
    혼합해서 사용하는 것도 가능하다.

```
* 1단계
  - 2단계
    + 3단계
      + 4단계
```

- 1단계
  - 2단계
    - 3단계
      - 4단계

## 2.4. 코드

4개 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않은 행을 만날때까지 변환이 계속된다.

### 2.4.1. 들여쓰기

```
This is a normal paragraph:

    This is a code block.

end code block.
```

실제로 적용해보면,
적용 예:

---

This is a normal paragraph:

    This is a code block.

end code block.

---

> 한 줄 띄어쓰지 않으면 인식이 제대로 되지 않는 문제가 발생합니다.

```
This is a normal paragraph:
    This is a code block.
end code block.
```

적용 예:

---

This is a normal paragraph:
This is a code block.
end code block.

---

### 2.4.1. 코드 블럭

코드블럭은 다음과 같이 2가지 방식을 사용할 수 있습니다:

- `<pre><code>{code}</code></pre>` 이용방식 -> 근데 어려워서 안할 듯 나는 ;;

```
<pre>
<code>
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }

}
</code>
</pre>
```

<pre>
<code>
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }

}
</code>
</pre>

- 코드블럭코드("\```")을 이용하는 방법

<pre>
<code>
```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```
</code>
</pre>

```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```

깃헙에서는 코드블럭코드(/```) 시작점에 사용하는 언어를 선언하여 문법 강조(Systax Highlighting)이 가능하다.

<pre>
<code>
```java
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```
</code>
</pre>

```java
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```

## 2.5. 수평선 `<hr/>`

아래 줄은 모두 수평선을 만든다. 마크다운 문서를 미리보기로 출력할 때 페이지 나누기 용도로 많이 사용된다.

```
* * *
***
*****
- - -
------------------------------
```

- 적용예

---

---

---

---

---

## 2.6. 링크

- 참조링크

```
[link keyword][id]

[id]: URL "Optional Title here"

// code
Link: [Google][googlelink]

[googlelink]: https://google.com "Go google"
```

Link: [Google][googlelink]

[googlelink]: https://google.com "Go google"

- 외부링크

```
사용문법: [Title](link)
적용예: [Google](https://google.com, "google link")
```

Link: [Google](https://google.com, "google link")

- 자동연결

```
일반적인 URL 혹은 이메일주소인 경우 적절한 형식으로 링크를 형성한다.
* 외부링크 : <http://example.com/>
* 이메일 링크: <address@example.com>
```

- 외부링크 : <https://blog.naver.com/yiseojun1>
- 이메일 링크: <yiseojun4350@gmail.com>

## 2.7. 강조

```
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
~~cancelline~~
```

_single asterisks_
_single underscores_
**double asterisks**
**double underscores**
~~cancelline~~

> `문장 중간에 사용할 경우에는 **띄어쓰기** 를 사용하는 것이 좋다.`  
> 문장 중간에 사용할 경우에는 **띄어쓰기** 를 사용하는 것이 좋다.

## 2.8. 줄바꿈

3칸 이상 띄어쓰기(` `)를 하면 줄이 바뀐다.

```
* 줄 바꿈을 하기 위해서는 문장 마지막에서 3칸 이상을 띄어쓰기해야 한다.
이렇게

* 줄 바꿈을 하기 위해서는 문장 마지막에서 3칸 이상을 띄어쓰기 해야 한다.___\\ 띄어쓰기
이렇게
```

- 줄 바꿈을 하기 위해서는 문장 마지막에서 3칸 이상을 띄어쓰기해야 한다.
  이렇게
- 줄 바꿈을 하기 위해서는 문장 마지막에서 3칸 이상을 띄어쓰기 해야 한다.  
  이렇게

---
