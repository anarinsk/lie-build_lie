**How to Build `lostineconomics.com`**
 

2019-11-14

Jun Sok Huhh | :house:[lostineconomics.com](http://lostineconomics.com)

# tl;dr 

- 깔끔함을 빙자한 허름&귀차니즘 홈페이지를 무료로 만들고 싶다면, 나를 따르라~ 

# 뭐 대단한 사이트라고... 

그렇다. 전혀 대단하지 않다. 왜 이런 글을 쓰냐고? 그냥 기록을 위해서다. 미래의 어느 시점에서 다 까먹을 '나'놈을 위해서 기록을 남겨 놓는 것이다. 이 글을 볼 사람도 없겠으나, 혹시라도 도움이 된다면 고맙겠다. 

<p align="center">
<kbd>
  <img src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_1.png?raw=True" width="600">
</kbd></p>


# Contraints

애초에 이 사이트를 만들면서 몇 가지 제약 사항을 걸었다. 

1. 도메인 구입 비용만 제외하고 github(깃헙)만 쓴다.
2. 과도할 정도로 깔끔한 사이트를 만든다. 
3. 코딩이 포함된 포스팅을 제외하고 수식을 포함해 빠르고 쉽게 포스팅을 작성한다.  

1이 가능해진 까닭은 깃헙에서 static web을 지원하기 때문이다. 깃헙을 이용 하면 이용자의 리포지터리(리포) 별로 프로젝트 페이지(Github Pages)를 만들 수 있다. 이 녀석을 활용하면 Jekyll, Hugo 등의 도구를 활용해 github 위에서 제대로 돌아가는 블로그, 홈페이지를 제작할 수 있다. 좋은 튜토리얼은 언제나처럼 구글신께 문의하시라.[^1]

[^1]: 링크 하나만 적어둔다.  [https://blog.chulgil.me/how-to-make-blog-using-github-1](https://blog.chulgil.me/how-to-make-blog-using-github-1/)

어느날 마음에 드는 Hugo skin을 고르고 있다가 이런 생각이 들었다. '내가 원하는 건 이런게 아니라, 그냥 블랭크 페이지에 $\LaTeX$ 이 휼륭하게 렌더링되는 정도인데..." 그런데 이런 허름한 미니멀리즘 구현하는 게 생각보다 쉽지 않았다. Jekyll이든 Hugo든 모두 블로그를 통으로 관리하게 만든 툴이다. md(markdown)로 글을 쓰면 여기에 여러 옷을 입히는 형태인데 이 옷을 내 마음대로 제어하는게 쉽지 않았다. 물론 이는 내가 html이나 javascript에 무지하기 때문이다. 이를 잘 알았다면 내가 원하는 형태대로 이리저리 뜯어고칠 수 있었겠지... 

# stackedit.io, the king 

md를 빠르게 로컬에 속박되지 않고 쓰게 해주는 툴들이 많이 있다. 그 중에서 나는 stackedit가 킹왕짱이라고 말하고 싶다. 이유는 아래와 같다. 

<p align="center">
<kbd>
  <img width="300" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_2.png?raw=True"></kbd></p>
  
1. stackedit.io는 github에서 소스를 받아와 웹 브라우저 상에서 가볍게 구현된다. 개인별 설정은 구글 드라이브 혹은 깃헙 저장한다. 어디서 쓰든 적절한 계정으로 로긴만 하면 작성하던 글을 포함해서 동일한 환경이 보장된다. 
2. 위 그림처럼 폴더 버튼을 누면 왼쪽으로 어떤 것을 썼는지 볼 수 있고 디렉토리 구조로 정리도 쉽게 구현할 수 있다. 오른쪽의 샵 버튼을 누르면 오른쪽으로 설정 관련 메뉴가 뜬다. 
3. md 문서를 다양한 형태로 저장하고, 변형하고, publish할 수 있다. 
4. $\LaTeX$ 수식이 필요한 사람에게는 딱이다. $\LaTeX$과 같이 본격적인 조판 작업에는 여러모로 아쉬움이 있지만 KaTeX을 통해 지원되는 정도로도 왠만한 용도는 감당하고 남는다. 

<p align="center">
<kbd>
  <img width="300" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_3.png?raw=True"></kbd></p>

3번이 이채로운 대목이다. 왼쪽 끝의 네모 안에 들어있는 샵을 누르면 그림처럼 메뉴가 펼쳐진다. 

- "Workspace"는 stackedit.io의 여러가지 환경을 저장하는 공간이다. 이 덕분에 서로 다른 장비에서도 로그인만 하면 동일한 결과가 보장된다. 
- "Syncronize" 는 저장을 의미한다. 여러 저장소, 구글드라이브, 깃헙, 드롭박스 등이 지원된다. 같은 md 문서를 여러 개의 저장소에 동시에 저장할 수 있다. 
- import/export는 외부의 문서를 들여오고 내보내는 기능이다. 예를 들어, md로 작성한 문서를 html의 포맷으로 로컬이 다운받을 수 있다. 
- publish가 상당히 특이한 기능인데, 이는 변형된 형태의 문서를 다시 다른 저장소로 내보내는 것을 의미한다. 이 기능이 블로그를 편리하게 운영하는 데 핵심적인 역할을 한다. 

# Landing index.html

일단 `깃헙아이디.github.io`로 리포를 딴다. 즉, lostineconomics.com의 경우에는 `anarinsk.github.io`가 된다. 이는 깃헙 리포이기도 하지만, 해당 깃헙 아이디의 대표 주소도 된다. 이 리포/페이지를 일종의 랜딩 페이지, 즉 대문으로 활용할 수 있다. 대문에는 여러가지 스타일을 입힐 수 있겠지만 나는 안했다. 

대문 페이지의 경우 깃헙에서 제공하는 Jekyll을 활용할 수 있다. lostineconomics.com의 경우 minimal 양식을 더 줄여 활용했다. 

- 설정을 담고 있는 `_config.yml` 파일을 거의 다 날리고 필요한 부분만 챙겼다. 
- `index.md` 파일은 대문에 노출될 콘텐츠를 담고 있다. 새로운 포스트가 생길 경우 이 부분만 수정하면 된다. 이 파일 역시 stackedit.io에 연결해두고 쓰면 편리하다. [직접](https://github.com/anarinsk/anarinsk.github.io) 둘러보시라. 

# Write Hard Way 

- stackedit.io의 export 기능을 활용했다. 그럼처럼 `import/export` &rarr; `export as HTML`로 html로 로컬에 저장한다.
- 해당 html을 github의 public 리포에 올려둔다. 
- html을 렌더링해주는 별도의 서비스에 연결해 녀석을 렌더링한다. 

이러한 운영 방식의 단점은 다음과 같다. 

- 복잡하다. md를 고치고 html로 저장하고 이를 다시 깃헙을 열어 심어줘야 한다. 뭔가 깔끔하지 않다. 
- html을 렌더링해주는 서비스가 그다지 빠릿빠릿하지 않다. 사라지는 서비스도 있고 렌더링 속도도 만족스럽지 않다. 

# Write Easy Way 

곰곰히 생각해보니 더 쉬운 방법이 있었다. 이 방법을 가능하게 하는 요소는 다음과 같다. 

- 깃헙은 각 리포마다 html을 포워딩해준다. 즉, 리포마다 static web을 만들 수 있다. 주소는 `https://github.com/계정/리포이름` 이런 식으로 들어간다. 이미 html을 렌더링해주는데 굳이 별도의 서비스를 써야 할 이유가 있을까? 
- 문제는 stackedit.io에서 작업한 md 문서를 바로 html로 필요한 리포에 집어 넣는 방법이다. 이를 구현해주는 것이 stackedit의 publish 기능이다. 이 기능을 활용하면 필요한 포맷으로 필요한 위치에 파일을 넣을 수 있다. 

앞서 각 리포의 스태틱웹은 브랜치(일반적으로는 마스터 브랜치)에 `index.html` &rarr; `index.md` &rarr; `README.md` 순으로 문서를 읽어 이 녀석을 주소가 왔을 때 노출한다. 따라서 우리가 만든 문서를 html로 바꾸고 이를 `index.html` 해당 리포에 넣어주면 이 녀석을 저 주소에서 웹에 노출시킬 수 있는 것이다. stackedit.io의 publish 기능이 바로 이것을 실현해준다. 

<p align="center">
<kbd>
  <img width="500" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_7.png?raw=True"></kbd></p>


- 싱크 버튼(원형 화살표)을 누르면 파일이 동기화된다. 즉 작업 중인 md 파일이 동기화된다. 
- 업로드 버튼을 누르면 publish가 구현된다. 즉 이미 지정해둔 파일 형식와 위치에 해당 파일이 푸시된다. 

<p align="center">
<kbd>
  <img width="300" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_6cat.png?raw=True"></kbd></p>

- Publish에서 주의해야 할 것은 "File Path"다. 보통 작성중인 md 파일이 디폴트로 담겨 있다. 그림에서 고양이가 서 있는 부분을 `index.html`로 바꿔주자. 한번만 바꿔주면 이대로 깃헙으로 푸시가 이루어진다. 
- 마지막으로 깃헙 리포의 "Setting"에서 "Github Pages" 옵션을 활성화해준다. 활성화 후 주소를 확인할 수 있다. 

<p align="center">
<kbd>
  <img width="400" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_8.png?raw=True"></kbd></p>

<p align="center">
<kbd>
  <img width="400" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_9.png?raw=True"></kbd></p>

해당 버튼 옆에 깃헙 아이콘은 동기화된 파일로 이동을 바로 구현해준다. 이것도 꽤 편리하게 활용할 수 있다. 구현 방식을 정리해보자. 

1. stackedit.io에서 md를 적성한다. 
2. 적절한 깃헙 리포를 만든다. `https://github.com/계정/리포이름`
3. 해당 리포에 md파일을 저장한다. (사실 md 파일은 다른 곳에 저장되어 있어도 관계 없다) 
4. 해당 md 파일을 `https://github.com/계정/리포이름`에 `index.html`의 이름으로 퍼브리시 한다. 
5. 깃헙 설정에서 홈페이지에서 깃헙 페이지를 활성화하자.
6. 수정 사항이 발생할 경우 stackedit.io에서 md 파일을 수정한 뒤 싱크와 퍼블리시를 하면 된다.  

홈페이지의 구조는 다음과 같다. 편의상 lostineconomics.com을 예로 들겠다.

- lostineconomics.com이 포워딩되는 주소: anarinsk.github.io 
- 개별 포스팅의 주소: anarinsk.github.io/리포주소 (예를 들어, 이 글의 주소는 anarinsk.github.io/lie-build_lie)

별도의 리포를 만드는 것이 번거로워보일 수 있겠다. 이런 관리 방식에는 귀차니즘 비용보다 큰 장점이 있다. 

- 이렇게 별도의 리포로 분리되는 것이 관리하기 편할 수 있다. 만일 포스팅이 많은 데이터나 자료를 품고 있다면 자연스럽게 정리되는 효과가 있다. 
- url 주소 상의 이득이 있다. 즉, ` anarinsk.github.io/[리포이름]` 방식으로 각 포스팅의 주소가 생성된다. 

주의사항! file path에서 디폴트로 주어진 `.md`를 수정하지 않으면 어떤 일이 생길까? 원래 `.md` 파일이 html로 교체되는 대참사(!)가 발생할 수 있다. 하지만 당황하지 마시라. 우리는 github에 파일을 저장하고 있다. 과거의 어느 순간으로도 돌아갈 수 있다! 그래도 귀찮은 일이 생기기 전에 publish에 주의하면 좋겠다. 

stackedit.io 차원에서 제공되는 안전장치도 있다. 아래 history 메뉴를 누르면 자신이 세이브한 어느 순간으로도 돌아갈 수 있다. stackedit.io 자체적으로 돌아가는 git 시스템이다. 훌륭하지 아니한가! 

<p align="center">
<kbd>
  <img width="250" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_11.png?raw=True"></kbd></p>
 
# Customization?

아무리 허름하다고 해도 특화는 필요하다! 예를 들어 Google Analytics를 심고 싶다면 어찌해야 하는가? stackedit.io는 개별적인 특화 기능도 제공한다. "Templates" 메뉴에서 특화된 html 및 스크립트의 코드를 설정하고 이를 페이지에 입힐 수 있다. 

앞서 Publish 메뉴에서 확인할 수 있듯이 자신이 필요한 코드나 스타일(css)을 적용할 수 있는 옵션이 제공된다. 기본 제공되는 네 개의 스타일은 삭제나 수정이 불가능하고, 이를 복사해서 나름의 코드와 스타일을 수정한 뒤 이를 publish 단계에서 적용할 수 있다. 아래 그림 중 박스친 것들은 커스터마즈한 항목의 예시다. 

<p align="center">
<kbd>
  <img width="350" src="https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_12.png?raw=True"></kbd></p>

:house:[lostineconomics.com](http://lostineconomics.com) | Jun Sok Huhh 
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTAxMTkyMzg1LDEwNDY4OTAzMzksLTg1Mj
gzOTkwNywtMTY5NDk5OTgyNCw5MzY4NDc4NzUsLTE0MDI4MjYx
LC0xODg3NTM3NDIxLC05MDAxMDI3MTcsLTIyOTQyMjc0NSwtNT
IzMjAyNzY0LDExODU2ODI1NTQsLTE2OTg3OTgyOTksLTQ5OTQ4
NDc3LDM0NTE4Mzc1OCwtOTkxNDIzMjg2LC05MDIyNjI1NDYsND
I2NTA5MTg0LDczOTg0MDUyMiwxMzAwMzM0MjEzLDE4ODcwMjE1
Nl19
-->