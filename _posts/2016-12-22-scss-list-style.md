---
layout: entry
title: SCSS 리스트 스타일
description: HTML tag 스타일 중 list는 유독 작성하기가 귀찮다. 특히 불릿을 본문 텍스트와 다른 폰트로 하고 싶을때 일이 복잡해진다. 이를 쉽게 몇가지 변수만 조정하면 쓸 수 있도록 SCSS 코드를 써보았다.
publish: true
---

HTML tag 스타일 중 list는 유독 작성하기가 귀찮다. Ordered list와 unordered list가 따로 있으며, 불릿 부분의 여백을 설정하는 방식도 조금 독특하다. 나아가 불릿을 본문 텍스트와 다른 폰트로 하고 싶을 때는 일이 한층 복잡해진다. 이 구차한 작업을 서로 다른 프로젝트에서 다섯 번쯤 반복하니, 다음에는 복사해 붙여넣기만 하면 되도록 정리할 필요를 느꼈다. 

우선 SCSS 코드는 [여기서](https://gist.github.com/yeun/d824fc7b04b756508f4b0143535cec30) 볼 수 있다. 단순히 복사해 사용한다면, 긴 코드를 모두 읽을 필요는 없다. 확인해야 할 부분은 5 - 16줄 사이의 변수들이다.

{% highlight scss linenos %}// Variables
$li-bottom-space: 0.8em;
$li-bullets-width: 1.7em;
$li-line-height: 1.55;

$ul-bullets-font: inherit;
$ul-bullets-font-size: 1.2em;
$ul-bullets-font-line-height: 1.2;
$ul-bullets-right-space: 0.65em;

$ol-bullets-font: inherit;
$ol-bullets-font-size: 1em;
$ol-bullets-font-line-height: inherit;
$ol-bullets-right-space: 0.65em;

$li-child-size-ratio: 0.95;
{% endhighlight %}

다음은 스타일을 적용한 리스트 이미지이다.

<img src="/images/2016-12-22/list.png" style="width: 608px;">

위 이미지에서 각 변수의 의미는 다음과 같다.

<img src="/images/2016-12-22/list-variables.png" style="width: 608px;">

- `$li-bottom-space`: list와 list 사이 간격이다.
- `$li-bullets-width`: 불릿 영역의 너비이다.
- `$li-line-height`: list 텍스트의 줄 높이를 뜻한다.
- `$ul-bullets-font`: Unordered list의 불릿에 사용될 폰트를 지정한다.
- `$ul-bullets-font-size`: Unordered list의 불릿 폰트 사이즈를 지정한다.
- `$ul-bullets-font-line-height`: Unordered list의 불릿의 줄 높이를 지정한다. list 텍스트와 세로 중앙정렬을 맞추기 위함이다.
- `$ul-bullets-right-space`: Unordered list의 불릿과 텍스트 사이의 여백이다.
- `$ol-bullets-font`: Ordered list의 불릿에 사용될 폰트를 지정한다.
- `$ol-bullets-font-size`: Ordered list의 불릿 폰트 사이즈를 지정한다.
- `$ol-bullets-font-line-height`: Ordered list의 불릿의 줄 높이를 지정한다. list 텍스트와 세로 중앙정렬을 맞추기 위함이다.
- `$ol-bullets-right-space`: Ordered list의 불릿과 텍스트 사이의 여백이다.
- `$li-child-size-ratio`: list 안에 list가 있을 때 지정한 비율만큼 폰트 사이즈가 줄어든다.

리스트에서 특히 불릿의 위치는 폰트에 따라 큰 차이가 나므로 스타일 코드에서 변수의 값은 상황에 맞게 조정이 필요하다.















