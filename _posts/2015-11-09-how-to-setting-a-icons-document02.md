---
layout: entry
title: "아이콘용 문서를 생성하는 방법 02"
description: 지난 글에 이어서 아이콘용 문서를 생성하는 방법에 관해 이야기한다. 지난번에는 Slice를 이용해서 문서를 구성하는 비교적 전통적인 방식을 알아봤다면 이번 글에서는 최근에 추가된 기능인 Artboard와 Export As를 사용하는 법을 알아본다. 
---

<small>본론에 들어가기에 앞서, 아이콘은 픽셀 렌더링이 가능한 곳에서 벡터로 그림을 전제로 한다. 따라서 Illustrator는 다루지 않는다.[^related_post] 아래 포스트의 내용은 2015년 11월 2일 당시의 최신 버전인 Photoshop CC 2015.0.1을 기준으로 한다</small>

[지난 글](/2015/10/27/how-to-setting-a-icons-document-01.html)에 이어서 아이콘용 문서에 관해 더 이야기한다. 지난번에는 Slice를 이용해서 문서를 구성하는 비교적 전통적인 방식을 알아봤다면 이번 글에서는 최근에 추가된 기능인 Artboard와 Export As를 사용하는 법을 알아본다. 두 방법이 비슷한 듯하면서도 약간씩 다르므로 두 글을 동시에 켜놓고 비교해보면서 읽어보아도 Photoshop의 세세한 특성들을 이해하는 재미가 있을 것이다.

아이콘 문서의 요건 등 기본적인 내용은 앞선 글에서 이야기했으므로 모두 생략한다. 만약 이전 글을 읽지 않았다면 먼저 읽고 이 글을 읽는 것을 추천한다. 

## 문서 생성하기

1. `Command + N`을 눌러 문서 생성 창을 연다. 
2. `width`와 `height`에 그릴 아이콘의 크기를 입력한다. (아이콘을 여러 개 그릴 계획이라도 아이콘 하나의 크기로 설정한다.) `Background Content`는 `White`로 설정한다.
<img src="/images/2015-11-09/new.png" style="width:677px;">

## 아이콘 레이아웃 잡기
<ol>
  <li>
    <p>24개의 36px 짜리 아이콘을 그린다고 가정하고, 아래와 같이 <a href="http://guideguide.me/" target="blank">GuideGuide</a>로 4행 6열에 상하좌우 간격이 24px인 Guide를 그려준다. 그린 후에는 <code>Command + Shift + ;</code>를 눌러서 Guide를 잠가주는 게 좋다.</p>

    <div class="center">
      <img src="/images/2015-11-09/guide00.png" style="width: 267px;"><img src="/images/2015-11-09/guide01.png" style="width: 326px;">
    </div>
  </li>
  <li>
    <p>Guide가 그려졌다면 현재 문서를 Artboard로 변환한다. Layer 창에서 Background Layer의 Lock 아이콘을 눌러 일반 Layer로 변환한다.</p>
    <div class="center">
      <img src="/images/2015-11-09/lock.png" style="width: 252px;">
      <img src="/images/2015-11-09/unlock.png" style="width: 252px;">
    </div>
  </li>
  <li>
    <p>변환한 Layer를 우클릭 한 후 <code>Artboard form Layers...</code>를 누른다.</p>
      <img src="/images/2015-11-09/artboard00.png" style="width: 525px;">
  </li>
  <li>
    <p>설정 창이 뜨면 Artborad의 이름을 적는다. 이 이름은 나중에 아이콘을 그리면서 일일이 바꿔줘야 하므로 지금은 아이콘 이름의 패턴에만 맞게 적는다. OK 버튼을 누르면 우측 이미지처럼 문서의 상단에 방금 지정한 이름이 나타난다. </p>
    <div class="center">
      <img src="/images/2015-11-09/artboard01.png" style="width: 655px;">
    </div>
  </li>
  <li>
    <p>Artboard Tool<img src="/images/2015-11-09/artboard_tool.png" class="img-text" style="width: 35px;">을 선택한 뒤 문서의 Artboard 이름을 누르거나, Layer창에서 Artboard를 눌러 선택한다. Artboard를 선택하면 Properties 창에 Artboard의 크기와 좌표가 나타난다.</p>
    <div class="center">
      <img src="/images/2015-11-09/select.png" style="width: 325px;"><img src="/images/2015-11-09/properties.png" style="width: 230px;">
    </div>
  </li>
  <li>
    <p><code>command + alt + shift</code> 키를 누른 채로 좌측 방향키<code>➔</code> 를 연속으로 누르거나 <code>alt</code>를 누른채로 Artboard를 드래그해서 좌측의 Guideline에 맞게 복사한다. 드래그를 해서 움직일 때는 간혹 x, y 좌표가 정확히 맞지 않으므로 Properties 창에 정확한 좌푯값을 입력한다. (지금 단계에서는 복사한 Artboard의 이름을 수정할 필요가 없다. 하지면 여기서는 설명을 위해서 "icon02"로 수정했다.)</p>
    <img src="/images/2015-11-09/copy.png" style="width: 453px;">
  </li>
  <li>
    <p>모든 Guide에 맞게 Artboard를 복사한다. 복사할 때는 하나씩 하지 않고 생성된 모든 아트보드를 복사하는 식으로 늘려나간다.</p>
    <img src="/images/2015-11-09/artboards.png" style="width: 499px;">
  </li>
