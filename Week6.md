# Week6

<br>

# Rotoscoping
* 매트를 수동으로 생성하여 다른 배경 위에 합성 할 수 있도록 하는 기술. 
* roto노드를 통해 Alpha값을 만들어낸다.
* 움직임에 관련된 부분을 필수적으로 따야한다. (ex. 손가락, 손가락 전부 (접힐때는 마디마디로 나뉘어서 따야한다.))
* 하드 서페이스 물체들도 하나로 하는것이 아니라 부위별로 나눠 줘야 한다. 퍼스펙티브를 잘 맞춰주면 좋다.
* 로토스코핑은 외곽을 따는 것이 중요하다. 외곽을 최대한 잘 잡아내고 안쪽은 큰 로토를 따서 채워주는 방식으로 진행한다.

<br>
<br>
<br>

# Rotoscoping Prep
* **Identify Motion Path** (이동 경로 식별)
: 애니메이팅으로 따지면 Straight ahead 방식이 아닌 pose to pose 방식으로 잡는다. Frame 별로 잡기 보다는 크게 작업한다. 어떻게 움직이는지 분석 해야 한다. (ex. 가위바위보 하는 손의 가위 →  보자기의 이동 방식 분석)

* **Separate by Objects** (개체별 구분) : 개체를 오브젝트 끼리 구분하는 것.

* **Stabilize Plate** (안정 판) : 카메라가 위 아래로 움직일 경우 맞추기가 어렵다. 그래서 tracking 으로 카메라가 움직이는 방향의 반대값을 줄 수 있다. (위 아래로 흔들리는 카메라의 반대값을 주어 반대로 움직이게 만든 후 → 그 상태에서 로토 스코핑을 한다. →  로토 쉐입이 원래 상태로 따라 움직이게 반대값을 넣으면 → 원본대로 움직이게 된다.)

* **Primary and Secondary Forms** : 오브젝트에서 움직임이 적은 중앙의 형체 (주로 중앙 바디)를 메인으로 잡고 그 외의 쉐입을 맞춰준다.

* **Use Rotational Points** : 
가위바위보 할때 회전하는 부분들, 3D 리깅 했을때 뼈를 심는 (조인트를 심는) 그 지점을 잘 파악해서 움직임 포인트를 정한다. 

[출처](https://youtu.be/rBPz0LL0yF0)

<br>
<br>
<br>

# 절대경로 저장
파일 경로 → 절대경로 (이 경로를 알면 탐색기에서 위치를 찾아갈 수 있다.)

* 파일 공유를 위해서는 상대공유로 변환해야한다.

상대 경로 → 스크립트 위치를 기본으로 해서 위치를 찾아가는 것.

## 설정 방법 ##
1. Project directory를 수정 ( Edit > Project Setting or Shift+S) 
2. Script Directory 버튼을 눌러 nuke script가 저장되는 경로로 설정. [python {nuke.script_directory()}] 다음 코드로 채워짐.


3. file path 앞에 참조시킬 directory를 **../** 으로 교체해준다.

Ex. **절대경로**: C:/Users/Admin/Documents/Nuke/Project001/Shot002/Frame02_####.dpx

**상대경로**: ../Shot002/Frame02_####.dpx

[출처](https://support.foundry.com/hc/en-us/articles/208961109-Q100154-Relative-file-path-referencing-in-Nuke)

<br>
<br>
<br>

# Rotopaint
* 로토페인트 : 로토모드의 기능이 있으면서, 브러쉬 블러 등이 추가 되어있는 기능 , 로토 스코핑, 장비 제거, 가비지 매트 및 먼지 파열과 같은 작업에 도움이 되는 벡터 기반 노드. 

* 브러쉬 툴: 브러쉬 질, 쉬프트 마우스 왼쪽 클릭 드래그 - 브러쉬 크기를 정할 수 있다. 
하드니스를 통해 외곽의 날카로음을 조절 가능하다.
설명하는 노트를 남길때 주로 사용한다.

* 스탬프 툴: 처음엔 브러쉬 모양이 바뀐다, 컨트럴 키 눌러서 드래그, 움직이지 않는 포인트와 이동하는 포인트 두개를 설정하여 멈춰있는 레퍼런스 부분을 통해 움직이는 쪽이 레퍼런스 영역에서 이미지를 가져와 적용한다. 
쉬프트 키를 누르고 드래그 해 크기를 조절한다. 

[출처](https://learn.foundry.com/nuke/content/reference_guide/draw_nodes/rotopaint.html)

# Merge operation
병합 노드로 이미지를 레이어링 할 때 병합된 이미지로 출력되는 새 픽셀값을 위해 한 입력의 픽셀 값이 다른 입력의 픽셀 값으로 계산되는 방식을 결정하는 합성 알고리즘.

누크가 더하고 빼고 곱하고 나누는 과정을 대신 해준다.

* A,B = RGB에 해당하는 값
* a,b = 알파에 대한 값.

![mergeoperation](https://user-images.githubusercontent.com/112802528/199413605-d9612364-b95d-45a8-89c5-a35da25c36e8.JPG)

**Over** : 배경 플레이트에 전경 요소를 겹칠 때 사용.

A 인풋을 B에 더한다.
= B의 인풋에 A만큼의 구멍이 난것. 그리고 B를 곱한다. 

![over](https://user-images.githubusercontent.com/112802528/199414675-a91cb46b-4d25-4090-bbb7-8e0601793de2.JPG)



[출처](https://learn.foundry.com/nuke/content/comp_environment/merging/merge_operations.html)




연구 및 운동 ● 회전 운동 ○ 사람과 함께 하는 1 ■ 예) 걷기, 달리기, 영화에서 찍은 사진 ○ 딱딱한 표면으로 찍은 사진 ■ 예) 자동차, 노트북, ETCS. ● 병합 작업 ● 논의한 주제 조사 ● Github에 직접 글과 함께 자세한 설명과 함께 요약 작성 ● 연구 정보를 복사만 하지 마십시오 ● 인용 필요(필수)
