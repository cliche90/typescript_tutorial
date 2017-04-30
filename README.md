# Typescript Tutorial for ionic2

## 1. 시작

- 아이오닉2 프레임워크란?

    <strong>하이브리드 앱 개발 프레임워크</strong>의 한 종류.<br>
즉, 극단적으로 말해 웹 기술을 이미 가지고 있는 사람이 추가적인 학습 없이도 앱 개발을 바로 할 수 있도록 해주는 개발 플랫폼입니다.

- 장점 및 ionic을 통해 얻을 수 있는 것

    1. 기초적인 웹기술(html, css, js 등)을 알고 있으면 굉장히 빠른 속도로 개발 가능
    2. iOS, Andrid, Windows 등 각 플랫폼에서의 개발을 따로 하지 않아도 된다.(각 플랫폼에 맞게 UI가 변경된다)
    3. 개발에 드는 시간이 매우 절약된다.
    4. 별도의 앱 구동 과정 없이 곧바로 웹브라우저에서  결과 확인이 가능하다.

- 아이오닉에서는 javascript대신 typescirpt를 사용하기를 권하고 있다.



## 2. 아이오닉2 앱 개발을 위한 준비 과정

- 터미널 / cmd
    > 본 문서는 윈도우10의 기능인 bash on Ubuntu on Windows 기준으로 작성 되었으므로, Ubuntu 기준의 커맨드를 이용하시면 됩니다. 또한 sudo 권한으로 설치하더라도 문제가 있을 경우 `sudo su`  커맨드로 루트 권한을 받아 작업을 진행하셔야 합니다.

- IDE / Editor
    > 본 문서는 Visual Studio Code를 기준으로 작성되었습니다.

## 3. node.js / npm 설치

- [node.js / npm 설치](https://nodejs.org/ko/download/package-manager/)<br>
    Debian과 Ubuntu에 기반을 둔 Linux 배포판 부분을 참고  
>
    curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
    sudo apt-get install -y nodejs

## 4. cordova / ionic 설치

    npm install -g cordova ionic

## 5. ionic2 프로젝트 생성
- 아래의 커맨드들은 아이오닉2 버전으로 myApp이라는 이름으로 어플리케이션을 생성함을 의미합니다.
>
    ionic start myApp blank --v2
>    
    ionic start myApp tabs --v2
>    
    ionic start myApp sidemenu --v2

- blank는 빈 Application 생성
- tabs는 tab이 있는 Application 생성
- sidemenu는 sidemenu가 있는 Application 생성

## 6. ionic RUN!
    cd myApp
    ionic serve -c -l
- 생성한 프로젝트 디렉토리 아래로 이동하여 `ionic serve` 커맨드로 App을 실행시킵니다.
- `-c`는 콘솔 창에 로그를 띄워주기 위한 옵션입니다.
- `-l`은 다양한 플랫폼에서 확인을 한 번에 할 수 있도록 하는 옵션입니다.

# ERROR 발생시 조치법
> bash on Ubuntu on Windows 로 해당 과정을 진행하면 많은 에러가 발생하는데 해결한 문제들의 조치사항들을 적어두었습니다.
- 만약 커맨드 실행 후 "Failed to open browser: Command failed: xdg-open ~~" 와 같은 오류가 발생하면 bash에 몇 가지 커맨드가 설치되어 있지 않은 것이므로 아래의 커맨드를 이용하여 xdg-utils와 lynx, w3m을 설치해 주어야 합니다.
- 오류를 방치해도 크게 상관 없을 것으로 보이나, 신경이 쓰인다면 설치하고 진행하면 됩니다. 오류 중에는 w3m에 관한 부분도 있었으므로 함께 설치해 줍니다.
>
    sudo apt install xdg-utils
    sudo apt install lynx
    sudo apt install w3m

> Please install your Cordova CLI to version >=4.2.0 `npm install -g cordova`
- 위와 같은 warning 이 발생할 경우에는 커맨드 창에 아래의 커맨드를 실행하면 해결됩니다.
>
    cordova telemetry on

> Native: tried calling StatusBar.styleDefault, but Cordova is not available.
- 위와 같은 warning은 cordova가 브라우저가 아니라 Device 환경에서 작동하기 때문인데, 무시하셔도 좋을 것 같습니다.