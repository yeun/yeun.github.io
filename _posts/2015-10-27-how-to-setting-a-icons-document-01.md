---
layout: entry
title: "아이콘용 문서를 생성하는 방법 01"
description: 아이콘을 그릴 때 생성하는 문서에 관해 이야기한다. 문서야 그냥 생성하면 되지 않느냐고 할 수 있지만 조금만 신경 써서 문서를 생성하면 아이콘을 관리하거나 추출할 때 무척 편리하다. 
---

<small>본론에 들어가기에 앞서, 아이콘은 픽셀 렌더링이 가능한 곳에서 벡터로 그림을 전제로 한다. 따라서 Illustrator는 다루지 않는다.[^related_post] 아래 포스트의 내용은 2015년 10월 27일 당시의 최신 버전인 Photoshop CC 2015.0.1을 기준으로 한다</small>

오늘은 아이콘용 문서를 생성하는 방법에 대해 이야기해보려고 한다. <q>아이콘용 문서</q>라는 특정한 용도를 염두에 두고 문서 생성을 하는 게 일반적인지는 잘 모르겠다. 다만 -UI 디자인 중에 가장 많이 반복한 단일 작업이 아이콘 그리기였던- 내 경우엔 몇가지 설정을 처음부터 하지 않아서 후에 귀찮은 반복 작업을 해야 하는 일이 많았고, 그래서 아이콘을 그릴 문서는 이러이러해야 뒤탈(?)이 없다는 사소한 노하우가 생겼다. 물론 그냥 문서를 생성해서 아이콘을 그린다고 큰 문제가 되는 것은 아니다. 하지만 아래 내용을 지켜 문서를 생성한다면 정렬이 1px만 흐트러져도 정신 건강을 해치고야 마는 심약한 디자이너들에게 도움이 되리라 생각한다.

## 아이콘용 문서의 요건

아이콘용 문서가 충족해야 하는 조건은 다음과 같다.

##### 아이콘 간의 조화를 쉽게 파악할 수 있어야 한다.
아이콘은 하나만 두고 보는 것보다 전체를 놓고 보았을 때 디자인에서 느껴지는 분위기를 파악하기 쉽다. 아이콘 각각에 모든 스타일(특징)을 담을 수 없으며, &times;, <, > 등의 기본적인 아이콘은 스타일이 달라도 대동소이하기 때문이기도 하다. 그러므로 아이콘 각각이 독립된 문서이거나 아이콘 사이를 툴의 interface가 간섭한다면 곤란하다. 

##### 문서의 크기가 확장 가능해야 한다.
20개의 아이콘 세트를 그렸는데 다시 추가로 10개를 더 그려야 하는 일이 생각보다 왕왕 발생한다. 따라서 아이콘 문서의 확장이 쉬워야 한다.

##### 각각의 아이콘을 추출하기 편리해야 한다.
아이콘을 그린 후 Layer를 하나하나 Export 시키는 일은 고역이다. 아이콘을 그린 문서는 항상 Export가 쉬워야 한다. 이때 아이콘을 이루는 벡터 크기가 아닌 사용자가 지정한 크기, 즉 여백을 포함한 크기로 자동 추출이 가능해야 한다. 

##### 문서의 배경 색과 아이콘의 색을 쉽게 변경할 수 있어야 한다.
상황에 따라 아이콘이 놓이는 배경색은 다르다. 흰 배경 위에 검은색의 아이콘일 때는 괜찮아 보였던 형태도 검은 배경 위에서 보면 어딘가 어색할 수 있다. 그러므로 배경색과 아이콘 색의 모든 경우를 확인하기 쉬워야 한다.

그럼 위 조건을 문서를 생성하는 법을 알아보자.

## 문서 생성하기

