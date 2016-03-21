---
layout: entry
title: RGB와 HSB
description: 최근에 동료 디자이너에게 HSB의 Brightness 값이 상대적이라는 개념을 설명할 일이 있었다. 마침 비슷한 주제로 세미나를 했던 적이 있어서 그때 썼던 키노트를 활용하려고 했는데 다시 보니 설명이 충분치 않았다. 그래서 정돈된 글로 갈무리할 필요를 느꼈다. 
publish: true
---

RGB와 HSB는 너무나 익숙한 개념이기도 하지만 구체적으로 이 둘의 차이가 무엇인지 RGB Cube와 HSB Cylinder 속에서 Hue(색상), Saturation(채도), Brightness(밝기)가 어떻게 움직이는 모양인지 배운 적이 없기에 감각에 의존해서만 색에 접근했다. 하지만 누군가에게 설명할 때 “왠지 이 색이 더 좋은 것 같으니까 골랐다” 라고 말할 수는 없기에 한번 시간을 들여 색상 시스템을 공부했고 그 후로는 머릿속에서 색 공간을 그리는 일이 훨씬 명료해짐을 체감했다. (그리고 왜 개발자에게 컬러 스펙을 HSB로 전달하면 안 되는지도 알 수 있었다.)이 포스팅으로 다른 디자이너들에게도 그와 같은 도움이 되길 바라며 아는 바를 정리해본다.

## 빛의 삼원색, 색의 삼원색

후에 나올 이야기를 좀 더 쉽게 이해할 수 있도록 먼저 기본적인 개념을 되짚어보려고한다.
빛의 삼원색, 색의 삼원색이라는 표현을 들어보았을 것이다. 
빛의 삼원색은 Red, Green, Blue 즉 지금 이야기하려는 RGB이고 색의 삼원색은 Cyan, Magenta, Yellow로 주로 인쇄 시 이야기하는 잉크의 색인 CMY이다.

<figure>
  <img src="/images/2016-03-21/primary-colors.png" style="width: 600px;">
  <figcaption>빛의 삼원색(좌)과 색의 삼원색(우)</figcaption>
</figure>

어릴 때 접하는 미술 도구로부터 우리는 12색 사인펜의 모든 색을 다 섞으면 검은색이 된다는 것을 직감적으로 알고 있다. 이렇게 섞어서 검은색이 되는 것을 감산 혼합(減算 混合)이라고 한다. 반대로 빛은 아무 빛이 없을 때가 검은색이며 모든 빛을 더하면 흰색이 된다. 이를 가산 혼합(加算 混合)이라고 한다.

- 빛의 삼원색 = 가산 혼합의 삼원색 = Red, Green, Blue = RGB
- 색의 삼원색 = 감산 혼합의 삼원색 = Cyan, Magenta, Yellow = CMY

그러므로 8 bits 체계에서 왜 검은색이 (0, 0, 0)이고 흰색이 (255, 255, 255)인지 알 수 있다. 삼원색이 하나도 없는 상태가 검은색이고, 삼원색이 모두 최대로 있는 상태가 흰색이기 때문이다.

그렇다면 아래 RGB 값들은 색으로 표현하면 무슨 색일까?

1. RGB(255, 0, 0)
2. RGB(0, 255, 0)
3. RGB(0, 0, 255)
4. RGB(23, 185, 79)



## HSB의 탄생

1, 2, 3번은 쉽게 답을 맞혔을 것이다. 1번은 Red가 최대고, Green과 Blue는 없는 상태이므로 당연히 빨간색일 것이다. 2, 3번도 같은 식으로 각각 초록, 파랑이라고 답할 수 있다. 반면 4번은 무슨 색인지 유추해내기 어렵다. 이렇게 RGB 값은 직관적으로 이해하기 어려우므로 HSB라는 호환체계가 1970년경에 고안되었다. 그럼 다시 4번 문제로 돌아가서 RGB(23, 185, 79)를 HSB로 변환해 보면 HSB(141, 88, 73)이다. 바로 명 채도가 약간 낮은 초록색이라는 것을 알 수 있다.

<figure>
  <img src="/images/2016-03-21/convert-rgb-hsb-ps.png" style="width: 620px;">
  <figcaption>HSB(141, 88, 73)</figcaption>
</figure>

