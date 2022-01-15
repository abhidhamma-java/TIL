# Array 정렬하기
***

```java
int[] array = new int[]{5, 4, 3, 2, 1};

//기본 정렬방식이 오름차순 이라서
//{1, 2, 3, 4, 5}로 정렬된다 
Arrays.sort(array);

//다시 내림차순으로 {5, 4, 3, 2, 1}로 정렬된다
Arrays.sort(arr,Collections.reverseOrder());

//부분 정렬하기
Arrays.sort(arr, 0, 4);

//커스텀한 방식으로 정렬하려면 이렇게 할 수 있다
Arrays.sort(arr, (e1, e2) -> {
            if(e1[0] == e2[0]) {
                return e1[1] - e2[1];
            } else {
                return e1[0] - e2[0];
            }
        });

//int Type array가 아닌 경우 이렇게 정렬할 수 있다
Arrays.sort(arr, (s1, s2) -> {
            // 단어 길이가 같을 경우
            if (s1.length() == s2.length()) {
                return s1.compareTo(s2);
            }
            // 그 외의 경우
            else {
                return s1.length() - s2.length();
            }
        });
```