</ol>

##무한한 단색 공간 만들기
<ol>
  <li>
    <p>이제 문서 생성은 끝났다. Move Tool<img src="/images/2015-11-09/artboard_tool.png" class="img-text" style="width: 35px;">을 선택한 상태로 Artboard 바깥 영역을 우클릭한다. 아래와 같이 Standard Screen Mode의 색상을 변경할 수 있는 창이 뜨면 <code>Select Custom Color</code>를 선택한다.</p>
    <img src="/images/2015-11-09/screen_mode00.png" style="width: 610px;">
  </li>
  <li>
    <p>
      <code>Select Custom Color</code>를 선택하면 Color Picker가 뜨는데 흰색<code>#FFFFFF</code>을 선택하면 아래와 같이 Artboard와 그 바깥 영역의 색이 같아졌다.
    </p>
    <img src="/images/2015-11-09/screen_mode01.png" style="width: 529px;">
  </li>
</ol>

<hr>

하지만 여기서부터 Artboard를 사용하는 방법의 치명적인 단점이 나타나는데 바로 저 Artboard의 이름과 외곽선을 지울 수 없다는 점이다.

<img src="/images/2015-11-09/name_border.png" style="width: 1053px;">

위 이미지에서 보다시피 아이콘 주변에 UI 요소가 있고 없음은 보기에 꽤 큰 차이가 있다. 어설프게나마 이 UI 요소를 안 보이게 하는 방법이 있는데 아래 내용에서 더 알아보도록 한다.

##모든 Artboard의 배경색을 한번에 바꾸기<br>(UI요소 숨기기)

Artboard는 각각 독립적이다. 즉 한 Artboard에서 Solid Color Layer[^SolidColorLayer]를 생성하면 Solid Color가 적용되는 곳은 전체가 아닌 해당 Artboard 뿐이다.

<img src="/images/2015-11-09/color_change.png" style="width: 453px;">

이런 식이라면 전체 아이콘 세트의 배경색을 바꿔보고 싶을 땐 모든 Artboard의 Solid Color Layer를 바꿔줘야 한다. 내가 원하는 것은 한번의 클릭으로 전체 아이콘의 배경색을 바꾸는 것이므로 모든 Artboard를 아우르는 Solid Color Layer를 만들어야 한다.