1. `Command + N`을 눌러 문서 생성 창을 연다. 
2. 생성할 문서의 `width`와 `height`를 입력한다. width는 400 - 500px, height는 300px 이상이면 적당하다. 문서 사이즈는 나중에 다시 바꿔줘야 하므로 이 단계에서는 대강 입력한다. <strong>`Background Content`는  `Transparent`로 설정한다.</strong>
<img src="/images/2015-10-23/new.png" style="width:667px;">
3. OK 버튼을 눌러 문서를 생성했다면 디폴트로 생성된 `Layer 1`이 선택된 상태에서 `Layers` 창 가운데 반달 모양 버튼을 눌러 `Solid Color Layer`를 생성한다. `Solid Color Layer` 옵션을 누르면 Color Picker가 뜰 텐데 아이콘의 배경색으로 사용할 색을 지정한다. 보통 흰색`#FFFFFF`을 선택한다.
<img src="/images/2015-10-23/solid_color00.png" style="width:352px;">
4. 기존에 있던 `Layer 1`이 `Color Fill 1`으로 바뀌었으며 문서의 배경에도 색이 채워졌다.

<div class="center">
  <img src="/images/2015-10-23/solid_color01.png" style="width:252px;"><img src="/images/2015-10-23/solid_color02.png" style="width:318px;">
</div>

<hr>

### 왜 Solid Color Layer를 사용할까?

배경에 색을 넣는 용도로 `Solid Color Layer`를 사용하는 이유는 앞서 이야기한 <q>확장 가능한 문서 크기</q>와 <q>쉽게 바꿀 수 있는 배경색</q> 때문이다. 아래는 각각 `Background Content`를 `White`로 생성한 문서와 `Solid Color Layer`를 사용한 문서의 Canvas Size를 확장한 이미지이다.

<div class="center">
  <img src="/images/2015-10-23/BG00.png" style="width: 345px;">
  <img src="/images/2015-10-23/BG01.png" style="width: 345px;">
</div>

`Background Content`를 `White`로 생성한 문서는 새로 확장된 영역의 배경색이 `Background color`<img src="/images/2015-10-23/FG_BG.png" class="img-text" style="width: 35px;"> 로 들어간다. 반면 `Solid Color` 로 배경색을 채운 문서는 문서의 크기를 얼마나 어떤 방식으로 변경하든 배경색이 일정하게 유지된다. 

배경색을 바꾸는 것도 후자가 더 쉽다. 

- `Background Content`를 `White`로 생성한 문서의 배경색을 바꿀 때
  1. `Paint Bucket Tool`을 선택한다.
  2. `Foreground color`를 더블 클릭한다.
  3. Color Picker에서 배경에 적용할 색을 선택한다.
  4. Background<img src="/images/2015-10-23/bg_layer.png" class="img-text" style="width: 181px;"> Layer를 선택한다.
  5. 배경에 `Paint Bucket Tool`로 색을 붇는다.

- `Solid Color Layer`를 사용한 문서의 배경색을 바꿀 때
  1. `Solid Color Layer`의 `Layer Thumbnail`을 더블 클릭한다.
  2. Color Picker에서 원하는 색을 선택한다.

앞선 경우에선 다섯 단계를 거쳐야 하는 일이 `Solid Color Layer`를 사용하면 두 단계로 줄어든다. 그럼 다시 본론으로 들어가서 문서를 계속 생성해보자.

<hr>

## 아이콘 레이아웃 잡기

아이콘의 배경색을 채웠다면 이번에는 Guide를 그릴 차례다. 아이콘은 적당한 간격을 두고 가로나 세로가 약간 긴 직사각형에 가깝게 정렬되어 있어야 보기 좋다.

<div class="center">
  <img src="/images/2015-10-23/align00.png" style="width: 350px;"><img src="/images/2015-10-23/align01.png" style="width: 300px;">
</div>

그러므로 그리고자 하는 아이콘의 개수가 10개라면 2&times;5, 30개라면 5&times;7 정도로 행렬을 맞춘다. 만약 아이콘을 한번 그리는 데서 그치지 않고 앞으로도 개수가 계속 늘어날 예정이라면 열의 수를 7에서 8 정도로 맞추고 행을 계속 늘려나가도록 한다. (가로 스크롤보다 세로 스크롤이 쉽기 때문이다.) 

