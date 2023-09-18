<<<<<<< HEAD
### 리뷰어(push한 사람): 
ee
=======
# Quest 02. 거북이 미로찾기

>난이도: 🟡🟡🟡⚪⚪  
>장르: ColabTurtlePlus, 함수, 조건문 활용  
>>>>>>> b1c4bffdc37456413f6b8f69c3735fe9e51dd0c4

## AIFFEL Campus Online Code Peer Review

- 코더 : 서승호  
- 리뷰어 : 김연  

## PRT(Peer Review Template)

```

from ColabTurtlePlus.Turtle import * # ColabTurtle 라이브러리에서 Turtle 클래스를 import


# 미로 데이터
maze = [
    [0, 1, 0, 0, 0],
    [0, 0, 0, 1, 0],
    [0, 1, 1, 0, 0],
    [0, 0, 1, 1, 0],
    [0, 0, 0, 0, 0]
]

# 시작 위치와 목적지 위치
start_x, start_y = 0, 0
end_x, end_y = 4, 4

# 터틀 초기 설정
window = (100, 100)
initializeTurtle(window, 'logo')
speed(1)

# 미로 찾기 알고리즘
def solve_maze(x, y):
    # 목적지에 도착한 경우(조건문)
    if x == end_x and y == end_y:
        print("미로를 찾았습니다") # "미로를 찾았습니다" 라는 문장을 출력하고
        return True # True를 반환한다.

    # 현재 위치에서 갈 수 있는 방향 탐색
    for dx, dy in [(0, 1), (1, 0), (0, -1), (-1, 0)]:
        nx, ny = x + dx, y + dy
        # 미로 범위(0,0 ~ 4,4) 내에 있고, 갈 수 있는 길인 경우
        # maze 행렬에 숫자 0인 부분을 찾아서 갈 수 있도록 and로 연결
        if 0 <= nx < 5 and 0 <= ny < 5 and maze[nx][ny] == 0:
            # 갔던 길 표시
            maze[nx][ny] = 2
            pendown()
            # 다음 위치로 이동
            goto(nx*10, ny*10)  # 거북이 다음 위치로 이동

            penup()

            # 코드를 해석해주세요!!
            # 재귀적으로 다음 장소를 찾는 코드다.
            if solve_maze(nx, ny):
                return True
            else:
                # 다시 이전으로 돌아가기
                pendown()
                goto(x * 10, y * 10)
                penup()
                # 표시된 길 0표시(지우기)
                maze[nx][ny] = 0


    # 길을 찾지 못한 경우
    # "길을 찾을 수 없습니다"를 출력하고
    # False를 리턴

    else:
        print("길을 찾을 수 없습니다")
        return False
# 시작 위치에서 미로 찾기 시작
goto(start_x, start_y)
solve_maze(start_x, start_y)
import pprint
pprint.pprint(maze)

````

- [✔️]  ** 1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요? **      
- [✔️]  ** 2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요? **    
- [✔️]  ** 3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나”, ”새로운 시도 또는 추가 실험을 수행” 해봤나요? **    
- [✔️]  ** 4. 회고를 잘 작성했나요? **    
- [✔️]  ** 5. 코드가 간결하고 효율적인가요? **    

## Review

문제를 이해하는 과정에서 시간을 많이 할애했던 저로서는 효율적이고 간결하게 작성된 답안을 볼 수 있어서 좋았습니다.  그루님의 코드를 보며 제 코드에 대해 더 연구할 수 있었던 유익한 과제였습니다.  