여기서 잠깐, 만약 일러스트를 사용하는 독자라면 이 답에 고개를 갸우뚱할 수 있다. 일러스트에서 같은 값 RGB(23, 185, 79)를 입력하면 HSB(139, 87, 72)로 변환하기 때문이다.

<figure>
  <img src="/images/2016-03-21/convert-rgb-hsb-ai.png" style="width: 620px;">
  <figcaption>HSB(139, 87, 72)</figcaption>
</figure>

이런 현상이 발생하는 이유는 HSB가 RGB를 호환하기 위해 만들어졌기 때문에 직관적이지만 정확하지는 않기 때문이다. 정수[^integer]로만 놓고 계신 했을 때 RGB 체계에서 나올 수 있는 색상은 256<sup>3</sup>=16,777,216개이다. 반면 HSB는 360 × 100 × 100 = 3,600,000개로 RGB 색상의 약 21%밖에 표현하지 못하며 1:1 매칭되지도 않는다. 하지만 인간이 볼 수 있는 색이 1,000만여 개 정도이므로 HSB가 RGB를 완벽히 호환하지 못하는 것을 크게 걱정할 필요는 없다. 다만 이렇게 프로그램에 따라 같은 값이라도 서로 다르게 변환하는 현상을 방지하고 싶다면 HSB보다는 RGB를 기준으로 작업하는 것이 좋다. 

## RGB Cube에서 HSB Cylinder로

그럼 이제 본격적으로 RGB가 어떻게 HSB로 환원되며 어떤 과정에서 색상 정보가 변질되는지 알아보자. 

RGB는 한 변의 길이가 256인 정사각형으로 그릴 수 있다. 이를 RGB Cube라고 한다.

<figure>
  <img src="/images/2016-03-21/RGB_color_solid_cube.png" style="width: 600px;">
  <figcaption>RGB Cube</figcaption>
</figure>

이 RGB cube를 HSB Cylinder로 만들기 위해선 먼저 이 정사각형의 한 꼭짓점인 검은색(RGB(0, 0, 0))과 흰색(RGB(255, 255, 255))을 잇는 축이 수평에 직각이 되도록 돌린다. 

<figure>
  <img src="/images/2016-03-21/rgb-to-hsb-01.gif" style="width: 200px;">
  <figcaption>검은색이 아래, 흰색이 위로 가도록 RGB Cube를 돌린다</figcaption>
</figure>

이렇게 돌린 RGB Cube를 정면에서 바라보면 각 꼭짓점, Red, Green, Blue와 Cyan, Magenta, Yellow의 높이가 다르다.

<figure>
  <img src="/images/2016-03-21/rgb-cmy-level.png" style="width: 700px;">
  <figcaption>R, G, B와 C, M, Y의 높이가 다르다</figcaption>
</figure>

이 높이를 강제로 중앙값으로 통일한다.

<figure>
  <img src="/images/2016-03-21/rgb-to-hsb-02.gif" style="width: 300px;">
  <figcaption>R, G, B, C, M, Y 높이 비교</figcaption>
</figure>

이로써 C, M, Y의 위치가 흰색에서 검은색에 더 가까워졌고, R, G, B의 위치는 검은색에서 흰색에 더 가까워졌다. 이렇게 변형된 육각 마름모꼴을 원통 형태로 만들기 위해 하단의 검은색 꼭짓점을 육각형 형태로 늘인다.

<figure>
  <img src="/images/2016-03-21/rgb-to-hsb-03.gif" style="width: 200px;">
  <figcaption>검은색 꼭짓점을 육각형 형태의 면으로 만든다</figcaption>
</figure>

이번에는 상단의 흰색 꼭짓점을 아래로 눌러 육각 기둥 형태를 만든다.

<figure>
  <img src="/images/2016-03-21/rgb-to-hsb-04.png" style="width: 400px;">
  <figcaption>흰 꼭짓점을 눌러 납작하게 만든다</figcaption>
</figure>

이렇게 만들어진 육각 기둥의 각 면을 둥글게 만들어서 높이와 반지름이 같은 원기둥으로 만든다.

<figure>
  <img src="/images/2016-03-21/hsb.png" style="width: 250px;">
  <figcaption>육각 기둥의 옆면을 둥글려 원통으로 만든다</figcaption>
</figure>

tada! RGB Cube가 HSB Cylinder로 변했다. 

