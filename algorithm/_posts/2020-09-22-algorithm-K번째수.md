# K번째수 - 프로그래머스

속성: 2020년 9월 2일 오후 10:25
속성 1: Seongmin Jeong님이

## 1. 문제설명

배열 array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하려 합니다.

예를 들어 array가 [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3이라면

1. array의 2번째부터 5번째까지 자르면 [5, 2, 6, 3]입니다.
2. 1에서 나온 배열을 정렬하면 [2, 3, 5, 6]입니다.
3. 2에서 나온 배열의 3번째 숫자는 5입니다.

배열 array, [i, j, k]를 원소로 가진 2차원 배열 commands가 매개변수로 주어질 때, commands의 모든 원소에 대해 앞서 설명한 연산을 적용했을 때 나온 결과를 배열에 담아 return 하도록 solution 함수를 작성해주세요.

## 2. 제한사항

- array의 길이는 1 이상 100 이하입니다.
- array의 각 원소는 1 이상 100 이하입니다.
- commands의 길이는 1 이상 50 이하입니다.
- commands의 각 원소는 길이가 3입니다.

[입출력](K%E1%84%87%E1%85%A5%E1%86%AB%E1%84%8D%E1%85%A2%E1%84%89%E1%85%AE%20-%20%E1%84%91%E1%85%B3%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%A5%E1%84%89%E1%85%B3%20f7beac66f9164ea7ad96d090d2f7a483/%E1%84%8B%E1%85%B5%E1%86%B8%E1%84%8E%E1%85%AE%E1%86%AF%E1%84%85%E1%85%A7%E1%86%A8%2064f7fbdc94fb457baceabc61a36d1dc4.csv)

### 입출력 예 설명

[1, 5, 2, 6, 3, 7, 4]를 2번째부터 5번째까지 자른 후 정렬합니다. [2, 3, 5, 6]의 세 번째 숫자는 5입니다.[1, 5, 2, 6, 3, 7, 4]를 4번째부터 4번째까지 자른 후 정렬합니다. [6]의 첫 번째 숫자는 6입니다.[1, 5, 2, 6, 3, 7, 4]를 1번째부터 7번째까지 자릅니다. [1, 2, 3, 4, 5, 6, 7]의 세 번째 숫자는 3입니다.

## 3. 결과

간단히 배열의 정렬 및 k번째 랭크를 검출하는 문제입니다. 
아래의 코드보다 더 짧고 간결한 방법들이 많으나 읽기 편한 방법을 선택합니다.

```python
#python3

def solution(array, commands):
    answer = []
    for i in range(0,len(commands)):
        tmp = array[commands[i][0]-1:commands[i][1]]
        tmp.sort()
        answer.append(tmp[commands[i][2]-1])
    return answer
```