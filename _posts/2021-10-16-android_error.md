---
layout: post
title: 안드로이드 System UI isn't responding 에러 해결법
date: 2021-10-16 18:59 +0900
tags: [안드로이드, android, 에러, error]
---

# [안드로이드] System UI isn't responding 에러 해결법  
>안드로이드 스튜디오의 AVD환경에서 테스트 중 만난 에러 해결법.  
[출처 사이트](https://mmol.tistory.com/entry/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-System-UI-isnt-responding-100-%ED%95%B4%EA%B2%B0%EB%B2%95)  

***
# 해결 방법  
AVD에 대한 설정 저장경로를 따로 설정하지 않았다면,  
C드라이브 / User / User 폴더 / .android / avd / 현재 사용중인 AVD 폴더에 있는  
'userdata-qemu.img' 파일을 삭제합니다. 이후 AVD를 재실행.  
System UI isn't responding 오류가 해결됩니다. 데이터가 계속 쌓이기 때문에 꼭 오류가 나지 않아도 정기적으로 해주는 것도 좋다고 합니다.  

# 주의사항!  
AVD에 저장한 설정값, 데이터들이 전부 사라지니까 주의하시길 바랍니다.