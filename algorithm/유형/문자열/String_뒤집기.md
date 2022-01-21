# String 뒤집기

```java
String s = "abcde";
String reverse = "";

for(int i = s.length() - 1; i >= 0; i--) {
  reverse += s.charAt(i);
}
```