<ol>
  <li><p>모든 Artboard를 덮는 큰 Artboard를 생성한다.</p>
  <img src="/images/2015-11-09/background.png" style="width: 714px;">
  </li>
  <li>
    <p>새로 만든 Artboard의 이름을 Background로 바꾸고, Artboard 순서를 제일 밑으로 옮긴 후 Background Artboard의 Layer 1을 선택한 상태에서 Solid Color Layer를 생성한다.</p>
    <div class="center">
      <img src="/images/2015-11-09/artboard_order.png" style="width: 252px; vertical-align: top;">
      <img src="/images/2015-11-09/background01.png" style="width: 282px;">
    </div>
  </li>

  <hr>

  이미 Standard Screen Color가 Solid Color Layer처럼 작동하고 있으므로 왜 굳이 Solid Color Layer를 만들었는지 궁금할 것이다. Solid Color Layer를 만든 이유는 Artboard의 이름과 Outline이 Standard Screen Color에 맞춰 작동하기 때문이다.

  <img src="/images/2015-11-09/bg_color.png" style="width: 989px;">

  위 이미지에서와같이 Standard Screen Color가 밝은색이면 UI 컬러는 어두운색, Standard Screen Color가 어두운색이면 UI 컬러는 밝은색으로 나타난다. 이 점을 역 이용해서 Background Artboard를 밝은 배경으로 설정해두고 Standard Screen Color를 어두운색으로 설정하면 (밝은색 위에 밝은색으로 표기되기 때문에) Artboard UI Color가 보이지 않게 된다.

  <hr>

  <li>
    <p>
      생성한 Solid Color를 흰색으로, Standard Screen Color를 검은색으로 설정한다.
    </p>
    <div class="center">
      <img src="/images/2015-11-09/bg_white.png" style="width: 680px;">
      <img src="/images/2015-11-09/bg_black.png" style="width: 680px;">
    </div>
    <p>ta da! Artboard UI가 사라졌다.</p>
  </li>
  <li>
    <p>
      검은 배경을 보고 싶다면 반대로 Solid Color Layer는 검은색, Standard Screen Color는 밝은 회색으로 설정한다.
    </p>
    <img src="/images/2015-11-09/bg_dark.png" style="width: 699px;">
  </li>
</ol>

<hr>

안타깝게도 이 방법으로 Artboard UI를 없애는 데는 한계가 있다. UI Color는 무채색에, 일정 명도로만 표기되므로 그에 딱 맞는 배경색이 아니라면 완벽하게 사라지게 할 수 없기 때문이다. 그러나 대체로 흰색 배경 위에서 아이콘을 그리며 유채색 위에서 볼 때는 최종 아이콘의 느낌을 확인하는 용도로만 사용하므로 아이콘 그리기에 어느 정도 익숙해졌다면 큰 지장은 없다.


## Export As로 아이콘 저장하기

<ol>
  <li>
    <p>아이콘을 다 그렸다면 저장하기 전에 Background Artboard의 Solid Layer의 눈을 꺼준다. 배경이 투명으로 저장되게 하기 위함이다.</p>
    <img src="/images/2015-11-09/eyeoff.png" style="width: 252px;">
  </li>
  <li>
    <p>추출하려는 아이콘 Artboard를 모두 선택한다.</p>
    <img src="/images/2015-11-09/selectall.png" style="width: 742px;">
  </li>
  <li>
    <p>
      Layer 창에서 우클릭 한 후 <code>Quick Export as PNG</code>를 선택한다.
    </p>
    <img src="/images/2015-11-09/quickpng.png" style="width: 343px;">
  </li>
  <li>
    <p>
      아이콘 추출 파일을 저장하려는 디렉토리를 선택한 뒤 <code>Open</code> 버튼을 누른다.
    </p>
    <img src="/images/2015-11-09/quicksave.png" style="width: 866px;">
  </li>
  <li>
    <p>
      아이콘 전체를 SVG로 저장하려면 <code>File</code>><code>Export</code>><code>Export Preferences...</code>로 들어간다.</p>
    <img src="/images/2015-11-09/exportpref.png" style="width: 552px;">
  </li>
  <li>
    <p><code>Quick Export Format</code>의 값을 <code>SVG</code>로 변경한 뒤 위의 3, 4번 과정을 반복한다.</p>
    <img src="/images/2015-11-09/format.png" style="width: 436px;">
  </li>
  <li>
    <p>
      모든 Artboard가 SVG로 추출되었다.
    </p>
    <img src="/images/2015-11-09/svg.png" style="width: 760px;">
  </li>
</ol>

<hr>

Photoshop CC 2015 이전 버전에서는 SVG로 추출하는 것이 거의 불가능 했기 때문에 SVG Export를 지원은 Artboard의 큰 장점이다. 하지만 보다시피 Slice처럼 파일 이름의 패턴을 지정할 수는 없다. [Slice를 사용해서 Save for Web으로 저장하는 방법](/2015/10/27/how-to-setting-a-icons-document-01.html)과 Artboard를 사용해서 Export As로 추출하는 방법 모두 장단점이 있으니 각자의 성향이나 작업 환경에 따라 적절히 활용해서 사용하길 바란다.

[^related_post]: 관련 포스트: [아이콘 그리기 Photoshop or Illustrator?](/2014/07/28/psd-or-ai.html)
[^SolidColorLayer]: Solid Color Layer에 대한 설명은 [이 포스팅](/2015/10/27/how-to-setting-a-icons-document-01.html)을 참조한다.
