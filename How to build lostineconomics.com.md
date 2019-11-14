
**How to Build lostineconomics.com**
 

2019-11-14

Jun Sok Huhh | :house:[lostineconomics.com](http://lostineconomics.com)

# tl;dr 

- 깔끔함을 빙자한 허름&귀차니즘 홈페이지를 무료로 만들고 싶다면, 나를 따르라~ 

# 뭐 대단한 사이트라고... 

그렇다. 전혀 대단하지 않다. 왜 이런 글을 쓰냐고? 그냥 기록을 위해서다. 미래의 어느 시점에서 다 까먹을 나놈을 위해서 기록을 남겨 놓는 것이다. 혹시라도 도움이 된다면 몹시 고맙겠다. 

![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_1.png?raw=True =600x) 

# Contraints

애초에 이 사이트를 만들면서 몇 가지 제약 사항을 걸었다. 

1. 도메인 구입 비용만 제외하고 github(깃헙)만 쓴다.
2. 과도할 정도로 깔끔한 사이트를 만든다. 
3. 코딩이 포함된 글 이외에 빠르고 쉽게 쓸 수 있어야 한다. 

1이 가능해진 까닭은 github에서 static web을 지원한 덕분이다. github을 이용하면 이용자의 리포지터리 별로 프로젝트 페이지를 만들 수 있다. 이 녀석을 활용하면 Jekyll, Hugo 등을 활용해 github 위에서 제대로 돌아가는 블로그, 홈페이지를 제작할 수 있다. 

문득 마음에 드는 Hugo skin을 고르다가 이런 생각이 들었다. '내가 원하는 건 이런게 아니라, 그냥 블랭크 페이지에 $\LaTeX$ 이 휼륭하게 렌더링되는 정도다. 그런데 이런 미니멀리즘 구현하는 게 의외로 쉽지 않았다. Jekyll이든 Hugo든 모두 블로그를 통으로 관리하게 만든 툴이다. md(markdown)으로 글을 쓰면 여기에 옷을 입히는 형태인데 이 옷을 내 마음대로 제어하는게 쉽지 않았다. 물론 이는 내가 html이나 javascript에 무지하기 때문이다. 이를 잘 알았다면 내가 원하는 형태대로 이리저리 뜯어고칠 수 있었겠지... 

# stackedit.io, the king 

md를 빠르게 로컬에 속박되지 않고 쓰게 해주는 툴들이 많이 있다. 그 중에서 나는 stackedit가 킹왕짱이라고 말하고 싶다. 이유는 아래와 같다. 

![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_2.png?raw=True =250x)

1. github에서 소스를 받아와 웹 브라우저 상에서 구현된다. 개인별 설정은 구글 드라이브 혹은 깃헙 저장한다. 어디써 쓰든 로긴만 하면 동일한 환경이 보장된다. 
2. 위 그림처럼 폴더 버튼을 누리면 외쪽ㅇ로 어떤 것을 썼는지 볼 수 있고 디렉토리 구조로 정리도 쉽게 구현할 수 있다. 
3. md 문서를 다양한 형태로 저장하고, 변형하고, publish할 수 있다. 

![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_3.png?raw=True =250x)

3번이 이채로운 대목이다. 왼쪽 끝의 네모 안에 들어있는 샵을 누르면 그림처럼 메뉴가 펼쳐진다. 

- "Workspace"는 stackedit.io의 여러가지 환경을 저장하는 공간이다. 이 덕분에 서로 다른 장비에서도 로그인만 하면 동일한 결과가 보장된다. 
- "Syncronize" 는 저장을 의미한다. 여러 저장소, 구글드라이브, 깃헙, 드롭박스 등이 지원된다. 같은 md 문서를 여러 개의 저장소에 동시에 저장할 수 있다. 
- import/export는 외부의 문서를 들여오고 내보내는 기능이다. 예를 들어, md로 작성한 문서를 html의 포맷으로 로컬이 다운받을 수 있다. 
- publish가 상당히 특이한 기능인데, 이는 변형된 형태의 문서를 다시 다른 저장소로 내보내는 것을 의미한다. 이 기능이 블로그를 편리하게 운영하는 데 핵심적인 역할을 한다. 

# Basic Scheme 

일단 자신의 깃헙 아이디로 리포지터리(리포)를 딴다. 즉, lostineconomics.com의 경우에는 `anarinsk.github.io`가 된다. 이 주소가 해당 아이디의 대표 주소가 된다. 이 페이지는 일종의 랜딩 페이지, 즉 대문이다. 대문에는 적절한 스타일을 입힐 수 있겠지만, 그런 일은 별로 안 하는 것이 좋다. 대문 페이지의 경우 

- 깃헙에서 제공하는 Jekyll을 활용할 수 있다. lostineconomics.com의 경우 minimal 양식을 활용했다. 
- `_config.yaml` 파일을 거의 다 날리고 필요한 부분만 챙겼다. 
- `_index.md` 파일은 대문에 노출될 콘텐츠를 담고 있다. 새로운 포스트가 생길 경우 이 부분만 수정하면 된다. 이 파일 역시 stackedit.io에 연결해두고 쓰면 편리하다. 직접 둘러보셔도 좋겠다. [https://github.com/anarinsk/anarinsk.github.io](https://github.com/anarinsk/anarinsk.github.io)

# Hard way 

- stackedit.io의 export 기능을 활용했다. 그럼처럼 `import/export` &rarr; `export as HTML`로 html로 로컬에 저장한다.
- 해당 html을 github의 public 리포에 올려둔다. 
- html을 렌더링해주는 별도의 서비스에 연결해 녀석을 렌더링한다. 

이러한 운영 방식의 단점은 다음과 같다. 

- 복잡하다. md를 고치고 html로 저장하고 이를 다시 깃헙을 열어 심어줘야 한다. 뭔가 깔끔하지 않다. 
- html을 렌더링해주는 서비스가 그다지 빠릿빠릿하지 않다. 없어지는 서비스도 있고 렌더링도 느린 경우도 종종 있다. 

# Easy way 

곰곰히 생각해보니 더 쉬운 방법이 있었다. 이 방법을 가능하게 하는 요소는 다음과 같다. 

- 깃헙은 각 리포마다 html을 포워딩해준다. 즉, 리포마다 static web을 만들 수 있다. 주소는 `https://github.com/계정/리포이름` 이런 식으로 들어간다. 이미 html을 렌더링해주는데 굳이 별도의 서비스를 써야 할 이유가 있을까? 
- 문제는 stackedit.io에서 작업한 md 문서를 바로 html로 필요한 리포에 집어 넣는 방법이다. 이를 구현해주는 것이 stackedit의 publish 기능이다. 이 기능을 활용하면 필요한 포맷으로 필요한 위치에 파일을 넣을 수 있다. 

앞서 각 리포의 스태틱웹은 브랜치(일반적으로는 마스터 브랜치)에 index.html &rarr; index.md &rarr; README.md 순으로 문서를 읽어 이 녀석을 주소가 왔을 때 노출한다. 따라서 우리가 만든 문서를 html로 바꾸고 이를 `index.html` 해당 리포에 넣어주면 이 녀석을 저 주소에서 웹에 노출시킬 수 있는 것이다. stackedit.io의 publish 기능이 바로 이것을 실현해준다. 

![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_7.png?raw=True =300x)

- 싱크 버튼(원형 화살표)을 누르면 파일이 동기화된다. 즉 작업 중인 md 파일이 동기화된다. 
- 업로드 버튼을 누르면 publish가 구현된다. 즉 이미 지정해둔 파일 형식와 위치에 해당 파일이 푸시된다. 
![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_6.png?raw=True =300x)
- Publish에서 주의해야 할 것은 "File Path"다. 보통 작성중인 md 파일이 디폴트로 담겨 있다. 녀석을 `index.html`로 바꿔주자. 한번만 바꿔주면 이대로 깃헙으로 푸시가 이루어진다. 
- 마지막으로 깃헙 리포의 "Setting"에서 "Github Pages" 옵션을 활성화해준다. 활성화 후 주소를 확인할 수 있다. 

![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_8.png?raw=True =300x)

![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_9.png?raw=True =300x)

해당 버튼 옆에 깃헙 아이콘은 동기화된 파일로 이동을 바로 구현해준다. 이것도 꽤 편리하게 활용할 수 있다. 구현 방식을 정리해보자. 

1. stackedit.io에서 md를 적성한다. 
2. 적절한 깃헙 리포를 만든다. `https://github.com/계정/리포이름`
3. 해당 리포에 md파일을 저장한다. (사실 md 파일은 다른 곳에 저장되어 있어도 관계 없다) 
4. 해당 md 파일을 `https://github.com/계정/리포이름`에 `index.html`의 이름으로 퍼브리시 한다. 
5. 깃헙 설정에서 홈페이지에서 깃헙 페이지를 활성화하자.
6. 수정 사항이 발생할 경우 stackedit.io에서 md 파일을 수정한 뒤 싱크와 퍼블리시를 하면 된다.  

홈페이지의 구조는 다음과 같다. 편의상 lostineconomics.com을 예로 들겠다.

- lostineconomics.com이 포워딩되는 주소: anarinsk.github.io 
- 개별 포스팅의 주소: anarinsk.github.io/리포주소 

별도의 리포를 만드는 것이 번거로워보일 수 있지만, 사실 이렇게 별도의 리포로 분리되는 것이 관리상 편할 수 있다. 만일 포스팅이 많은 데이터나 자료가 동원된다면 오히려 자연스럽게 정리되는 효과도 있다. 
 
# Customization! 

아무리 허름하다고 해도 특화는 필요하다! 예를 들어 Google Analytics를 심고 싶다면 어찌해야 하는가? stackedit.io에는 개별적인 특화 기능도 제공한다. "Templates" 메뉴에서 특화된 html을 설정하고 이를 저장할 수 있다. 앞서 Publish 이미지에서 확인할 수 있듯이 해당 스타일을 적용할 수 있는 옵션을 제공한다. 

![enter image description here](https://github.com/anarinsk/lie-build_lie/blob/master/assets/imgs/img_10.png?raw=True =300x){: .mycenter}

:house:[lostineconomics.com](http://lostineconomics.com) | Jun Sok Huhh 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI4NzY0NjA5MiwtMTc5NDA0NDc0MywzNz
UyMzM3OThdfQ==
-->