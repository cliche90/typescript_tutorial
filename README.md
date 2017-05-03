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

## 7. 프로젝트의 구성
- node_modules

    npm을 통해 설치된 package들이 저장되는 장소

- platforms

    실행할 예정인 플랫폼들(android, ios, browser 등)이 추가되어 있다.(윈도우의 경우 설치된 위치가 다를 수 있음)

- plugins
    
    cordova를 통해 설치되는 플러그인들이 저장되는 장소

- resources
    
    자원(ico, image 등)들을 관리하는 디렉토리

- src

    가장 중요한 부분. 실질적으로 소스코드를 작성할 때 사용하는 부분.

- www

    웹 관련한 부분으로, 결과물들을 확인할 수 있는 디렉토리

- config.xml

    cordova의 설정을 정하는 파일. widget 태그의 id 속성은 package name으로 app을 완전히 독립적으로 구분할 수 있는 이름. preference는 app 전체에 대한 설정들을 의미

## 8. src 디렉토리의 구성

- index.html

    `<ion-app>` 태그는 실질적으로 App이 로딩이 되는 장소이다. 즉, App의 시작지점.

- assets

    정적인 파일들을 관리하는 디렉토리.

- theme

    디자인 구성을 위한 코드작성에 사용되는 디렉토리.

> Tip: Component는 html, scss, typescript의 합으로 구성된다고 생각하면 쉽다.

- app

    app.component.ts, app.html, app.scss로 구성되어 있는 컴포넌트라고 생각할 수 있다. app.module.ts는 전체 app에 대한 내용이 들어 있는 파일이라고 생각할 수 있다. main.ts 의 경우 루트 컴포넌트에 붙이는 작업을 한다.

- pages

    초기에는 tabs라는 디렉토리를 통해서 abaout, contact, home 디렉토리를 볼 수 있는 구조이다.

## 9. cordova란?

> 웹 기술(html, css, js)를 통해 app을 개발할 수 있도록 해 준다.

- ionic framework?

    간단하게만 말하자면 cordova와 angular2js 그리고 Gulp 등을 묶어서 감싼 프레임워크라고 할 수 있다.

- 아이오닉 자체가 특별하여 웹 기술 기반으로 app을 개발할 수 있도록 한다기보다는 핵심은 cordova에 있다.

- camera나 accelerometer 등 웹 기술과는 동떨어진 플러그인들을 사용할 경우에 cordova plugin을 설치하여 사용한다.

- "node_modules" vs "plugins"

    __node_modules__ : javascript 라이브러리가 설치되는 장소

    __plugins__ : cordova plugin들이 설치되는 장소    

## 10. Angular js2 & Typescript

### 10-1. Angular js2

    js프레임워크 중 하나이며 구글이 관리중, 클라이언트 측 개발을 위해 필요한 프레임워크. 하나의 어플리케이션은 컴포넌트와 템플릿의 조합으로 작성, 컴포넌트들을 디펜던시 인젝션을 이용하여 컴포턴트에 필요한 것들을 디펜던시로 관리. 컴포넌트들은 directive 형태로 사용.
    
    정리하면 템플릿은 디자인적인 측면, 컴포넌트는 기능적인 측면으로 만들어, 템플릿을 재사용하는 방식으로 개발하도록 하는 것이 지향하는 바이다.

> meta-data를 작성 → @Component와 같은 decorator를 통해 meta-data 작성 가능

> class를 작성 → class = data + logic

- meta-data 작성으로부터 만들어진 태그를 사용할 수 있다. 이러한 형태의 컴포넌트를 directive라고 볼 수 있다.

### 10-2 Typescript

    ms에서 관리중에 있으며, 기본 페이지에 보면 스케일 가능한 js라고들 많이 이야기 한다.

    - 타입이 지정된 js의 superset(확장된 기능을 가짐)이라고 할 수 있다.

    - 타입이 지정되기 때문에 에러를 매우 쉽게 찾아낼 수 있어, 개발하는 데에 편의를 제공한다.

    - Type, OOP, Scalability(확장성)

    - 장점만 있는 것은 아니나, 확장성이나 OOP 측면 등에서 장점을 가진다.

    - js와의 가장 큰 차이는 type이 있는가 없는가이다. 그러나 ES6 js와 엄청 큰 차이가 있는 것이 아니기 때문에 type이 적용되는 js라고 생각해도 충분하다.

    - ts

    class Greeter {
        greeting: string;
        construct (message: string) {
            this.greeting = messsage;
        }
        greet() {
            return "Hello, " + this.greeting;
        }
    }


    - js

    var Greeter = (function(){
        function Greeter(message){
            this.greeting = message;
        }
        Greeter.prototype.greet = function() {
            return "Hello, " + this.greeting;
        }
        return Greeter;
    })

## 11. Typescript 기본 문법

### 11-1. 특징

> Javascirpt that scales(확장 가능한 자바스크립트)

- classes
- modules
- interfaces
- generics
- static typing(optional)


    npm install -g typescript   // typescript 설치

    tsc -v  // typescript 설치 및 버전 확인

    tsc main.ts     // main.ts 파일을 main.js 파일로 변환

### 11-2. Typescript 테스트

- 필요한 파일들을 만들고 web browser에서 직접 확인
- Typescript / Javascript Playground에서 직접 확인

위 두 가지 방법이 있음. Playground 방식의 경우 따로 html 파일을 작성하지 않아도 되기 때문에, 확인하는 것이 편리하다.

### 11-3. 변수(variable)

> variable = space + name

- 값을 저장하는 공간
- 값에 이름을 줄 수 있다.

기본적으로 typescript는 3개의 basic type을 가진다.

- boolean
- number
- string

* 작성 방식

    var 변수명: 타입 = 값

- any

    any 타입으로 선언된 변수에는 무엇을 넣어도 상관없는 변수이다.

- Sample Code
>
    var isDone: boolean = false;
    var age: number = 23;
    var myName: string = "name";
    var notSure: any = "hello"

    console.log(isDone);
    console.log(age);
    console.log(myName);
    console.log(notSure);

- null vs. undefined

    null : 변수가 비어있다.

    undefined : 비어있다는 명세조차 되어있지 않다.

- collection
>
    var list: number[] = [1, 2, 3];
    var list: Array<number> = [1, 2, 3];

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