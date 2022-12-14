# Week7
## feedback ##
1. Tif파일에 알파가 들어가 있으면 로토 그렸을때 흰색으로 칠하면 보이지 않는다. -> 이럴경우 노드를 하나 더 추가 해야 한다. 

2. 리드노드로 이미지를 불러왔을때 -> RGB가 흰색이다(0이 아닌 수치가 들어있다.) 이런 상태면 Shuffle 노드와 remove노드 두개 위 노드로 RGB를 연결해주면(알파 제외) 알파를 볼 수 있다.

3. Shuffle , remove 노드는 많이 쓰이니 기억해둔다.

4. 가운데를 잡아주는 로토 쉐입이 들어가면 구멍이 뚫리는 사태를 피할 수 있다.

5. 외곽을 표현하는 포인트가 급격하게 움직이면 알파가 사라지는 양상이 다르니까 신경 써줘야 한다. (개별적으로 움직이지 않는것이 좋다. 점 위치를 신경쓰자.)

6. M키 -> 컬러 오버레이 단축키

<br>
<br>
<br>

# Chroma key
* 크로마키란? (+ Week3)

두 개의 영상을 합성하는 기술이다. A와 B 이렇게 두 개의 영상이 있으면, B 영상으로부터 '좁은 범위의 색'을 제거하거나 투명하게 만들어서 뒤의 A 영상이 비치게 할 수 있다. 이 기술은 또한 컬러 키, 색 분리 오버레이, 그린스크린, 블루스크린이 라고도 일컬을 수 있다.

## Chroma key 에서 블루? 그린? ## 

### Week3 research =  ###
* **녹색**: 디폴트로 디지털 카메라가 사용하기 쉽고, 조명이 적게 들고, 낮에는 성능이 향상되지만, 색상 유출에 어려움을 겪을 수 있다. 
     * ex.금발
<br>

* **파란색**: 가장자리가 깨끗하고 색이 잘 튀지 않는다. 밤에는 더 좋지만 조명이 더 필요하다.
    * ex.뉴스룸 기상캐스터는 종종 그린스크린 앞에서 촬영된다.

**어떤 색이 더 지배적으로 존재하느냐, 실내냐 실외냐에 따라서 그린이나 블루를 선택하는 편.**

ex. 필름으로 촬영할 때는 블루로 썼고 디지털 촬영하면서 그린을 사용.

<br>
<br>

## Chroma key의 시작
매트를 쉽게 추출하기 위한 방안으로 크로마키를 하는 것.

필름 현상할때, 필름은 빛이 들어오면 그 빛이 상에 맺혀서 필름에 정보값이 입혀지는 것. (ex. 필름이 다 말아지기 전 열어서 빛이 들어와서 필름 값을 잃은 경험.)

<br>
<br>

## 블루 스크린의 시작
필름에서 RGB 중에 대비가 높은 B채널을 이용해 매트를 만든 것.

블루 배경, 배우에게 노란 조명을 쏴서 배경과 인물을 분리하고 합친다. (ex.킹콩)

단점: 컬러에서 쓸 수가 없음. 흑백영화에서 사용.

기술이 발전하면서 테크닉 컬러에서 RGB를 분할해 추출할 수 있는 기능이 나옴.

<br>
<br>

## 옐로우 스크린의 시작
흰색 배경으로 구현, 일반 무대 조명은 밝은 노란색 나트륨 램프와 함께 사용. 나트륨 빛은 거의 전적으로 좁은 주파수 대역에 떨어지며 프리즘을 사용하여 다른 빛과 분리할 수 있고 카메라 내에서 동기화된 별도의 필름 캐리어에 투사할 수 있다. 노란색의 특정한 파장만 가늠하여 영역대의 노란색을 빼는 것

* 디즈니에서 개발하여 메리포핀스 같은 촬영을 했음.

<br>
<br>

## 그린스크린(Green Screen) 

