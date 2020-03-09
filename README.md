요즘 사용하는 오픈소스 입력기가 마음에 들어 소개하고자 합니다.

[##_Image|kage@bK5Dsp/btqB0gelQYN/cZWATGnmnRxuRVKLJfLSLK/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|||_##]

nimf라는 입력기인데, nimf의 뜻은 nimf is an input method framework라고 합니다. 재귀적인 이름부터 근본이 넘치죠? GNU가 Gnu is Not Unix였던거 생각하면 근본력부터가 다릅니다.

ibus 한글 입력기의 경우, twitter 공식 웹사이트나 pycharm이나 clion등 제트브레인사의 IDE에서 끝 글자가 씹히는 버그가 아직도 안잡히고 있는데, nimf는 그런거 없습니다. 

그렇다고 한글만 지원하냐? 절대 아닙니다. 다국어 입력기에요. UI도 깔끔하고, 시스템 트레이에 뜨는 아이콘도 너무 귀엽습니다. 최고에요.

[##_Image|kage@8IvqA/btqBW1pRkiw/vDEDNlFcf6QXvzz4wyAcw0/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|'한' 겁나 귀엽지 않습니까?||_##]

근데 문제는 현재 nimf 개발이 진행되지 않고 있어서, 패키지저장소에서는 outdated라고 뜹니다. (apt저장소는 모르겠습니다만 최소한 yaourt에서는 그렇습니다.) 따라서 nimf 의존성 패키지들을 yaourt로 한번에 깔고, gitlab에 있는 파일을 수정해서 수동으로 설치합니다.

> yaourt nimf

[##_Image|kage@cbo1WG/btqBZsfl8q4/7vRxcC17RdCKt3aoKp6bTK/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|||_##]

어차피 의존 패키지만 깔고 빌드해도 GTimeVal에서 오류가나서 빌드가 안되니, PKGBUILD 편집 스킵하고 바로 깝시다.

이후 [https://gitlab.com/nimf-i18n/nimf/](https://gitlab.com/nimf-i18n/nimf/) 에 가서, 파일을 다운받거나 클론을 뜹니다.

[

nimf-i18n / nimf

Nimf is an input method framework https://nimf-i18n.gitlab.io

gitlab.com



](https://gitlab.com/nimf-i18n/nimf)

[##_Image|kage@bwsQJb/btqBWDbIpAR/Qozeq9Zf55Q2WXoT9IYKeK/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|개발자 선생님 정말 감사합니다. (--)(__)||_##][##_Image|kage@ldT8x/btqBZqht3uD/BQmlEsVNFaO2KyeQdQTY6K/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|||_##]

이후 configure.ac를 텍스트 에디터로 열어서 편집해줍니다.

[##_Image|kage@nSlkM/btqBZglQxcw/kYbaeNkLGoYXTlkb6RSeZ1/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|||_##]

25번째줄을 보면

> EXTRA\_CFLAGS="-Wall -Werror"

이라고 되어 있는데, 이를 

> EXTRA\_CFLAGS=”-Wno-error”

바꾸고 저장합니다.

참고자료: [https://blog.enyou.kr/archives/424](https://blog.enyou.kr/archives/424)

[

우분투 19.10에서의 nimf 설치 – Atelier Enyou

우분투 19.10에서의 nimf 설치 nimf는 리눅스 한글 입력기 중에서 거의 유일하다시피 첫 글자 및 끝 글자 버그가 발생하지 않는 입력기이다. 그렇기 때문에 기분 좋은 한글 생활을 위해서는 nimf가 필수이지만, 최근 안 좋은 사건으로 인해 개발을 하시던 분이 개발을 그만 두게 되었다. 다행히도, 저장소와 gitlab을 남겨두셨기 때문에 우분투 19.04 이하 사용자는 PPA 저장소를 이용하면 되고, 19.10 이상 사용자라면 gitlab의 빌드 절

blog.enyou.kr



](https://blog.enyou.kr/archives/424)

**Update. 2020/03/08 10:44 PM**

**위의 과정이 귀찮으신분은 제가 포크뜨고 에러 무시하게끔 수정한 레포지터리를 사용하셔도 됩니다. **

**\+ 님프는 한국어 입력기가 아니라 다국어 입력기 입니다.**

**[https://github.com/sheepjin99/nimf](https://github.com/sheepjin99/nimf)**

[

sheepjin99/nimf

우주최강 다국어 입력기 nimf. Contribute to sheepjin99/nimf development by creating an account on GitHub.

github.com



](https://github.com/sheepjin99/nimf)

이후 터미널에서 ./autogen.sh 를 실행합니다.

[##_Image|kage@sAqhR/btqBZMdwpwp/nDulxOR8Z2XEoNdQ3mK9Z0/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|||_##][##_Image|kage@cj6UkI/btqBXFmAEhK/TRN4gBqgCwPSL2XoEmGg7k/img.png|alignCenter|data-origin-width="0.0" data-origin-height="0.0"|||_##]

이후는 님프 깃랩([https://gitlab.com/nimf-i18n/nimf/](https://gitlab.com/nimf-i18n/nimf/))을 따라하면 정말 잘 설치됩니다! 

제가 이 입력기를 사랑하는 이유는 

1\. 트위터 공식 웹사이트에서 끝 단어가 사라지는 버그가 없습니다.(중요)

2\. 타이핑을 할 때 뭔가 착착 달라붙는 느낌입니다. 반응속도에도 차이가 있으려나요? 플라시보일지도 모릅니다.

GTimeVal 에러를 넘어가는 방식을 취했지만 나중에 deceperated 되면 nimf를 사용하지 못할수도 있겠네요 ㅠㅠ 

아직은 가이드를 따라하는 수준밖에 못되지만 공부 열심히해서 고쳐보고 싶습니다...
