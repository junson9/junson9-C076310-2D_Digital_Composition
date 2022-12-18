# Week15

기말고사 작업 하면서 서치한 것

# CameraShake노드

- 진폭, 회전, 스케일 등의 임의의 변화를 사용하여 시뮬레이션 된 카메라 흔들림을 시퀀스에 추가--
- 모션 블러를 생성하는 셔터 컨트롤도 포함되어 있다.

![camerashake 노드](https://user-images.githubusercontent.com/112802528/208302488-f195b008-b4cd-4ce5-985c-af534782c60d.JPG)

- rotation 회전
- scaling 스케일 변동
- frequency 흔들림 최저 주파수
- octaves 기본 흔들림 + 주파수 =임의의 흔들림

[출처](https://learn.foundry.com/ko/nuke/content/reference_guide/transform_nodes/camerashake.html)

# Replacement Phone Screen Using Planer Tracker

![트래킹](https://user-images.githubusercontent.com/112802528/208302774-66b07b3f-dba2-400d-b3fb-d0e913fe6e5b.JPG)

1. 손가락 마디별로 roto planer tracker 노드로 따주기
2. 화면도 마찬가지
- 노드화면에서 Hold_out (위) screen (아래)
위치하기
3. 화면 트래킹 
4. 합성 소스 이미지 가져와서 - 코너핀 적용 -> 트래킹 코너핀 적용 -> 머지

[출처](https://youtu.be/5SWrhgB7GBk)