<figure>
  <img src="/images/2016-03-21/HSV_color_solid_cylinder.png" style="width: 500px;">
  <figcaption>HSB(HSV) Cylinder</figcaption>
</figure>

이 HSB Cylinder[^HSV-HSB]를 잘라 단면을 보면 H(hue)를 기준으로 한 color picker의 익숙한 모습을 볼 수 있다.

이렇게 RGB Cube를 HSB Cylinder로 변형하면서 색공간이 다음과 같이 달라졌다.

- R, G, B는 흰색보다 검은색과 C, M, Y는 검은색보다 흰색과 가까웠는데 두 길이가 같아졌다.
- 검은색은 점이었는데 면이 되었다.
- 흰색과 R, G, B, C, M, Y의 높이(brightness, value)가 같아졌다.
- 검은색과 흰색을 잇는 축과의 각도는 R, G, B가 C, M, Y보다 컸는데 모두 같아졌다.
- 색점간 간격이 같았는데, 달라졌다. 

<figure style="width: 381px; display: inline-block;">
  <img src="/images/2016-03-21/rgb-dot.jpg">
  <figcaption>RGB Cube 속의 색점</figcaption>
</figure>
<figure style="width: 300px; display: inline-block;">
  <img src="/images/2016-03-21/hsb-dot.png">
  <figcaption>HSB Cylinder 속의 색점</figcaption>
</figure>

HSB 상의 명 채도를 절댓값으로 생각해서 발생하는 많은 오해가-이를테면 똑같은 명 채도의 노랑색과 빨강색을 찍었는데 노랑이 더 밝아 보인다든지, 짙은 남색은 채도 변화가 눈에 잘 안 띈다거나 하는 것들- 이 변환 과정에 연유한다.

## RGB Cube 속에서의 <br> Hue, Brightness, Saturation

그렇다면 색 간의 관계를 더 정확히 이해하기 위해 다소 낯선 RGB Cube를 더 뜯어보기로 한다. 

### Hue 색상[^hue]

<figure>
  <img src="/images/2016-03-21/rgb-hue.png" style="width: 600px;">
  <figcaption>RGB Cube의 Hue</figcaption>
</figure>

RGB Cube에서나 HSB Cylinder에서나 Hue는 검은색과 흰색을 잇는 축을 기준으로 하는 각도로 표현된다. 하지만 HSB Cylinder에서는 같은 Hue 값을 가지는 색상이 사각형의 면으로 표현되는 데 반해 RGB Cube에서는 각도마다 변의 길이가 다른 삼각형이라는 점이 다르다.

### Brightness 밝기

앞서 빛의 삼원색에 대해 알아보았다. 빛은 가산 혼합이며 각 Red, Green, Blue 빛의 정도가 많을 수록(밝을수록) 흰색에 가까워진다. 그러므로 RGB(a, b, c)라 할 때 (a + b + c)/3이 그 색의 brightness다. 따라서 검은색과 흰색을 잇는 축에 직교하는 평면 위에 있는 점들, 즉 (a + b + c)/3의 값이 같은 색들은 그 밝기가 서로 같다.[^lab]

<figure>
  <img src="/images/2016-03-21/rgb-brightness.png" style="width: 600px;">
  <figcaption>RGB Cube의 Brightness</figcaption>
</figure>

위 이미지로부터 R, G, B는 C, M, Y보다 어두운색임을 알 수 있다.

### Saturation 채도

RGB Cube의 흰 꼭짓점과 검은 꼭짓점을 잇는 중심축은 당연하게도 모두 회색으로 이루어져 있다. Hue 이미지를 보면 이 축에 가까워져 올수록 채도가 낮아짐을 알 수 있다. 즉 채도는 RGB Cube의 검은색 점에 정점을 두며, 중심축을 공유하는 원뿔형이다.

<figure>
  <img src="/images/2016-03-21/rgb-saturation.gif" style="width: 500px;">
  <figcaption>RGB Cube의 Saturation</figcaption>
</figure>

그러므로 C, M, Y는 R, G, B보다 채도가 낮은 색임을 알 수 있다.

## 결론

지금까지 HSB와 RGB의 구성 원리를 알아보았다. 두 색공간의 차이로부터 많은 관계를 유추할 수 있다. 디자인하는 데 필요한 간단한 상식을 위주로 돌아보며 포스팅을 마치려 한다.