* 그린스크린은 샷의 배경에 배치된 네온 그린 화면이다.
<br>

* 그린스크린은 디지털 효과를 볼 수 있도록 샷의 배경에 배치된 큰 녹색 배경이다. 
<br>

* 포스트 프로덕션에서 특수효과 부서는 CGI 또는 플레이트(plates)라고 불리는 배경 영상을 사용하여 배경을 녹색에서 원하는대로 편집한다.
<br>

* 화면이 녹색일 필요는 없고 항상 녹색인 것은 아니다. 
<br>

* 전자신호가 잘 잡히고 야외촬영에서 효과적이다. Requires less light 

* **녹색**: 디폴트로 디지털 카메라가 사용하기 쉽고, 조명이 적게 들고, 낮에는 성능이 향상되지만, 색상 유출에 어려움을 겪을 수 있다. 
     * ex.금발

<br>
<br>

## 조명
* 사이드 스필라잇 (Side Spill Light) : 초록색이 반사되어 묻지 않도록 떼어주는 조명
* 키 라이트 (Key Light) : 핵심 톤을 설정, 장면의 주요 피사체를 비추기 위함

크로마를 촬영할 땐 조명이 많이 필요해진다.

![조명](https://user-images.githubusercontent.com/112802528/206953012-8e8dd75b-11f9-49f1-8106-5581e83837a5.JPG)

[출처](http://www.magnumco.com/film-lights/the-key-light-what-it-is-how-it-works-and-why-it-matters/)

[출처2](https://www.izzyvideo.com/three-point-lighting/)


<br>
<br>
<br>

# Keyers
* luminance key
![루미너스키](https://user-images.githubusercontent.com/112802528/206954905-5f5dc3e3-8121-41df-9b7e-7be3a56f0bdc.JPG)

감마 수치를 이용하여 알파를 만드는 노드, 그린스크린, 레드스크린의 키잉을 할 수 있다.

keylight 노드 / IBK 노드
[출처](https://learn.foundry.com/nuke/content/reference_guide/keyer_nodes/keyer_nodes.html)

얼티밋 프라이머 - 방송국에서 쓰는 하드웨어와 동일한 방식으로 키를 빼도록 만드는 노드.

IBK - 디퍼런스 키 계열 배우없이 촬영해놓은 그린배경을 기반으로 두 에셋의 차이를 이용해 키를 뺀다.

크로마키어- 크로마 채널을 이용하여 빼는것.

* 목적이 무엇? - 매트를 쉽게 만드는 목적으로 사용한다.

* 키 하나로 안 빠지는 경우, 키라이트를 여러개 만들어서 빼기도 한다. 

* 키 믹스(keymix) 라는 노드로 합쳐주면 온전한 알파 채널을 얻을 수 있다. 


<br>
<br>
<br>


# Hollywood Camera Work
https://www.hollywoodcamerawork.com/

# VFX for filmmakers
https://www.vfxforfilm.com/
102 키에만 관련된 공부과정 두개를 참고하면 좋겠다.


<br>
<br>
<br>

# 키 작업 과정

## Denoise 노드 생성

Denoise 옵션

1. Denoise 양을 많게할거냐
2. 적게할거냐 
3. 얼만큼 되돌릴거냐
4. 부드러운정도는 어느정도로 할거냐

어두운 부분에 샘플링

## Hard key,soft key
* hardkey- 안쪽 내부만 잡는 것
* softkey-외곽 다듬는 것

두개 합치는 방법 = Keymix 노드

소포트 키의 경우 - keymix노드와 roto를 이용해 정리

## 최종  
* hardkey + softkey = Channel Merge 노드를 사용해 합쳐준다.

## 마지막 (추가)
Despill (Gizmo node)키를 뺀 이후 외곽을 회색으로 만들어 주는 노드. 
Despill madness - 얼굴 푸른끼 빼는 노드.


