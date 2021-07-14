---
layout: post
title: 숫자야구 ver 0.2 in Python
date: 2021-07-14 22:43 +0900
tags: [python, tkinter, 숫자야구, GUI, etc]
---

# [Python] tkinter GUI 숫자 야구 게임 만들기
>저번에 심심풀이로 만들었던 숫자 야구 게임을 tkinter 모듈을 이용해서 GUI환경으로 만들어 보겠습니다.  
[이전 숫자야구 게시글](https://mswoo.github.io/2021/07/06/baseball/)

***

# 코드 설명  
1.우선 tkinter 모듈을 import합니다.  
`from tkinter import *`


2.root라는 이름으로 `Tk()`와 `mainloop()`만 선언해주면 윈도우 창이 생성됩니다.  
```{.python}
root = Tk()
root.mainloop()
```

3.생성한 윈도우 창에 하나씩 추가하면 됩니다.  
`title()` 제목 설정  
`geometry()` 윈도우 창의 크기와 시작위치를 설정  
`resizable(False, False)` 윈도우 창의 크기를 늘리거나 줄이지 못함.


4.필요한 label, entry, button 등을 추가해주겠습니다.  
Button의 command에 함수명을 입력하면 버튼 클릭 시 해당 함수를 실행합니다.  
Text에 y축 scrollbar를 추가하였습니다.  
```{.python}
label = Label(root, text="숫자를 입력하세요.")
label.pack()

ent = Entry(root, width=5)
ent.pack()

btn = Button(root, text="시도하기", command=check)
btn.pack()

btn2 = Button(root, text="정답보기", command=answer)
btn2.pack()

scrollbar = Scrollbar(root)
scrollbar.pack(side=RIGHT, fill=Y)

txt = Text(root, width=30, height=15, yscrollcommand=scrollbar.set)
txt.pack()
```

5.기존 콘솔창에서 실행되던 숫자야구 게임의 입력, 정답체크 하는 부분을 `check()` 함수로 만들어주고,  
'시도하기' 버튼을 클릭하면 check()함수를 실행하고, enter키를 눌렀을 때도 `check()` 함수를 실행할 수 있게 해줍니다.
```{.python}
root.bind('<Return>', enter)

def enter(event) :
	check()
```

6.게임 중 정답을 알고 싶을 때 '정답보기' 버튼을 클릭하면 정답을 string으로 형 변환 후 합쳐서 messagebox로 알려줍니다.
```{.python}
def answer():
	strans = list(map(str, gameAnswer))
	hint = "정답은 " + strans[0] +", "+ strans[1] +", "+ strans[2] +", "+ strans[3] +" 입니다."
	messagebox.showinfo("정답", hint)
```

***

# 실행 화면  
![basegui](https://user-images.githubusercontent.com/23252539/125631723-37fc2460-76c3-4b93-996b-243a170d0505.JPG)

***

[전체코드](https://github.com/MsWoo/Python/blob/main/baseball/baseball_gui.py)는 깃 저장소에 올려놨습니다.