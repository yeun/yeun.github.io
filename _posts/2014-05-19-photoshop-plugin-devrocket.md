---
title: "Photoshop Extension: DevRocket"
layout: entry
description: Photoshop에서 iOS 디자인을 효과적으로 보조하는 DevRocket을 소개한다.
---

<small>이 글은 [스포카 테크 블로그](http://spoqa.github.io/2014/05/19/photoshop-plugin-1.html)에 기재한 글을 옮겨와 다듬은 포스트이다. 2014년 5월 19일 당시 최신 버전인 Photoshop CC 2014.2를 기준으로 작성되었다.</small>

[Dev Rocket](http://devrocket.uiparade.com/)은 아마 iOS 디자인을 하시는 분들은 많이 알고있을 것이다. 모바일 UI를 디자인 하다보면 각 디바이스 사이즈에 맞게 새 문서를 생성하고 리소스를 자르고, 리사이징하는 등 반복 작업이 많은데 그런 업무를 수월하게 해주는 Extension이다. 몇 번의 버젼 업데이트를 하면서는 `Refills`와 같은 효과적인 부가 기능도 지원하고 있다. 생김새는 아래와같다.

<img src="/images/2014-05-19/DevRocket_GUI.png" style="@include resize(385px); width: 385px; height: auto; margin: auto;">

1. Refills
2. Ui Snips
3. Layout Guides
4. Mini Mode
5. View Templates
6. Icon Templates
7. Preview Design
8. Export Assets
9. View Mode (Standard Mode, Retina Mode)

내가 특히 자주 쓰는 기능은 `1` `2` `5` `8` `6` `9` 이다. 

## 1. <img src="/images/2014-05-19/DevRocket_Refills.png" class="img-text" style="width: auto;">Refills

제작자, [Norm](https://dribbble.com/Norm)이 야심차게 만든 기능, Refills이다. 간단히 설명하자면 버튼이나 아이콘 이미지, 브라우저 기본 UI 등 반복적으로 쓰이는 에셋을 저장해 놓고 바로 가져다가 쓸 수 있도록 하는 일종의 shotcut 메뉴라고 할 수 있다.
Refills 버튼을 누르면 아래와 같은 창이 나타난다.

<img src="/images/2014-05-19/DevRocket_Refills01.png" style="width: 304px; height: auto; margin: auto;">

이 상태에서 세번째의 Library<img src="/images/2014-05-19/DevRocket_Refills02.png" class="img-text" style="width: 25px;">버튼을 누르면 Refill을 추가할 수 있는 UI가 나타난다. 아래 이미지는 Refill Store에서 iOS7 Refill을 다운 받아서 적용한 모습이다.

<img src="/images/2014-05-19/DevRocket_Refills03.png" style="width: 304px; height: auto; margin: auto;">

여기서 원하는 Refill을 드래그 앤 드롭해서 작업하는 문서에 내려놓으면 바로 레이어가 생성한다.

Refills는 사람들이 Refills Store에 올려놓은 에셋을 구매해서 사용할 수도 있고, 자기가 만든 것을 바로 업로드해서 사용할 수도 있다. 위의 예시처럼 각 플랫폼의 UI, 회사의 로고, 브랜드 아이덴티티 등을 저장해놓고 사용하면 무척 편리하다. [Refills](http://pixeldropr.com/refill-readr.html)은 특별하게 기능만 따로 떼어내서 무료로도 제공하고 있다.


## 2. <img src="/images/2014-05-19/DevRocket_UISnips.png" class="img-text" style="width: auto;">UI Snips

모든 Extension을 통틀어 가장 자주 쓰는 기능이다. (체감상으로는 이 기능만으로도 $19의 값을 충분히 한다.)

레이어를 선택하고 이 버튼을 누르면 그 레이어 사이즈 맞게 새 문서로 추출된다. 포토샵의 `Duplicate Layer`>`Destination`:`New Document`와 비슷한 기능이지만 `UI Snips`는 여백이 없는 새 문서에 레이어를 뽑아준다는 점이 다르다. 이 버튼 하나만 누르면 레이어를 깔끔히 추출해주는 편리함은 이루 말할 수가 없다! CC부터는 포토샵 자체적으로 저장까지 한번에 되는 `Generate`>`Image Asset`기능을 제공하고 있는데, 이것도 아주 유용한 기능이지만 폴더 관리법이나 에셋을 수정하는 상황에 따라 적절하지 않을 때가 있어서 여전히 애용하고 있다.


## 3. <img src="/images/2014-05-19/DevRocket_Layoutguides.png" class="img-text" style="width: auto;">Layout Guides

<img src="/images/2014-05-19/DevRocket_Layoutguides01.png" style="width: 380px; height: auto; margin: auto;">

위와 같이 iOS 문서에 맞는 가이드를 그려주는 기능이다. 나는 거의 모든 가이드를 [GuideGuide](http://www.guideguide.me/)로 그리고 있기에 사용 빈도는 높지 않지만, <img src="/images/2014-05-19/DevRocket_ViewTemplates.png" class="img-text" style="width: 112.5px;"> View Templates 기능으로 템플릿을 생성한 후에 별 고민 없이 가이드를 그리고 싶을 때 편리하다.

## 4. <img src="/images/2014-05-19/DevRocket_Minimode.png" class="img-text" style="width: auto;">Mini Mode

<img src="/images/2014-05-19/DevRocket_Minimode01.png" style="width: 304px; height: auto; margin: auto;">

Dev Rocket 창을 최소화시켜준다. `UI Snips` `Layout Guides` `View Mode` `Preview Design` 기능을 제공한다. 하지만 UI Snips을 제외한 세가지 기능은 잘 쓰지 않아 그다지 유용한 기능은 아니라고 생각한다.


## 5. <img src="/images/2014-05-19/DevRocket_ViewTemplates.png" class="img-text" style="width: 225px;"> View Templates

매번 업데이트되는 디바이스 사이즈를 외우거나, 일일히 찾아보는 것도 은근히 시간을 잡아먹는다. `View Templates`은 이런 귀찮음을 해소시켜 준다. 심지어 가로/세로, 레티나까지 모두 지원하고 이렇게 생성한 문서에는 기본적으로 `Status Bar`, `Nav Bar`, `Tab Bar` 레이어를 제공한다.

<div style="text-align: center;">
<img src="/images/2014-05-19/DevRocket_ViewTemplates01.png" style="width: 304px; height: auto; padding-right: 0; padding-left: 0; display: inline-block; vertical-align: top;">
<img src="/images/2014-05-19/DevRocket_ViewTemplates02.png" style="width: 300px; height: auto; padding-right: 0; padding-left: 0; display: inline-block;">
</div>

이 기능이 너무 편리한 탓에 기기 사이즈를 종종 까먹는 부작용이 발생하곤 하지만... UI Snips 다음으로 자주 사용하는 기능이다.

## 6. <img src="/images/2014-05-19/DevRocket_IconTemplates.png" class="img-text" style="width: 225px;"> Icon Templates

`View Templates`과 비슷한 기능으로써 모든 아이콘 사이즈를 간편하게 리사이징 할 수 있게 해주는 기능이다. 이 버튼을 누르면 아래와 같은 문서가 생성된다.
<img src="/images/2014-05-19/DevRocket_IconTemplates01.png" style="width: 100%;">

가장 큰 아이콘인 `MASTER ARTWORK - DOUBLE CLICK TO EDIT`레이어를 수정하면 모든 아이콘에 그 이미지가 반영된다. 하지만 iOS7의 모서리 곡률이 반영되어 있지 않고 아이콘 그리드 시스템을 따로 가이드해주고 있지 않아서 최근에는 잘 사용하지 않는다.

대신 같은 방식이지만 iOS7 용으로 추천드릴 만한 Icon Templates은 [M18](https://dribbble.com/shots/1111035-Template-for-iOS-7-App-Icons?list=searches&tag=m18&offset=0)과 [Pixel Restart](http://appicontemplate.com/) 가 있다.


## 7. <img src="/images/2014-05-19/DevRocket_Previewdesign.png" class="img-text" style="width: 225px;"> Preview Design

<img src="/images/2014-05-19/DevRocket_Previewdesign01.png" style=" width: 519px; height: auto; margin: auto;">

디자인한 UI의 Preview를 보여준다. 이 기능은 [Skala Preview](http://bjango.com/mac/skalapreview/)로 대체되기 때문에 잘 사용하지 않지만 Windows 사용자거나 iOS 기기를 가지고 있지 않다면 간단하게 느낌만 살펴보기 유용할 것이다.


## 8. <img src="/images/2014-05-19/DevRocket_ExportAssets.png" class="img-text" style="width: 225px;"> Export Assets

이 기능은 `UI Snips`에서 잠깐 언급했던 `Generate`>`Image Asset`과 매우 유사한 기능이다.

- `Image Asset` 체크를 해두면 따로 확인하는 과정 없이 이미지 리소스가 자동적으로 저장 됨
- `Export Assets` 버튼을 눌러서 이미지를 저장 됨

`Export Assets` 버튼을 누르면 다음과 같이 모든 레이어를 Export 할 것인지, 선택된 레이어만 Export할 것인지를 묻는다.

<img src="/images/2014-05-19/DevRocket_ExportAssets01.png" style="width: 304px; height: auto; margin: auto;">

선택을 하면 이번에는 어떤 해상도로 Export 할지를 묻는다. 원하는 해상도를 선택하면 오른쪽 이미지처럼 예쁘게 정리해서 레이어들을 추출해준다.

<div style="text-align: center;">
<img src="/images/2014-05-19/DevRocket_ExportAssets02.png" style="width: 304px; height: auto;display: inline-block;">
<img src="/images/2014-05-19/DevRocket_ExportAssets03.png" style="width: 150px; height: auto; display: inline-block; vertical-align: top; padding-top: 34px;">
</div>

Group 속의 레이어들은 Merge해서 추출해 주는 등 몇가지 규칙들이 있지만, 알아두면 레이어 정리를 깔끔히 할 때 아주 강력한 기능이다.

## 9. <img src="/images/2014-05-19/DevRocket_Viewmode01.png" class="img-text" style="width: auto;"><img src="/images/2014-05-19/DevRocket_Viewmode02.png" class="img-text" style="width: auto;">View Mode

비 레티나(Standard)와 레티나 뷰로 전환시켜주는 기능이다.

<div class="center">
  <img src="/images/2014-05-19/DevRocket_Viewmode01.png" class="img-text" style="width: 25px;"> Standard Mode 
  <img src="/images/2014-05-19/DevRocket_Viewmode01.png" class="img-text" style="width: 25px;"> Retina Mode
</div>

위의 버튼을 누르면 포토샵에서 `Image`>`Image Size`:`200%` or `50%` 한 것과 같이 문서 크기를 조정한다. 하지만 최근에는 3GS를 거의 신경쓰지 않는 추세라 자주 사용하진 않는다. 대신 화면 해상도와 상관없이 작업하던 문서를 200% 확대하거나 50% 축소하고 싶을 때 사용한다.

