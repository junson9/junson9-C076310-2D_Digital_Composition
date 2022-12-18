# Week14

기말고사 작업 하면서 리서치한 것

# TimeClip 노드

- TimeOffset 비슷한 노드 
- [ TimeClip ]노드를 사용하면 클립을 시간 앞뒤로 이동하고 클립 내의 프레임 순서를 반대로 할 수 있음.

- 클립을 슬립,  클립의 프레임 범위를 설정하거나 이 프레임 범위 밖의 프레임에 대한 작업을 설정하거나 클립을 검은색으로 페이드하거나 식을 설정하여 노드의 동작을 조정

[출처](https://learn.foundry.com/nuke/content/reference_guide/time_nodes/timeclip.html)


# Text 노드

- 이미지에 텍스트 오버레이를 추가할 수 있는 노드. 
- 표시할 텍스트를 입력하거나 Tcl 식 또는 Tcl 변수를 사용하여 텍스트 오버레이를 만들 수 있음. 
- 텍스트 오버레이는 그룹 탭의 애니메이션 레이어를 사용하여 애니메이션화할 수도 있으므로 시간이 지남에 따라 해당 속성(예: 위치, 크기 및 색상)이 변경.
 - ex) 슬레이트를 만들거나 크레딧을 스크롤할 때 유용

- 사용 해보니까 한글 폰트는 적용되지 않음

[출처](https://learn.foundry.com/nuke/content/reference_guide/draw_nodes/text.html)

https://youtu.be/GZu4KA0Mz8Y

# Nuke Mask Roto

배경에 캐릭터가 지나가서 거기에 로토따서 넣는 방법
https://youtu.be/KF61VLSF3JM

![마스크 로토](https://user-images.githubusercontent.com/112802528/208250134-fef96a5c-ca38-434e-a747-3b4b871337e3.JPG)

![마스크 로토2](https://user-images.githubusercontent.com/112802528/208250220-bfa7a95e-37b4-40d6-8f6e-5ad8da6bf833.JPG)

Roto mask 트랜스폼 노드를 사용하여 움직임 
- 응용할 거리가 많아 보임  
