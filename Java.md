# Java

리스트를 배열로 바꿔서 사용하고 싶을 때
```java
ArrayList<String> strList = new ArrayList<>();
String[] strArr = strList.toArray(new String[0]);
// strList.size() > 0 이므로 strList.size 크기의 배열을 생성하게 된다.
```