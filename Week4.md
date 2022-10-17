# Week4

<br>

## After Effects and Nuke

* After Effects: 투디, 모션그래픽, 같은 어도비계열의 작업이 용이하다.

* Nuke X: 실사촬영본의 합성, 3D랜더링 된 과정을 추가하거나 보정을 한다.

Nuke: 실사촬영 안하는 3D 2D 애니

Nuke Studio: 타임라인 기능, 시퀀스를 관리할 수 있는 프로그램 + 누크X = 합쳐진 것.

Hiero: 타임라인이 나오지 않는다. 

<br>
<br>
<br>


# GOBO light
특수필름에 빛을 투광시켜 지면이나 벽면에 전달내용을 이미지로 투사하는 방식의 빛을 이용한 신개념 장비
   * ex) 감옥창살, 배트맨 조명 등..

<br>
<br>
<br>


# Nuke interface
![2276D84452872D081D](https://user-images.githubusercontent.com/112802528/196102371-7b3b68cc-d81a-4818-82d6-5bf14610de21.png)
![The-Foundry-NUKEX](https://user-images.githubusercontent.com/112802528/196102446-c3903761-f4eb-494f-ad01-95a816faf303.jpg)

**Menu**

**Viewer**

**Tool**

**Properties** 
노드를 삽입한 후 노드의 출력을 정의하는 옵션과 함께 속성패널이 활성화 된다. 노드 그래프에서 노드를 클릭하면 형성되어서 각종 기능과 수치를 조절할 수 있다. 

<br>
<br>
<br>


## Node Graph

누크에서 기본적으로 채널, 레이어 및 셰이더를 관리하는 방법이다. 

노드그래프를 사용하면 다양한 구성요소와 작업과정을 개별 노드로 시각적으로 구축이 가능하다.
* G키 ->Grade 노드 활성화. 
* TAP키 -> 노도를 서치 메뉴창이 만들어짐. 
* Tool창에서 노드를 불러온다.
* L키를 통해 노드들이 겹쳐있을 때 정리.

## 노드그래프 단축키 정리 
* <-> 축소
* <.> 점 노드 삽입
* <1,2,3> 노드 그래프에서 선택한 노드로 입력 생성,연결 (노드를 선택하지 않고 보기를 순환)
* <+> 확대
* < B > 블러노드 삽입
* < Backspace > 선택한 노드 삭제 
* < C > ColorCorrect 노드 삽입
* < D > 노드 비활성화/ 활성화
* < G > Grade 노드 삽입
* < N > 선택한 노드 이름바꾸기
* < O > 로토 노드 삽입
* < Tab > 노드 서치 메뉴 활성화

  [출처](https://learn.foundry.com/nuke/content/misc/hotkeys_studio.html)


<br>
<br>
<br>


## 뷰어창 여러개 띄우는 방법
![a-b](https://user-images.githubusercontent.com/112802528/196104992-8b7eb7db-b747-4e34-8400-0cbcf91aacdf.png)
b를 선택하고 싶으면 가운데 있는 -를 누르면 뷰어에 창을 여러개 띄울 수 있다.

<br>
<br>
<br>

## 노출조절 ##
![노출조절](https://user-images.githubusercontent.com/112802528/196105429-3feaed94-b87e-4f10-bf4d-2f184d677b46.png)
뷰어에서 만.

<br>
<br>
<br>

## 기능설명 ##
![다운로드 (3)](https://user-images.githubusercontent.com/112802528/196105771-2fcc640f-efdd-4c70-a920-ead28c0fe88e.png)

* 1번: title safe (자막 넣을 때), action safe (액션 할 때), format center, Format (내가 가지고 있는 포맷이 어디인지 확인)
* 2번: 화면 비율 조절
* 3번(제브라 패턴): 익스포저로 바꿀시 게인 수치를 올렸을 때 빗금친 것이 보인다. 노출이 괜찮나 확인용도.
* 4번: 프록시 계산 할 양을 줄이는 것
 * 5번: 풀 프레임 프로세싱, 보이지 않는 스캔라인을 다 스캔해 이미지를 뷰어에 보여준다.
 * 6번: 뷰어를 리프레시 하는 기능.
 * 7번: 사각형 안의 영역만 조절이 되는 것. (뷰어에 띄우는게 너무 오래 걸릴 때 영역을 줄여 그 부분만 본다.)

 ![다운로드 (4)](https://user-images.githubusercontent.com/112802528/196106415-b849144b-2f0c-4ce9-9d17-552dfdab2252.png)

200% 뷰 이미지 확대

1:1 원본비율 , 1:16=더 각지게 보인다.

<br>
<br>
<br>

## 뷰포트
![다운로드 (5)](https://user-images.githubusercontent.com/112802528/196106593-2ad9a614-679b-420e-9616-63fb6c00082b.png)
* Tap키로 3D, 2D 공간 이동 가능.

![다운로드 (2)](https://user-images.githubusercontent.com/112802528/196106889-12eadc16-98cc-4683-9794-8e8d629ddd5b.png)
* 뷰포트 컨트롤 누르며 돌아다니면 점이 생김.

* 픽셀의 정보를 알고싶을 때 가능
오른쪽 아래 방향 화살표를 누르면 한 로그 값의 수치 팔비트의 헥스 값의 수치 등등 여러개의 픽셀의 수치를 확인가능.

* Ctrl+Shift :선택 된 영역의 평균 값도 확인 가능 나중에 크로마키 작업할 때 많이 봄 예를들어 이정도 평균 값 있는 애들을 빼줘라할때 쓸수있음

Ctrl+마우스 오른쪽 누르면 사라짐

![다운로드 (1)](https://user-images.githubusercontent.com/112802528/196107319-0d1206dc-973f-4688-9b63-dc40baeaabe4.png)
* 속성 창 옵션 최대 패널 갯수 조절

<br>
<br>
<br>

## 로토노드

키보드 O 눌러서 생성

![로토노드](https://user-images.githubusercontent.com/112802528/196107618-611dd81a-7b1b-42f0-9151-74c7e67b7a37.png)

![로토](https://user-images.githubusercontent.com/112802528/196107588-4ec4ada6-cebb-47d7-8e5b-f2e39428d835.png)

* 로토 생성-> 인 풋을 이미지에 연결
* 로토모드의 기능: 패스 그려서 쉐입을 만들어 주는 것, 알파로 사용할 커브를 그리는 것.

![로토도구](https://user-images.githubusercontent.com/112802528/196107865-fd9b731e-bb42-4142-8c90-c5b80e0febdf.png)

왼쪽 맨 위부터
* 셀렉트 모드
* 펜툴
* 커브
   + 스무스 단축키 Z
   / Shft+Z 줄어듬 / E - 헤더 커짐 
