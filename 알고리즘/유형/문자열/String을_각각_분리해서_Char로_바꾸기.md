# String을 각각 분리해서 Char로 바꾸기

***

```java
for(char c : s.toCharArray()) {
  ...
}
```

> String을 char로 분리할 경우에는 이 방법이 가장 간단하다
> 하지만 인덱스를 이용해야 할 필요가 있을 경우에는 향상된 포문
> 을 사용할 수 없어서 아래의 방법으로 사용해야 한다

```java
for(int i = 0; i < s.length(); i++) {
  char c = s.charAt(i);
  ...
}

```
