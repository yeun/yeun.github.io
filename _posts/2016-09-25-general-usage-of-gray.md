---
layout: entry
title: Open color 회색의 사용법
description: 며칠 전 Open color를 공개했기에 홍보 겸 간단한 설명서 겸 컬러 스킴 제작과 용처에 관한 글을 써야겠다고 계획하고 있었다. 오늘은 그중 가장 쉽게 읽히면서도 실용성이 높은 주제인 회색 사용법을 풀어보려고 한다.
publish: true
---

며칠 전 [Open color](https://yeun.github.io/open-color/)를 공개했기에 홍보 겸 간단한 설명서 겸 컬러 스킴 제작과 용처에 관한 글을 써야겠다고 계획하고 있었다. 오늘은 그중 가장 쉽게 읽히면서도 실용성이 높은 주제인 회색 사용법을 풀어보려고 한다. 

### 회색 스펙트럼의 구성

UI에서 명도는 때로 의미를 내포한다. 마우스를 올렸을 때 짙어지는 요소는 클릭할 수 있음을 암시하고, 유독 밝은 회색의 텍스트는 비활성, 혹은 만료를 나타내기도 한다. Open color의 회색은 다른 색상들과는 달리 이런 용도를 염두에 두고 제작되었기 때문에 각 단계의 명도 차이가 일정하지 않다. 아래는 이미지는 오픈컬러의 회색 스펙트럼이다.

![open-color-gray](/images/2016-09-25/open-color-gray.png){:width="729px"}

자세히 보면 gray 0, gray 1, gray 2의 색 차이는 무척 근소하고 gray 6과 gray 7은 눈에 띄게 차이가 난다. 각각 어디에 쓰이는 것을 상정한 색상인지 아래에서 실례와 함께 용도를 보자.

### 텍스트

본문 텍스트 컬러에는 gray 7이나 gray 8을 사용한다. Gray 7은 부드러운 느낌이 나며, 배경과 자연스럽게 어우러진다. 메뉴 레이블, 버튼 텍스트 등 기능적인 UI 요소에 적절하다. 반면 블로그나 SNS, 헤드라인 등 콘텐츠가 강조되는 곳에서는 글씨가 배경과 또렷이 구분되는 8번이 적합하다.

<div class="center">
  <div class="color-gray-7">
    Gray 7을 적용한 텍스트
  </div>
  <div class="color-gray-8">
    Gray 8을 적용한 텍스트
  </div>
</div>

텍스트에는 검은색 뿐만 아니라 회색도 빈번히 사용된다. 회색 텍스트는 주요한 텍스트보다 강조하지 않으려고 옅게 처리한 것과 비활성 상태를 나타내는 것으로 나뉜다. 전자의 예시는 랜딩페이지의 헤드라인 밑에 불어있는 설명이나, 메타 데이터 등에서 볼 수 있다. 본문 텍스트보다는 옅지만, 비활성으로 느껴질 만큼 옅지 않기 때문에 사용자에게 중요하지 않은 정보, 혹은 부연 설명 정도로 인식된다. 이런 텍스트에는 gray 6을 사용한다. 반면 폼이나 버튼, 링크 등이 비활성임을 나타내는 텍스트에는 gray 5가 적절하다.

<div class="center">
  <div class="color-gray-6">
    Gray 6을 적용한 텍스트
  </div>
  <div class="color-gray-5">
    Gray 5를 적용한 텍스트
  </div>
</div>
<p></p>
{% highlight scss linenos %}// Text
$text-color:         $oc-gray-7;
$text-color-crisp:   $oc-gray-8;
$text-color-light:   $oc-gray-6;
$text-color-disable: $oc-gray-5;
{% endhighlight %}


### 배경

일반적으로 배경은 흰색이지만, 모드의 전환, 영역의 구분 등을 위해서 옅은 회색을 사용할 때도 있다. 이때는 gray 0 혹은 gray 1을 사용한다. 비교적 최근까지 gray 0(`#f8f9fa`)처럼 흰색에 가까운 회색은 잘 쓰지 않았다. 그러나 디지털 기기의 디스플레이 기술이 발전 함과 동시에 극단적인 심플함을 강조하는 디자인 트랜드가 떠오르면서 무척 밝은 회색이 UI에 등장하기 시작했다. 그런 이유로 gray 1은 약간 촌스러운 느낌을 줄 수 있지만, 한편으로는 사양이 좋지 않은 기기, 시력이 좋지 않은 사용자에게도 충분한 어포던스를 확보한다.

<div class="center">
  <div class="bg-box bg-gray-0 color-gray-6">
    Gray 0을 적용한 배경
  </div>
  <div class="bg-box bg-gray-1 color-gray-6">
    Gray 1을 적용한 배경
  </div>
</div>

배경이 gray 0인 요소 위에 또다시 배경색으로 영역을 구분한다면 gray 1을 쓸 수 있다.

<div class="center">
  <div class="bg-box bg-box-block bg-gray-0 color-gray-6">
    Gray 0을 적용한 배경
    <div class="bg-box bg-box-block bg-gray-1 color-gray-6">Gray 1을 적용한 배경</div>
  </div>
</div>

{% highlight scss linenos %}// Background
$bg-color-white:        $oc-white;
$bg-color-gray:         $oc-gray-0;
$bg-color-gray-adjust:  $oc-gray-1;
{% endhighlight %}

버튼과 같은 요소는 배경색을 더 짙게 만들어서 상태의 변화를 나타낼 수 있다. Normal 상태의 배경 색에 두 단계 짙은 색을 사용한다.


<div class="center">
  <div class="bg-box bg-white bg-hover color-gray-6">
    마우스를 올려보세요
  </div>
  <div class="bg-box bg-gray-0 bg-hover color-gray-6">
    마우스를 올려보세요
  </div>
</div>

{% highlight scss linenos %}// Background state
.background {
  $bg-color: $bg-color-white;
  background: $bg-color;

  &:hover,
  &:focus,
  &:active {
    @if $bg-color == $oc-white {
      backgound-color: $oc-gray-1;
    } @if $bg-color == $oc-gray-0 {
      backgound-color: $oc-gray-2;
    } @if $bg-color == $oc-gray-1 {
      backgound-color: $oc-gray-3;
    }
  }
}
{% endhighlight %}

### 선

선요소는 gray 3과 gray 4를 사용한다. `<hr>` 등의 요소 간 구획을 나누는 선에는 gray 3이 적합하고, 폼이나 버튼의 테두리, 즉 동작할 수 있음을 암시하는 선으로는 gray 4가 적합하다.

<div class="center">
  <div class="border-box border-gray-3 color-gray-6">
    Gray 3을 적용한 선
  </div>
  <div class="border-box border-gray-4 color-gray-6">
    Gray 4를 적용한 선
  </div>
</div>

비활성 상태를 암시할 때는 grey 2를 사용한다.

<div class="center">
  <div class="border-box border-gray-4 color-gray-6">
    Gray 4를 적용한 선
  </div>
  <div class="border-box border-gray-2 color-gray-5">
    Gray 2를 적용한 선
  </div>
</div>


{% highlight scss linenos %}// Form
$hr-color:                  $oc-gray-3;
$border-color:              $oc-gray-3;
$form-border-color:         $oc-gray-4;
$form-disable-border-color: $oc-gray-2;
{% endhighlight %}


### 반전 색상

Open color는 흰색 베이스의 선 요소로 이루어진 UI 스타일을 근거로 두고 제작되었지만, 이런 스타일에서도 종종 검은 배경에 흰색 텍스트를 쓸 때가 있다. 이때엔 배경은 gray 9, 텍스트는 상태에 따라 gray 0, gray 5, gray 6, 선 요소는 gray 7을 쓴다.

<div class="center">
  <div class="bg-box bg-box-block bg-gray-9 color-gray-5">
    Gray 9를 적용한 배경
    <hr class="bg-gray-7">

    <div class="color-gray-0">
      Gray 0을 적용한 텍스트
    </div>
    <div class="color-gray-5">
      Gray 5를 적용한 텍스트
    </div>
    <div class="color-gray-6">
      Gray 6을 적용한 텍스트
    </div>

    <div class="bg-box bg-box-block bg-gray-8 color-gray-5">Gray 8을 적용한 배경</div>
  </div>
</div>


{% highlight scss linenos %}// Inverse
$text-color-white:          $oc-gray-0;
$text-color-inverse:        $oc-gray-5;
$text-color-inverse-light:  $oc-gray-6;

$bg-dark-gray:              $oc-gray-9;
$bg-dark-gray-adjust:       $oc-gray-8;

$hr-color-inverse:          $oc-gray-7;
{% endhighlight %}

### 유의 사항

위에 열거한 사용법은 제작자가 제안하는 보편적인 규칙일 뿐, 절대적이거나 이 외의 방법으로 쓸 수 없는 것은 아니다. 또한, 여기서 열거하지 않은 세분된 사용처에는 위의 규칙을 따를 수 없으므로 사용자의 상황에 맞게 적절히 대입하길 바란다.