##### HSB 컬러와 RGB 컬러는 1:1 대응하지 않는다.

HSB컬러는 RGB컬러의 약 21%밖에 표현하지 못한다. 그래서 Color picker 상에서 HSB 값을 가감하며 조정하면 원하는 색을 미세하게 뽑을 수 없으며, 그래픽 툴 간에 RGB 값이 달라지기도 한다. 이런 이유로 큰 틀에서는 HSB로 색을 뽑되 최종 색은 RGB 값으로 기록, 공유하는 것이 정확하다.

##### HSB Color Picker의 단면은 색 밀도가 균일하지 않다.

<figure>
  <img src="/images/2016-03-21/density.png" style="width: 326px;">
  <figcaption>Hue 0의 HSB(좌)와 RGB(우) 단면</figcaption>
</figure>

보다시피 HSB 단면은 RGB 단면을 직관적으로 인지하기 쉽도록 변형한 것이다. 그 과정에서 흰색(255, 255, 255)과 원색 (255, 0, 0)을 잇는 변의 길이가 줄어들었으며(색 밀도가 높아졌으며) 한 점으로 표현되는 검은색(0, 0, 0)이 밑변이 되었다. 따라서 HSB 단면의 밑변과 흰점을 잇는 삼각형 영역이 (255, 255, 255), (255, 0, 0), (0, 0, 0)을 지나는 직각 삼각형보다 색 밀도가 낮다. 또한 세로축(Saturation)보다 가로축(Brightness)의 밀도가 높다.


##### HSB의 Saturation과 Brightness는 상댓값이다.

Saturation 값과 Brightness 값이 같더라도 Hue가 다르다면 두 색의 명도와 채도는 다를 수 있다. HSB 상에서 S, B는 같은 Hue 값 내의 상대 수치일 뿐 물리적, 인지적 절댓값을 의미하지 않는다. R, G, B가 C, M, Y보다 채도가 높으며 명도가 낮은 색상임을 유의한다.


---

### 참고 문헌과 이미지 출처

참고했던 페이지들과 이미지 출처이다. 이 포스트를 재미있게 읽었다면 아래 꼭지들을 더 읽어보기를 권한다.

- [Primary color](https://en.wikipedia.org/wiki/Primary_color)
- [RGB color model](https://en.wikipedia.org/wiki/RGB_color_model)
- [HSL and HSV](https://en.wikipedia.org/wiki/HSL_and_HSV)
- [Cylindrical coordinate system](https://en.wikipedia.org/wiki/Cylindrical_coordinate_system)
- [Relating HSV to RGB](http://www.dig.cs.gc.cuny.edu/manuals/Gimp2/Grokking-the-GIMP-v1.0/node52.html)
- [Color Theory and Principles](http://www.infocellar.com/Graphics/color-theory.htm)
- [Lab color space](https://en.wikipedia.org/wiki/Lab_color_space)
- [How To Avoid Equidistant HSV Colors](http://vis4.net/blog/posts/avoid-equidistant-hsv-colors/)

[^integer]: RGB와 HSB는 모두 실수 체계를 가진다. 하지만 일반적인 디자인 작업에서 이 둘을 소수점까지 다루지는 않고, 인간의 눈이 인지할 수 있는 색상의 영역이 정수로만 연산한 RGB 색 공간 안에 포함되기 때문에 이 포스트에서는 정수 체계에서의 색들만 다루었다. 
[^HSV-HSB]: HSV의 V는 value의 이니셜이며, HSB의 brightness와 같은 의미이다. 일반적으로 HSV라는 용어를 더 자주 쓰지만, 어도비 그래픽 툴을 사용하는 디자이너에게는 HSB가 익숙한 표현이므로 포스팅에서는 HSB라는 단어를 사용했다.
[^hue]: Hue를 한글로 “색상”이라고 번역하는데, 이는 H, S, B를 모두 포함하는 Color “색”이라는 개념과 종종 혼란을 빚으므로 주의하도록 한다.
[^lab]: 여기서 색의 명도가 같다는 의미는 물리적인 차원에서 한 설명이다. 인간의 눈이 인지하는 밝기와는 차이가 있으며 이는 Luminance라고 한다. Lab 색공간에서 L이 바로 Luminance를 뜻한다.