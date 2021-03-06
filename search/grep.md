# grep
입력된 파일에서 일치하는 패턴을 찾는 명령어

## 사용법

> grep [옵션] [패턴] [파일 ...]

| 옵션         | 설명 |
|:------------:|------|
| -A 라인수 | 일치한 패턴 다음 내용을 라인수만큼 출력 |
| -B 라인수 | 일치한 패턴 이전 내용을 라인수만큼 출력 |
| -C 라인수 | 일치한 패턴 앞뒤 내용을 라인수만큼 출력(-A, -B 옵션이 모두 적용) |
| -c | 파일별 검색된 라인수 출력 |
| -n | 파일에서 검색된 라인넘버 출력 |
| -H | 파일에서 검색된 라인에 파일명 출력 |
| -v | 패턴과 일치하지 않는 라인만 출력 |
| -i | 대/소문자 무시 |
| -m | 검색된 라인 제한 |
| -e | 여러 개의 패턴 중 일치하는 라인 출력 |

------

``` shell
# search.txt
Hello, World
Hello
World
```

search.txt 파일에서 `Hello` 가 포함된 라인 중 `World` 가 없는 라인만 출력

``` shell
$ grep "Hello" | grep -v "World"

Hello
```

여러 개의 패턴 중 일치하는 라인 출력

``` bash
$ grep -e "Hello" -e "World" search.txt
Hello, World
Hello
World
```
