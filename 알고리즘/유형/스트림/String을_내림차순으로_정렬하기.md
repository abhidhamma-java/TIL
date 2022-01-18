# String을 내림차순으로 정렬하기
***

String을 오름차순으로 정렬하는 방법은  
char로 바꾸어서 Arrays.sort()를 이용하면되는데

내림차순으로 정렬하려면 위에 정렬된 값을  
for문으로 순회하거나 StringBuilder를   
사용하는 방법밖에 없지만

stream을 사용하면 한번에 내림차순으로 정렬할 수 있다

```java
String str = "abcde";
str = Stream.of(str.split(""))
        .sorted(Comparator.reverseOrder())
        .collect(Collectors.joining());
```