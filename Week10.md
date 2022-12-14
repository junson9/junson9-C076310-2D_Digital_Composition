# Week10
<br>
<br>

**트래킹 : 요소 하나를 정해놓고 그것을 따라가게 하는것**

이미지에서 애니메이션 데이터를 추출 할 수 있는 2D 추적기. 

[출처](https://learn.foundry.com/nuke/content/reference_guide/transform_nodes/tracker.html)

### 1. 2D트래커 : 촬영본에서 선택한 영역, 포인트, 포인트가 속한 패턴을 따라가는 (좌우상하) 역할

트래커: 하나의 점이 쭉 움직이는 것/ 점이 움직이는것 = X Y 방향으로 움직이는것 가능 , 기울기는 알 수 없음 (점이니까 , 면적이 없음) 

- 투 포인트 트래커: 중간값이 두개인것임. 두 트래커를 이어 선이 되면 기울기가 생긴다. →회전가능 (영상 촬영을 했는데 흔들렸어 할때 사용)

- 쓰리 포인트 트래커 : 삼각형 면의 생성: 실제로는 투디지만. 포토샵에서도 프리트렌스폼 해보면 각 모서리를 움직여서 실제로 평면이지만 안쪽으로 들어가게 퍼스펙티브를 줄 수 있는 것처럼 면적을 이용해서 크기의 변화라던가 깊이의 변화를 실제 쓰리디는 아니지만 쓰리디 인것처럼 묘사 할 수가 있음. (면적을 교체할때 사용을 한다.)

### 2. 카메라 트래커 3D: 가상의 3D공간을 할때, 3D공간의 카메라 추적을 할때. (VFX 매치무브 팀이라고 해서 그 안에 쓸디 카메라를 만드는 팀도 있음 ) (3개가 있어야 이미지를 붙힐수가 있음.)


<br>
<br>

# Tracker (Tracker / Camera Tracker)

트래커 노드 : 로토스코핑처럼 툴바가 따로 있음. 

add track →트래킹 마커 생성 (생성을 할때의 기준 / 크로스헤어부분 (트래킹의 중간)이 픽셀이 좀 난잡한 특징점이 있는 영역을 하는게 좋다 → 예를들면 허허벌판보다는 나무가 좋다)

4각형 영역이 2개인데 가운데는 패턴영역 : 안에있는 픽셀의 트랙을 찾는 것, 최대한 유사한 수열을 찾는 것 밖에있는 패턴을 크게 키워주면 앞에 프레임과 뒤의 프레임을 계산했을때 확 바뀌는 경우가 있다.

 **결론→ 카메라를 심하게 흔들었을때 영역이 충분해야한단 소리  (젤 왼쪽 젤 오른쪽 잡고 움직이면 됨)**

가로로 이동하는 기차의 경우에는 → 가로로 이동을 하니까 좌우로 넓혀주고 상하는 좁게 맞춘다.

---
<br>
<br>

### 실습

상단의 트래커 툴바 

- 플레이버튼 : 끝까지 간다
- 그 앞 : 한프레임만 간다.
- 플레이버튼의 R : 영역을 지정하겠다는 것 → 지정을 하면 트래킹이 시작이 될 것. 좌측 상단의 영역이 내가 선택한 패턴이 잘 따라가고 있는지를 보시면 된다.- 트래킹 되면 파란색으로 캐쉬가 되었다고 뜬다.
- 에러 수치를 누크에서 표현을 해준다. → 초록색 (에러수치 낮음/ 노란색 붉은색으로 갈수록 (트래킹 에러수치가 높다.) 높으면 무조건 다시 해야하나? → 는 아님 왜냐, 붉게 표시된 부분이 앞부분보다 블러한 상태일 경우는 해도 괜찮겠는데? 파악하고 한다. 다시할거다 싶으면 x표시를 누르면 지워진다.  →지우고 다시 재생버튼 누르면 트래킹 시작
- 네모난 영역은 트렌스폼 노드 사용이 가능하다 (크기조절 같은게 가능하단 건가) / 1001에다가 가릴만한 요소를 만들어놓고 원본 플레이트에 연결을 해주면 똑같이 움직이겠죠 그런식으로 써먹는 것이다.

이렇게 되면 트랙 1번이 생겼죠 → 트랜스폼이란게 있음 설정탭에 (익스포트에) 

/ (트래커에 - TRS가 있는데  - 트랜스폼 로테이트 스케일)점이 하나만 있어서 (원포인트) 트랜스폼만 체크한것 로테이트나 스케일을 할 필요가 없어서.설정→ 트랜스폼→ 매치무브 → 플레이트가 오른쪽으로 움직임. → 따라감설정→트랜스폼→스테빌라이즈→원본 플레이트가 위아래로, 움직이는것과 반대로 들어감 (왼쪽으로) 

지금 이거는 의미가 없긴 함 점이 2개여야 의미있음. 흔들리는걸 잡아줄테니.
<br>
<br>

## 정확한 순서 

1. 영역을 찾는다
2. 트래커 노드를 만든다
3. 트래커 노드의 영역을 지정한다
4. 지정한 후 재생을 눌러 트래킹 라인을 만든다
5. 붉은것은 다시해야함.

***나무를 지우거나 다른 요소를 추가해달라는 주문이 들어옴***

→ 어떻게 해야할까? 컬러휠(그냥 가리려고 만든 노드) → 트랜스노드 → 스케일줄이고 → 움직임에 맞춰서 이동해야 하잖아요 그럴려고 트래커 만든 것.(하나의 노드)

→ 설정 익스포트 → 트랜스폼이라는 노드가 있음 → 움직이는 트렌스폼 노드를 하나 추가하는 것.스티블라이즈- 역방향

매치무브- 트랜스폼이 가지고잇는것과 동일하게 움직이는 노드

똑같이 하나씩 더있는데 베이크드라고 되어있죠.⇒ 형성 Transform_MatchMove →초록색 화살표 (노드 자체에 키프레임이 없고 트래커 1이랑 이어줬다는 뜻)

⇒ 두개 연결! **원포인트 트래킹의 주의점 → 트래커가 잘 따라갈 수 있는 영역을 선택을 해 주는게 중요하다.** 

트래킹은 역방향으로도 할 수 있음/ 정확한 위치를 쫓아가야하는게 트래킹. /그래야 덮어쓰거나 지우거나 할 수 있음.집을 없앤다: 트래커의 특징점을 찾아서 중심에 두기 ( 지붕사이에 중앙을 두기) → 좌우 영역 넓히기 → 트래킹시작 (흔들리지 않고 잘 가는지 확인하기. )(사진은 좌우영역 넓히는것)십자가에있는 중심영역이 잘 움직이고 따라가는지 확인해야함.(컨트라스트조절)

원본을 대비가 심하게 왜곡시켜도 됨-> 그러면 트래커가 더 잘 따라가기 때문에 

ㄴ 색을 변환한다거나 소스를 넣는다거나 할때는 원본유지를 해야하는게 맞지만 트래커를 할때는 움직이는게 중요한거기 때문에 … / Color Correct 컨트라스트를 조작해서 → 트래킹을 했을때 더 잘 뽑겠죠

→ 쓰고 나서 컬러값 지운다움에 트래킹만 남겨놓고 원본에 다시 연결하면 됨. (이런 일이 많기도 함)

트래킹의 일정 부분을 나무로 덮을꺼다 했을때 → 트래킹따기→ 이미지로토따기 → 알파영역만 가져오기 → 프리멀트 노드로 남긴다음에 → 원본이랑 머지하기 ( 캡쳐해서 이미지 추가 )(이미지 로토 따기→로토에블러주기→ 머지(마스크))로토따기→ 알파영역만 불러오기→이미지에알파영역있으면 SHUFFLE 노드 만들어서 알파만 끊어주기프리멀티를 달고 남긴다음에 트렌스폼 달아서머지 달고 → 원본이랑 이어준 다음에 → 트렌스폼으로 이동 

(트랜스폼 조절자 센터 조절 → 컨트롤키 눌러서 이동시키기 )프레임홀더를 해놔서 그대로 있을거임 그러니까 트래킹에서 따낸 매치무브 값 노드를 만들어서(베이크드) → 연결을 해주면 → 잘 따라감! ( 완성 )완성된 노드 (MG는 머지)

(프레임홀드 사용시 1001프레임의 로토이미지)

BUT 프레임홀드를 사용하지 않으면 영상이 흐르니까이렇게 된다.

프레임 홀드 노드를 사용한 이유 → 로토를 해놓은 부분을 따라서 영상이 따라가니까 그니까 설명을 하자면 로토 쉐입의 영상 내용물이 바뀌니까 나무들이 흐르는것처럼 보이게됨 그니까 그걸 막으려고 한 프레임에 있는걸 옮길거니까 프레임 홀드 노드를 꼭 사용을 해야한다.

+ 나무 더 심으려고 할때 원포인트 트래킹/ 하늘에 열기구를 띄워놓고 싶다 /멀리 있는 열기구를 추가하고 싶은데 눈대중으로 맞추기 보다는 트래킹을 만들어서 열기구를 띄워놓고 움직이는것이 좋다. 

---

[https://learn.foundry.com/course/4678/view/before-you-begin](https://learn.foundry.com/course/4678/view/before-you-begin)

누크 스크립트는 공유를 해줄거지만

플레이트는 공유를 못해줌 → 알아서 파운드리 사이트에 들어가서 다운받기 왜냐면 18기가나 됨 너무 커

트래킹 할곳을 정확하게 설정을 해주고 플레이트를 정확하게 분석을 해서 서치 에어리얼을 충분한 공간을 만들어 주는것이 필요합니다. 최대한 다 키우는것도 좋은건 아님. (넓은 영역을 계산 해야하니까) 
<br>
<br>

## 투포인트 트래커

나무 표지판 

점과 점이 연결되면 선이생기니까 → 이 선으로 기울기를 생성할 수 있다!트랙1번 (왼쪽 모서리) 트랙 2번 (오른쪽 모서리) 위 아래로 흔들리는 카메라니까 바깥 네모 영역의 위 아래도 맞춰줌 **에버리지 트랙**  → 평균값을 만들어줌 → 에버리지트랙은 rotate값은 안나옴(밑사진) (회전의 계산은 사용 불가능) 중간 위치값을 쓸때만 사용.타임라인에서 I,O 누르면 인풋 아웃풋 

**회전값을 위해**

스태빌라이즈를 뽑고 → 회전을 역방향으로 뽑아서 가만히 있는것처럼 카메라를 멈춰줌. 회전이 없는것 처럼 보이게 만들어 준다. 
<br>
<br>


## 쓰리포인트 트래킹

트랙 3개 만들기

알파 거미줄을 트랜스폼 매치무브를 해서 맞추기3 포인트 트래킹을 해서 매치무브 노드를 넣어주면 붙어있는것처럼 표현.로테이션 스케일 트랜스폼 3개가 다 들어가있음.

3 포인트 까지는 트래커에서 뭘 했자면 → 오른쪽 창 export 설정에서 트랜스 폼 노드를 만들었어요 / 매치무브거나 스티블라이즈거나4포인트 트래킹을 하면 cornetpin 2D모드로 변환해서 쓸 수 있어요
<br>
<br>

## 4 포인트 트래킹

꼭지점마다 트랙 설정 → cornetpin2D → 반드시 트래커 4개를 설정해야하는 노드 / 1 2 3 4 순서를

왼아래 오른쪽 위 오른 왼쪽 순서

3포인트 까지는 스케일을 맞춰주고 포인트를 맞춰줬어야했죠.4포인트 트레킹부터는 알아서 인식해서 맞춰줌. → cornerpin2D를 연결 → 설정 from →영역 좌표값이 들어있는데 → Set to input을 해주면 맞춰진다. → 노드 연결 끝내면→ 트래커가 맞춘 위치로 이동한다. ⇒ 트래킹 완성!


모서리가 둥글면? → 트랙을 안쪽으로 따서 4각형 만든다 → 트랜스폼으로 크기조절을 한다! → 만약 둥글게 올리는것도 하고싶으면 알파로 모서리 수정해서 올리기
<br>
<br>

## Camera Tracker

2D 트래커 → 패턴과 서치에어리어가 따로있는데

3D 트래커 → 점들의 움직임을 파악해서 가상의 3D 카메라 / ex. 마야의 카메라 값처럼 / 2D 영상에서 그 카메라를 추출해 내는것.애드 유저 트랙이라는걸 통해서 점을 찍을수는 있다.

설정창 → Features 

→ number of Features → 개수조절가능 (교수님은 충분하게 설정하는 편)어떤 한 점이 있는데 걔가 카메라 렌즈랑 수직으로 있지 않는한 오른쪽 왼쪽으로 퍼지죠 .

밖으로 나가면 안으로 들어오고

그 픽처들이 움직이는걸 계산해서 안으로 들어가는거네 밖으로 나오는거네 

바닥면에 있는애들도 깔리면서 움직이는걸 인식을 하고 서있는것도 인식을 해서 

계산을 하는것.
<br>
<br>

## 카메라트래커를 제대로 쓰려면 뭐가 필요한가

필름 백 프리셋을 제대로 넣어줄수록 완벽한 트래킹이 나온다.

![lens distortion grid](https://user-images.githubusercontent.com/112802528/207233586-e085c1f3-c58e-4213-9d19-9e11a5a2c9e9.jpg)

카메라의 센서 - 평면 → 렌즈는 굴곡 → 왜곡이 0인 렌즈는 없다. 3D 상에서만 존재함. (누크 마야 맥스 후디니 등 가상계산렌즈니까)**lens distortion grid** → 인쇄해서 촬영할때 가지고다니면 좋다. 그리드에다가 쓸수있도록 칸을 만들어놓으면 좋겠죠 . 촬영하기전에 카메라,렌즈값,조리개 기록을 해놓고 찍으면 Lens Distortion을 켤때 도움이 된다. → 렌즈디스토션 노드는 주변부 왜곡을 펴주는 역할을 하고 펴놓은 상태에서 합성을 얹고 합성이 끝나면 다시 삭제하는. 일할때 무조건 쓰는

## 카메라트랙의 설정

Camera Motion

Lens Distortion

Focal Lengh

Film Back Preset

Film Back Size 렌즈 디스토션이 있냐 없냐 물어봄

다 설정하고 → Track 클릭 → Solve 눌러서 써먹을수있는애인지 아닌지 계산 해줘야함

⇒ 초록색, 빨간색 , 주황색

초록색 솔브된것

빨간색 에러가 높은것

주황색 해결이 안된것.

오토트랙 설정- > 여러가지 수치를 이용을 해서 어떤것들만 남길것, 사용할것인지 고르기 가능

Min Lengh 3 (기본값) → 교수님은 5로 바꿈

Max Track Error → 최대 에러 수치를 어느정도로 해줄것인지 … 1.5정도도 괜찮음 

→ 만지고 나서는 다시 솔브해줘야함

근데 솔브하기전에


Delete Rejected → 붉은거 지워줄거니? 


다시 솔브→ 에러가 0.96으로 낮아졌죠 → 이정도면 사용가능.

이때 크리에잇 누르면 → Camera 노드가 나오죠 → 마야 카메라랑 똑같은 것

→ 누크 3D 공간으로 뷰어 변경  / 플레이 해보면 움직이는 카메라가 추출이 된 것

큐브같은걸 공간에 놓고싶을때 퍼스팩티브가 생기는데 2D로는 하기가 힘들고 어렵다. 

3D카메라를 추출을 하면 카메라를 기준으로 물체를 놨을때.

그냥 카메라를 추출하면 카메라가 월드 중점쪽에 생성됨. → 원본을 보면 바닥에 붙어서 찍었나? → 사람이 어느정도 서서 사람의 시점에서 찍은 플레이트인것 ⇒ 카메라가 좀 올라와야함

ㄴ 수동으로 맞추기는 불가능해.
<br>
<br>

## 다른방법이 뭐가있느냐


에러가 적은 픽처 바닥면 을 선택  → 우클릭 ground plane 선택 (얘네를 기반으로 바닥면 설정) → 세트셀렉티드 선택 → 바닥면의 포인트가 됨. 

씬 크리에이트 → 각각의 요소들이 가진 컬러 쓰리디 공간을 구성을 하는것. 

씬 - 마야 공간이나 마찬가지 … 각 요소별로 씬을 만들어야함. 씬 안에 카메라 반드시 있어야하고

씬안에 큐브가 있다는 뜻.


→ 3D 작업을 2디로 바꾸는 작업 (랜더를 해야하는것.)

**Scanline Render 노드 연결**

1. 카메라 
2. 오브제
3. 백그라운드

2D 랜더가 됨.


설정→ 씬에서 스케일을 키워준다거나 작게 한다거나 설정이 필요하다.

씬 스케일을 2배했더니 이렇게 하니까 큐브가 작아졌다.

결론⇒ 3D 공간에 물건을 집어넣을때 필요한게 뭐냐 -< **카메라트래커!**

---

3D 노드는 → 동그라미!

2D 노드는 → 각져있다!


Card / Cylinder / Sphere 같은 노드들 3D 상에서 테스트용으로 사용하기도하고 .. 모델링이라던가 그런것도 이쪽으로 불러올 수 있다. 

ReadGeo → Fbx파일도 불러올 수 있다. 


---
 

Trans form geo 노드를 통해 카드 를 표지판 위치에 가져다 놓고싶으면


기본이 노드셀렉션모드

버텍스 셀렉스 모드로오면

수작업으로 맞춰 줘도 되지만 → 버텍션 셀렉스 모드로 오면 → 포인트 클라우드를 직접 선택을 할 수 있다.

표지판에 네모를 붙이고싶다. (카드노드를)

이 부근이 표지판이 있는것 같다 그러면 선택을 하고 → 드래그 파란색 표기


카드의 트렌스폼지오노드에 아이콘 클릭 (스냅메뉴)임

지오투셀렉션 

원을 뒤로 보내고싶다 하면 로토스코핑으로 앞에 값을따서 가리면 됨.

**원포인트 투포인트 트래킹해보고**

**여러분이 촬영한걸로 트래킹을 해보셔도 좋습니다**

**추가로 카메라의 움직임이 있는 샷을 찾아서 이렇게 카메라 트래킹을 해보기**
