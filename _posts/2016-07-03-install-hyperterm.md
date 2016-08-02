---
layout: entry
title: HyperTerm 설치하기
description: JavaScript, HTML, CSS 기반의 터미널 프로그램인 HyperTerm을 설치하고, 간단한 테마를 설정한다.
publish: true
---

우스개 소리가 아니라 진지하게, 나에겐 개발 관련 프로그램이나 참조 웹사이트의 못생긴 디자인이 개발을 배우는데에 실질적인 진입장벽이다. 가끔 테마가 설치되지 않은 Sublime Text UI를 보게되면 ADHD에 걸린 것 마냥 집중이 안되며 어딘가 불안해지고, 자연의 HTML 그대로에 가까운 웹사이트를 볼 때면 볼 일만 보고 어서 화면을 꺼버리고 싶은 충동에 휩싸이기 때문이다. 다행히도 텍스트 에디터는 [Sublime Text](https://www.sublimetext.com/)와 [Material Theme](http://equinsuocha.io/material-theme/)에 정착해서 만족스럽게 사용[^install_sublime]하고 있지만, 터미널 프로그램은 항상 마음에 들지 않았다. 그러던 중 최근에 런칭한 HyperTerm을 알게 되었고, 설치 후 무척 만족하고 있기에 나와같은 심약한 디자이너들에게 설치 및 테마 설정 방법을 공유하려고 한다.

## 설치하기

1. [HyperTerm](https://hyperterm.org/) 웹사이트에 접속한다.
2. HyperTerm을 다운로드한다.
3. 다운로드 받은 프로그램을 설치한다.

설치법은 따로 적는게 무색할 정도로 쉽다.

## 테마 설정하기

*테마를 설정하기에 앞서 Sublime Text가 설치되어있지 않다면 [아래 주석](http://yeun.github.io/2016/07/02/install-hyperterm.html#fn:install_sublime)의 글을 먼저 읽고, 설치 후 진행하길 바란다.*

1. HyperTerm을 실행한다.
   <img src="/images/2016-07-03/hyperterm.png" style="width: 652px;">
2. 다음 명령어를 입력해서 `sublime` 명령어를 등록한다.
      {% highlight linenos %}ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime{% endhighlight %}
   <img src="/images/2016-07-03/sublime_command.png" style="width: 652px;">
3. 다음 명령어를 입력해서 Sublime Text로 .hyperterm.js 문서를 연다.
      {% highlight linenos %}sublime .hyperterm.js{% endhighlight %}
   <img src="/images/2016-07-03/open.png" style="width: 652px;">
4. 아래 그림과 같은 문서가 열리면 이곳에서 원하는 스타일대로 설정하고 저장하면 된다.
   <img src="/images/2016-07-03/sublime.png">

내가 설정한 테마는 아래와 같다.

{% highlight javascript linenos %}
module.exports = {
  config: {
    // default font size in pixels for all tabs
    fontSize: 14,

    // font family with optional fallbacks
    fontFamily: 'Source Code Pro, Menlo, "DejaVu Sans Mono", "Lucida Console", monospace',

    // terminal cursor background color and opacity (hex, rgb, hsl, hsv, hwb or cmyk)
    cursorColor: 'rgba(0,255,255,0.75)',

    // `BEAM` for |, `UNDERLINE` for _, `BLOCK` for █
    cursorShape: 'BLOCK',

    // color of the text
    foregroundColor: '#fff',

    // terminal background color
    backgroundColor: '#15181d',

    // border color (window, tabs)
    borderColor: '#3f4958',

    // custom css to embed in the main window
    css: '',

    // custom css to embed in the terminal window
    termCSS: '',

    // custom padding (css format, i.e.: `top right bottom left`)
    padding: '14px 18px',

    // the full list. if you're going to provide the full color palette,
    // including the 6 x 6 color cubes and the grayscale map, just provide
    // an array here instead of a color map object
    colors: {
      black: '#000000',
      red: '#ff5c86',
      green: '#24eaf0',
      yellow: '#ffbe69',
      blue: '#4996ff',
      magenta: '#9e84ff',
      cyan: '#2ddfff',
      white: '#e9ebf4',
      lightBlack: '#000000',
      lightRed: '#ff5c86',
      lightGreen: '#24eaf0',
      lightYellow: '#ffbe69',
      lightBlue: '#4996ff',
      lightMagenta: '#9e84ff',
      lightCyan: '#2ddfff',
      lightWhite: '#e9ebf4'
    },

    // the shell to run when spawning a new session (i.e. /usr/local/bin/fish)
    // if left empty, your system's login shell will be used by default
    shell: ''

    // for advanced config flags please refer to https://hyperterm.org/#cfg
  },

  // a list of plugins to fetch and install from npm
  // format: [@org/]project[#version]
  // examples:
  //   `hyperpower`
  //   `@company/project`
  //   `project#1.0.1`
  plugins: [],

  // in development, you can create a directory under
  // `~/.hyperterm_plugins/local/` and include it here
  // to load it and avoid it being `npm install`ed
  localPlugins: []
};
{% endhighlight %}

구문 강조 색상은 12가지로 더 세밀하게 지정할 수 있고, HTML, CSS 기반의 터미널이기 때문에 마치 웹처럼 개발자 도구를 켜서 스타일을 추가할 수도 있다. 난 아직 거기까지는 필요성을 느끼지 못해 따로 스타일을 추가하진 않았지만, 원한다면 무척 세세하게 스타일을 지정할 수 있어보인다.


[^install_sublime]: Sublime Text를 설치하고 테마를 적용하는 방법은 Spoqa 기술 블로그의 [Sublime Text 시작하기](http://spoqa.github.io/2015/11/11/install-sublime-text.html)에 적혀있다.