아이콘 사이의 간격은 20px - 40px 정도가 안정적이며 아이콘의 크기 대비 2/3로 설정하는 게 편하다. 예를 들어 아이콘 크기가 36px이라면 아이콘 사이의 간격을 24px로 정한다. 여기에 Gridline을 아이콘의 1/3 인 12px 간격으로 설정하면 아이콘의 크기와, 여백의 크기, Gridlined의 간격이 공배수 관계이기 때문에 매번 zero point를 바꿔줄 필요가 없다.

<ol>
  <li>
    <p>24개의 36px 짜리 아이콘을 그린다고 가정해본다. 따라서 <a href="http://guideguide.me/" target="blank">GuideGuide</a>로 4행 6열에 상하좌우 Margin이 60px, Gutter가 24px인 Guide를 그려준다. 그린 후에는 <code>Command + Shift + ;</code>를 눌러서 Guide를 잠가주는 게 좋다.</p>
    <div class="center">
      <img src="/images/2015-10-23/guide00.png" style="width: 253px;"><img src="/images/2015-10-23/guide01.png" style="width: 400px;">
    </div>
  </li>
  <li>
    <p>Guide를 그려보니 전체 문서의 크기가 원하는 것보다 약간 작다. <code>Crop Tool</code>을 사용해서 문서의 크기를 Guide에 맞게 늘려준다.</p>
    <img src="/images/2015-10-23/crop.png" style="width: 410px;">
  </li>
</ol>

## 무한한 단색 공간 만들기

1. `Command + ;`를 눌러 Guide를 끄면 흰색 문서와 회색의 Standard Screen Mode Color가 보인다. 이 회색 배경을 우클릭 해서 `Select Custom Color`를 선택한다.
<img src="/images/2015-10-23/custom_color.png" style="width: 590px;">

2. Color Picker가 열리면 배경색과 같은 색(`#FFFFFF`)을 선택한다. 그럼 아래 그림과 같이 문서의 경계가 보이지 않는 흰색 공간을 얻을 수 있다.
<img src="/images/2015-10-23/white.png" style="width: 484px;">

3. 만약 문서의 경계에 그림자나 선이 보인다면 `Command + K`를 눌러 Preferences 창을 켠 뒤 `Interface`>`Appearance`>`Select Custom Color`>`Boder`의 설정을 `None`으로 바꿔준다.
<img src="/images/2015-10-23/border.png" style="width: 479px;">

<hr>

여기까지 했다면 아이콘을 그리기 시작하면 된다. 여기서는 이미 아이콘을 다 그린 셈 치고 아이콘을 추출하는 법을 설명 할 텐데 그 전에 유감스러운 현재 상황을 먼저 이야기해야겠다.

현재 아이콘을 추출하는 방법은 크게 세 가지이며, 각각 단점이 있다.

##### Slice를 사용해서 `Save for Web`으로 저장한다.
- Slice를 일일이 만들기 귀찮다.
- `Save for Web`은 Update 계획이 없으며 기능이 언젠가 사라질 수 있다.[^adobe_support]

##### 각 Layer 혹은 Group에 `Export As`로 저장한다.
- `Export As`는 여백을 저장하지 못한다.

##### Artboard에 `Export As`로 저장한다.
- Artboard Name과 border를 Interface 상에서 숨길 수 없다.

Photoshop은 CC 2015부터 `Export As` 기능을 제공하고 있다. 이 기능의 가장 좋은 점은 SVG로 저장할 수 있다는 점이다. 이전 버전의 Photoshop에서는 SVG Export를 제공하지 않았기에 Vector Shape을 항상 Illustrator로 옮겨서 저장해야만 했다. 따라서 SVG 파일이 필요하다면 `Export As`를 쓰지 않을 수 없다. 하지만 이 기능은 여백을 자동으로 제거한다. (당연히 Slice도 지원하지 않는다.)
<img src="/images/2015-10-23/export_as.png" style="width: 780px;">

