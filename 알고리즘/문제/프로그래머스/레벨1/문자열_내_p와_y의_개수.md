# **문자열 내 p와 y의 개수**

***

```java
class Solution {
    boolean solution(String s) {
        boolean answer = true;

        int pCount = 0;
        int yCount = 0;

        for(char c : s.toCharArray()) {
            if(c == 'p' || c == 'P') {
                pCount += 1;
            }
            if(c == 'y' || c == 'Y') {
                yCount += 1;
            }
        }

        if(pCount != yCount) {
            answer = false;
        } else {
            answer = true;
        }

        return answer;
    }
}
```

***

## 사용된 유형

[String을 각각 분리해서 Char로 바꾸기](https://github.com/abhidhamma-java/TIL/blob/main/알고리즘/유형/문자열/String을_각각_분리해서_Char로_바꾸기.md)
