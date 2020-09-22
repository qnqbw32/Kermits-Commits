# 위장 - 프로그래머스

생성일: 2020년 9월 3일 오후 1:47

## 1. 문제설명

스파이들은 매일 다른 옷을 조합하여 입어 자신을 위장합니다.

예를 들어 스파이가 가진 옷이 아래와 같고 오늘 스파이가 동그란 안경, 긴 코트, 파란색 티셔츠를 입었다면 다음날은 청바지를 추가로 입거나 동그란 안경 대신 검정 선글라스를 착용하거나 해야 합니다.

[위장 도구](%E1%84%8B%E1%85%B1%E1%84%8C%E1%85%A1%E1%86%BC%20-%20%E1%84%91%E1%85%B3%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%A5%E1%84%89%E1%85%B3%20df1ec4c64286417b8f7a834ae11e305c/%E1%84%8B%E1%85%B1%E1%84%8C%E1%85%A1%E1%86%BC%20%E1%84%83%E1%85%A9%E1%84%80%E1%85%AE%20bc0fa0ee42e34a04aa21e382b1694d37.csv)

스파이가 가진 의상들이 담긴 2차원 배열 clothes가 주어질 때 서로 다른 옷의 조합의 수를 return 하도록 solution 함수를 작성해주세요.

## 2. 제한사항

- clothes의 각 행은 [의상의 이름, 의상의 종류]로 이루어져 있습니다.
- 스파이가 가진 의상의 수는 1개 이상 30개 이하입니다.
- 같은 이름을 가진 의상은 존재하지 않습니다.
- clothes의 모든 원소는 문자열로 이루어져 있습니다.
- 모든 문자열의 길이는 1 이상 20 이하인 자연수이고 알파벳 소문자 또는 '_' 로만 이루어져 있습니다.
- 스파이는 하루에 최소 한 개의 의상은 입습니다.

[입출력](%E1%84%8B%E1%85%B1%E1%84%8C%E1%85%A1%E1%86%BC%20-%20%E1%84%91%E1%85%B3%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%A5%E1%84%89%E1%85%B3%20df1ec4c64286417b8f7a834ae11e305c/%E1%84%8B%E1%85%B5%E1%86%B8%E1%84%8E%E1%85%AE%E1%86%AF%E1%84%85%E1%85%A7%E1%86%A8%20c43687939286454b9fb892ee74e449cb.csv)

### 입출력 예 설명

예제#1

headgear에 해당하는 의상이 yellow_hat, green_turban이고 eyewear에 해당하는 의상이 blue_sunglasses이므로 아래와 같이 5개의 조합이 가능합니다.

```
1. yellow_hat
2. blue_sunglasses
3. green_turban
4. yellow_hat + blue_sunglasses
5. green_turban + blue_sunglasses
```

예제 #2

face에 해당하는 의상이 crow_mask, blue_sunglasses, smoky_makeup이므로 아래와 같이 3개의 조합이 가능합니다.

```
1. crow_mask
2. blue_sunglasses
3. smoky_makeup
```

## 3. 결과

위장 부위별로 몇가지 의상을 지니고 있는지 Dict에 저장한 후 조합가능의 가짓수를 출력합니다. 간단하죠!? 😊

```jsx
//Javascript

function solution(clothes) {
    var answer = 0;
    var dictclothes = {};
    
    clothes.map((e)=>{
        if(dictclothes[e[1]]==undefined)
                dictclothes[e[1]]=1;
        else
                dictclothes[e[1]]+=1; 
    });
    
    let sum=1;
    for(var i in dictclothes)
        sum*=(dictclothes[i]+1);  
    
    answer = sum-1;
    return answer;
}
```