Artboard는 추출도 쉽고 여백까지 저장되지만 아래 이미지와 같이 Artboard Name과 Border를 숨길 수가 없다. 
<img src="/images/2015-10-23/artboard.png" style="width: 525px;">
아이콘은 그 크기가 작으므로 1, 2px도 무척 민감하게 느껴지므로 Zoom에 상관없이 일정한 굵기와 크기를 가진 interface가 항상 나타나 있다는 것은 치명적이다.

따라서 여기서 소개할 방법은 여백도 저장되면서 GUI가 시야를 방해하지 않는, <q>Slice를 사용해서 `Save for Web`으로 저장</q>하는 방법이다. Slice Tool은 `Export As`에 비하면 구시대의 유물과도 같은 느낌이지만 한번 만들어두면 손쉽게 전체 아이콘을 저장할 수 있고, Layer의 내용에 상관없이 사용자가 지정한 크기대로 추출해준다는 강점이 있다.

## Slice를 만들어서 PNG로 저장하기

1. `Slice Tool`을 선택해서 Slice를 Guide에 맞게 그린다. (`Slice Tool`은 `Crop Tool`을 오래 눌러 생기는 메뉴 창에 있다.) 아이콘을 다 그린 후라면 Guide와 동시에 아이콘 shape에도 snap이 작용하므로 모든 Layer의 눈을 끈 뒤에 Slice를 그려야 편하다.
<img src="/images/2015-10-23/slice00.png" style="width: 574px;">

2. Slice를 모두 그렸다면 `Slice Tool`이 선택되어있는 상태에서 Slice를 더블 클릭해서 Slice Options를 연다. Slice의 활성화가 풀렸다면 `Command`를 눌러 다시 Slice를 선택할 수 있다. Name 란에 그린 아이콘의 이름을 써넣는다. `Slice Background Type`는 `None`으로 설정한다. 이와 같은 방법으로 모든 아이콘의 Slice Name을 저장한다. 
<img src="/images/2015-10-23/archive00.png" style="width: 569px;">

3. Solid Color Layer의 눈을 끈 뒤 `File`>`Export`로 들어가서 `Save for Web`을 선택한다. 또는 단축키 `Command+ Shift + Alt + S`를 눌러서 `Save for Web`을 연다. `Preset`은 `PNG-24`로 설정하고 `Transparency`에 체크가 되어있는지 확인한다. 만약 아래 이미지처럼 Slice 배경이 투명하지 않다면 전체 Slice를 선택한 뒤 다시 `Preset`을 `PNG-24`로 설정한다. 모든 설정을 마치면 `Save` 버튼을 누른다.
<img src="/images/2015-10-23/save00.png" style="width: 1073px;">

4. `Save Optimized As` 창이 뜨면 `Slices`에서 `All User Slices` 옵션을 선택한다.
<img src="/images/2015-10-23/save01.png" style="width: 508px;">

5. 그 후 `Settings`에서 `Other...` 옵션을 눌러서 아이콘의 이름을 저장하는 방식을 설정한다. 될 수 있으면 `Filename Compatibility`는 모두 체크한다.
<img src="/images/2015-10-23/save02.png" style="width: 633px;">

6. 모든 설정을 마친 후 `Save`를 누르면 아래 이미지와 같이 질서 정연하게 뽑힌 아이콘 PNG 파일이 저장된다.
<img src="/images/2015-10-23/finish.png" style="width: 800px;">

---

이렇게 Slice를 사용해서 아이콘 문서를 생성하고 저장하는 법을 살펴봤다. 현재로는 이 방법이 최선이라고 생각하지만, SVG 파일로 Export 할 수 없고, Save for Web 기능이 언제 사라질지 모르므로 Artboard나 Export As 기능을 사용해서 추출하는 방법도 알고는 있어야 한다. 이 방법은 다음 포스트에서 다루어보겠다.


[^related_post]: 관련 포스트 [아이콘 그리기 Photoshop or Illustrator?](/2014/07/28/psd-or-ai.html)

[^adobe_support]: [Save for Web in Photoshop CC 2015](http://blogs.adobe.com/crawlspace/2015/06/save-for-web-in-photoshop-cc-2015.html)

