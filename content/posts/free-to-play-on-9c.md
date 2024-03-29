+++
title = '무료 플레이, 초대 코드, 그리고 온보딩 포탈'
date = 2022-10-27
draft = false
+++

이 글에서는, [플라네타리움]이 탈중앙 멀티플레이 게임인 [나인 크로니클]을 [Libplanet]과 함께 만들면서 알게 된 여러가지 일화들을 소개합니다. 어떤 것들은 그저 재미로 볼만한 것도 있는가하면, 경우에 따라선 꽤 교훈적인 일화일 수도 있는 그런 이야기들인데, 최대한 읽는 분들께 보탬이 되었으면 하는 생각입니다.

처음 이 글의 제목은 "나인 크로니클에서 배운 것들" 이었습니다. 그리고 제목에 걸맞게 이런 저런 주제들을 가볍게 다루는 그런 글이 되리라 예상했습니다. 하지만 막상 작성을 해보니, 특정 주제들에 대해서 길게 다루고 글을 나누는 게 낫겠다는 생각이 들어 주제를 좁히게 되었습니다.

[플라네타리움]: https://planetariumhq.com
[나인 크로니클]: https://nine-chronicles.com
[Libplanet]: https://libplanet.io

# 수수료 없는 블록체인

처음 Libplanet과 그를 이용한 탈중앙 게임[^12]을 구상할때, 저희는 이런 의문을 가졌습니다.

> 블록체인을 기반으로 한 탈중앙 애플리케이션에서, 토큰은 반드시 필요한가?

[비트코인(Bitcoin)][Bitcoin]이나 [이더리움(Ethereum)][Ethereum] 같은 것들이 이미 나와있는 시점에서, 이런 물음은 사실 "필요치 않다." 라는 결론을 어느 정도 암시하는 느낌도 들죠. 실제로 저희는 Libpalnet 을 만들 때, 이 라이브러리가 단순히 토큰이나 코인의 거래만을 다루는 것뿐만 아니라 게임의 전체 상태를 전부 포함하게 하고 싶었고,  어쩌면 이런 자산은 상대적으로 덜 중요한 것이었습니다.

여기에 연결되는 아이디어는 한 가지 더 있었는데,

> 꼭 모든 트랜잭션에 수수료가 필요할까? 채굴자[^1]가 게임의 이해 당사자라면 이런 인센티브를 굳이 주지 않아도 괜찮지 않을까?[^2]

저희는 당시 이더리움 네트워크에서 돌아가는 많은 [분산 애플리케이션(dApp)][dApp]들처럼, 트랜잭션을 실행하기 위해 수수료를 지불하는게 싫었고 이를 없애고 싶었죠. 왜냐하면 많은 게임들이 무료 플레이를 플레이어 유입을 위한 핵심 컨셉으로 가져가고 있었고, 저희도 그를 따르고 싶었기 때문입니다. 하지만 저희가 만드려는 스타일의 무허가형 네트워크에서, 무턱대고 수수료를 없애버리면 [채굴자는 블록에 트랜잭션을 포함할 인센티브가 사라집니다.][1]

당시 거론된 다른 문제 한가지는, 네트워크 전체에 트랜잭션을 무제한으로 송신할 수 있게 된다는 점입니다. 비트코인이나 이더리움처럼 [타원 곡선 전자서명(Elliptic Curve Digital Signature, ECDSA)][ECDSA]에만 의존할 뿐, 계정 자체에 [EOS]처럼 계정명을 따로 등록한다던지하는 별도의 신원 식별 시스템이 없는 무허가형 네트워크이기에, 이것 역시 큰 위협으로 여겨졌죠. 오히려 당시엔 "이기적 채굴" 보다 트랜잭션의 총량을 제어할 수 없다는 문제의식이 더 컸던 걸로 기억합니다.

# 초대 코드 (Invitation Code)

"초대 코드(Invitation Code)"[^3]는 이런 트랜잭션 총량 문제를 해결하기 위해 제안된 시스템으로, 동작하는 방식은 대충 이렇습니다.

1. 임의의 비대칭 키를 여러 개 만들어 체인 상태에 저장합니다. 
2. 그 비대칭 키의 개인키를 코드로서 발급합니니다.
3. 사용자는 발급받은 개인키를 활성화 액션(`ActivateAccount`)으로 만들어 트랜잭션을 서명한 다음 체인에 보냅니다.
4. 활성화 액션이 포함되지 않은, 모든 트랜잭션은 위의 활성화 과정을 거쳐야만 올바른 트랜잭션으로 간주되며 나머지는 버려집니다.

이렇게 해두면 전체 네트워크의 트랜잭션양은 발행한 코드로 제어할 수 있을 것 같습니다. 하지만 여기에는 몇가지 놓친 부분이 있었죠.

1. 임의의 비대칭키를 누군가 만들어서 체인 상태에 저장하는 것은, 이미 활성화 된 특정 사용자를 가정합니다. 이를 위해 일종의 "관리자" 같은 게 필요했죠.
2. 활성화 액션 역시 트랜잭션에 넣어서 보내야하기 때문에, 이 액션이 들어간 트랜잭션은, 설령 비활성화된 사용자라 한들 체인 정책에 의해서 허가해줘야 합니다. 즉 엄밀하게는 트랜잭션의 총량 제어가 되지 않습니다.
3. 초대 코드를 통한 활성화 시스템은 계정에만 영향을 줍니다. 이미 활성화 된 계정의 트랜잭션 총량을 제어하고 채굴자에게 인센티브를 주기 위해선 별도의 메커니즘이 필요합니다.
4. 초대 코드의 발행을 통제하는 시스템도 필요합니다. 또한 이 시스템에서 헛점이 있다면 [시빌 어택(Sybil Attack)][Sybil Attack]에 노출되고 위의 가정이 전부 무효해집니다.

이런 크고 작은 문제를 안고 있었지만 이 역시도 감내하고 가기로 합니다. 시작은 저희가 도맡아서 찍더라도, 언젠가는 하드포크를 거쳐 다른 사용자들이 만들 수 있게 하리라 다짐하면서요. [^4] [^5]

# 온보딩 포탈(Onboarding Portal)

제가 처음으로 기억하는 온보딩 포탈의 처음 목적은, 게이머들에게 NCG를 공급하기 위함이었습니다. 나인 크로니클은 최근의 모바일 게임들처럼 각종 퀘스트를 클리어 했을 때 NCG를 주고 싶었는데, 이는 플레이 동인을 유지하기 위함도 있었지만, 당시에는 플레이어들이 NCG를 수급할 방법이 전혀 없어, NCG를 쓰리라 가정한 다른 게임 기획이 동작하지 않는 문제가 있기도 했기 때문이죠. [^6] 그래서 어떤 분들은 "브릿지를 통해 시장에서 NCG 수급이 가능해진 이상, 온보딩 포탈이 더이상 불필요한 것 아닌가" 라고 말씀하시기도 하는데, 이후 활성 사용자 수(Daily Active User, DAU)나 잔존율(Retention)등을 관리하기 위한 목적이 커진 점을 고려할때, 아마 힘들지 않았을까 합니다.

온보딩 포탈은 재원을 프로토콜로 충당하는 것이 아니라 재단 준비금(`0xebCa4032529221a9BCd3fF3a17C26e7d4f829695`)으로 충당하며, 프로토콜이 아닌 플라네타리움에 의해 운영되는 서비스입니다. 초기엔 아주 간단한 파이썬(정확히는 [Flask] 기반) 웹서비스[^7] 였는데, 이후 신규 유입을 늘리기 위한 각종 그로스 해킹을 하면서 점차 고도화 되었습니다. 그리고 이 과정에서 등장한, 지금까지 저희를 괴롭히는 문제가 바로 다중 계정 문제입니다.

# 다중 계정

온보딩 포탈이 출범하면서 저희는 초대 코드를 온보딩 포탈을 통해 전송토록 했습니다.[^8] 온보딩 포탈은 블록체인으로 운영되는 탈중앙 서비스가 아니기에 [트위터][Twitter] 계정 연동에 기반한 독자적인 계정 체계를 가지고 있습니다. 트위터로 로그인 한 사용자가 자신의 나인 크로니클 주소를 입력하면 연동되는 방식이죠.

문제는, 이 트위터 계정이 너무 만들기 쉽다는 것입니다. 메일 주소만 있으면 만들 수 있는데, 이 역시 gmail등에서 지원하는 [라벨링 기능][2]을 사용하면 우회가 가능했죠. 이를 통해 한 사람에 의한 여러 계정, 즉 다중 계정(Multi Account)를 손쉽게 만들 수 있게 되었습니다. 이를 통해 포탈의 각종 퀘스트 보상을 자동화해서 편취하거나, 여러 계정을 사용할 때 게임에서 얻는 이점[^9]등을 활용해 다른 플레이어들보다 손쉽게 우위에 설 수 있게 되었죠.

커뮤니티는 분노했고, 이런 다중 계정과 봇(Bot)을 이용한 플레이를 제재해야 한다는 목소리도 높아졌습니다. 많은 게임들이 그렇듯, 봇들과의 전쟁을 선포하고 어쩌면 빠르게 종식될 수 있떤 이 문제가, 보다 복잡하게 된 것은 크게는 2가지 이유가 있었습니다.

## 나인 크로니클의 "공정"

나인 크로니클은 많은 탈중앙 애플리케이션들처럼 프로토콜에 의해 다양한 구현(e.g., [Go Ethereum][geth] - [Nethermind]) 이 나오는 것을 장려하자는 기조를 가지고 있었습니다. 그렇기에 저희는 몇몇 플레이어들이 플레이의 많은 부분을 자동화하는 것을 보고 열광했습니다. [^10] 대충 이런 느낌이었죠.

> 우린 봇(Bot)이 나와도 괜찮은, 나아가 봇을 장려하는 게임을 만들 것이다.

하지만 저희는 이더리움이나 비트코인이 아니었습니다. 저희는 여러가지 다양한 이유로 플레이어들에게 시간과 노력에 비례하여 보상이 지급되는데다, 그것이 바깥 세상에서 거래되기까지 하는 그런 게임을 만들고 있었죠. 사람들은, 자신의 노력이 누군가의 코드로 너무나 손쉽게 대체되는 현상에 적개심을 갖고 있었습니다. 생각해보면 세상의 일반적인 게임들에선 그게 당연하긴 하죠. (실효성은 차치하더라도) 매크로를 단속하며 "정상적인 플레이"를 강조하는 것은 그저 게임사들이 통제 중독에 빠져있거나 지독하게 보수주의적이라서 면책 조항을 갖고 싶은 것뿐만은 아닙니다. 많은 멀티 플레이어 게임에서 플레이어들이 기대하는 것은 현실보다 더 "공정(Fair)"한 결정입니다. 그렇기에, 게임에서 내가 할 수 없는 일을 남이 하는 것들을 볼 때마다 많은 플레이어들은 각자의 마음 속에 사는 "공정"에게 가서 묻습니다. - "이거 규칙 위반 아닌가요?"

하지만 여기까진 그나마 괜찮습니다. 비록 정도의 차이는 있을 지언정, HUD 등의 모딩을 묵인하거나 나아가 권장하는 기성 게임들도 있으니까요. 거기에 "나인 크로니클"은 플레이어간의 직접 경쟁형 게임은 아니기 때문에, 이런 자동화가 FPS의 [에임핵(Aimbot)][aimbot] 만큼이나 치명적인건 아니었거든요. 그래서 이건 이해하지 못하는 플레이어들에게, "나인 크로니클의 공정"(i.e., 자동화도 게임의 일부다)을 그저 잘 "설명"을 하면 되는 문제라고 볼 수도 있습니다.

## "포탈의 것은 포탈에게" 가 불가능한 이유

많은 경우에 봇, 그리고 자동화에 대한 성토를 거슬러 올라가다보면, 결국 자동화 자체보단 이런 자동화가 없이는 성립할 수 없는 다중 계정에 대한 문제로 귀결됩니다. 다시 말하면, 여러 계정에서 얻는 이득이 게임을 불공정하게 하고 망친다는 것이죠. 여기서 저는 어떤 중대한 오판을 하고 있었습니다.

> 신원 인증의 책임이 포탈에 있고, 또 이런 다중 계정의 이득이 포탈의 보상 뿐이라면, 이는 프로토콜과 무관한 문제이다.

이건 명백히 사실이 아닙니다. 왜냐면 저희가 만든 규칙들이 그렇지 않거든요. 자연히 생기는 자원인 AP는 계정에 귀속되기에, 이 계정 갯수가 곧 자원의 전체 생산량을 결정합니다. 단순히 포탈의 금고를 텅 비게 하는 문제가 아니라, 게임의 가정을 뒤흔드는 프로토콜 이슈이자 결함입니다. 만약 저희가 저 위의 프로토콜과 계정 발급을 진정으로 나눠서 생각하고 싶었다면, AP와 거기서 변환되는 게임 내 모든 자산들에 대한 근본적인 가정부터 다 바꿨어야 하는 겁니다. 그리고 그런 기능이 더 추가되지 못하게 막았어야 하죠. 아니면, 정말로 저 AP의 총량을 제어하는 문제를 다른 무엇보다 시급하게 구현했던지요.

하지만 이런 뻔한 사실조차 깨닫지 못한 채 시간은 흘러갔습니다. [^11] 그저 "봇을 권장하는 게임을 만들자" 라고만 되뇌이며 말이죠.

# 마세라티 문제

온보딩 포탈을 둘러싼 모든 문제가 다 이런 정책적인 모순에 기반한 것만 아니었습니다.

온보딩 포탈은 탄생 배경에서 알 수 있듯이, 굉장히 기민(Agile)하게 만들어졌습니다. 흔히 엔지니어들사이에서 [마세라티 문제(Maserati Problem)][Maserati Problem]라고 하는 게 있는데, 마세라티 살 돈이 없는 시점에, 모델과 색상을 고민해봐야 소용 없다는 격언이죠. 많은 실용주의 엔지니어들이 이 경구를 마음에 새기고, 몇명이 들어올지도 모를 서비스의 확장성보다 기능 구현을 빠르게 해서 전체적인 사용 흐름을 검증하는 것을 중요시합니다. 온보딩 포탈 역시 처음엔 그 기조에 충실하게 개발되었고, 덕분에 갑작스러운 개발에도 초기 사용자 유입이라는 과업을 성공적으로 달성했죠.

문제는, 이런 스타일의 개발 방식은 어느 순간엔 빚을 갚거나 혹은 아예 모라토리엄을 선언하고 효용을 포기해야 하는 순간이 온다는 것입니다. 마세라티를 진짜로 사야 할 때가 오긴 한다는 거죠. 그럼 "그 때는 그 고민을 행복하게 하면 되지 않느냐?"라는 생각이 드실 수도 있지만, 이게 또 마냥 행복할 수만은 없었습니다.

- 확장성과 안정성을 챙기는 엔지니어링은 그 나름의 전문성과 숙련도를 요구합니다. [^13] 현대의 안정적인 서비스들은 이를 높이기 위해서 다양한 기술들을 섞어서 사용해야 할 때가 있는데, 어떨 때 어떤 패턴을 써야 하는가는 경험에 의존하는 부분도 많기에 더더욱 골치아프죠. 아쉽게도 온보딩 포탈은 여러가지 이유로 인해 이런 경험있는 엔지니어들보다 웹 개발 경험이 그렇게 많지 않으신 주니어 엔지니어나, 다른 팀의 숙련된 백엔드 엔지니어가 일과를 쪼개서 도와주시는 정도로만 유지되어 왔습니다.
- 온보딩 포탈은 나인 크로니클 메인넷에 있는 계정 사용자의 정보를 조회하고, 출금 신청을 받으면 송금해주는  일을 합니다. 즉 나인 크로니클 메인넷, 정확히는 여기 연결되어 있는 RPC 노드에 강하게 의존하고 있는데요. 골치아픈건 이 RPC 노드가 엄청나게 불안정[^14]했다는 겁니다. 정보를 조회하기 위해 쿼리 요청을 보내면 때때로 결과가 아주 느리게, 혹은 아예 안날아오기도 하고, 송금을 하겠다고 트랜잭션을 보내면 이게 사라져있기도 했죠.
  - 물론 [마이크로 서비스 아키텍쳐(Microservice Architecture, MSA)][MSA]와 같이 아예 서비스를 나눌 것을 장려하는 개발 방법론도 있고, 그런 방법론들에서도 이런 서비스간의 불안정성은 설계에 고려해야 할 요소입니다. [장애 극복(Failover)][Failover]와 같은 고전적이고 단순한 개념부터 [배압(Backpressure)][Backpressure] 같은 개념도 있죠.
  - 다만 위에서 말한 것들처럼 이건 전문성과 숙련도에 많이 좌우되는 영역이고, 아쉽게도 포탈은 기술적인 기여라는 관점에선 이런 혜택을 많이 누리지 못해왔습니다.

그나마 천만 다행인것은 팀전체에서 관련 경험이 있는 엔지니어들이 그래도 있었기에, 위기 상황마다 최소한의 응급조치는 해가면서 버틸 수 있었습니다. 하지만 적어도 제가 볼 때 그들은 다들 마세라티를 고르는 것처럼 행복해보이진 않았습니다.[^15] 

전 이런 기여가 지속적으로 이어지려면 투자 의사뿐 아니라 일종의 동기 부여[^16]가 필요하다고 생각합니다. 그리고 여기서 온보딩 포탈의 배경과 목적을 되짚어보고, 현재까지의 플레이어 초기 유입을 어떻게 볼 것인가에 대한 평가와 분석이 선행되어야 할 것입니다. 그리고 미결 과제인 계정 갯수에 비례하는 자원 시스템과 이에 수반되는 다중 계정 제재에 대해, (전역 자원 제한이건, AP 순환 + 초대 코드 존치건) 최소한 실행은 해본 안이 있으면 더 좋겠죠.

# 부록 - 네트에 걸린 테니스 공[^18]

몇몇 분들은 저에게 이렇게 물으십니다.

> 맞아요. 그러니까 그걸 조금씩이라도 해야하는데, 왜 기여하는 팀이 아무도 없죠?

여기에 대한 저의 아주 치사한 버전의 변명은 이럴 것입니다.

> AP나 다른 재화 시스템을 게임팀 (기획팀, 클라팀)에서 주로 제안하고 구현하시니까, AP 순환과 초대 코드 인센티브도 게임팀에서 하실 거라고 생각했어요.

(대부분의 치사한 변명이 그렇듯이) 그다지 건설적이거나 올바르진 않은데, 제가 정말로 저렇게 믿었다면 게임팀의 다른 모든 (기획을 포함한) 개발 일정을 취소시키고라도 저걸 우선하셔야 한다고 주장했어야 했기 때문입니다. 혹은, 위의 초대 코드처럼 아주 간단한 거였다면 그냥 제가 혼자 구현하고 말았겠죠. 

아마 저 변명의 아주 솔직한 버전은 이걸겁니다.

> 크고 복잡한 일인데 제가 지지하는 방향[^17]도 아니라서, 그저 남이 해주길 바라며 미루고 있었습니다.

그저 솔직하다고해서 옳지 않은 일이 옳은 일이 되는 것이 아니고, 없던 쓸모가 갑자기 생기는 게 아니죠. 어쩌면 이 글은 저런 치사한하거나 솔직한 변명에 대한 제 반성에서 시작한 것일지도 모릅니다.


# 마치며

분명히 흥미나 정보 제공을 목적으로 글을 적기 시작했지만, 상상 속 독자들의 피드백을 듣다보니 무언가를 주장하고, 또 변명하는 글이 되어버렸네요. 조금이라도 본래의 취지(?)를 살려 요약하면 이런 내용일 것입니다.

* Libplanet과 나인 크로니클은 수수료 없는 무허가형 탈중앙 게임을 의도했지만 처음 가정만으론 부족했습니다.
* 초대 코드는 이런 초기 가정의 부족함을 보완하는 장치로 고안되었으나 완전히 완성되기 전에 출시되었습니다.
* 온보딩 포탈은 시장에 NCG 공급이라는 목적으로 개발되었지만, 초대 코드 발행의 유일한 수단이기에 다중 계정 문제의 최전선이기도 합니다.
* 나인 크로니클은 계정 숫자에 프로토콜의 "공정"이 영향을 받는 상태이며 이는 자동화에 대한 이해와 구분하여 다룰 필요가 있습니다.
* 온보딩 포탈은 위의 프로토콜 결함 외에도 여러가지 내외부적 기술적 문제가 있는 상태인데, 이를 잘 해결하기 위해서도 계정과 재화에 관한 관점이 정리될 필요가 있습니다.


[^1]: 이 글이 작성되는 22년 10월 기준, Libplanet은 [작업 증명(Proof of Work, PoW)][PoW]만을 지원합니다.
[^2]: [제 이전 글][신뢰하지 않을 자유]을 읽어보신 분이라면 이미 짐작하시겠지만, 이 가정은 이후에 큰 비극을 불러옵니다. 여기에 대한 이야기는 뒤에 다시 나옵니다.
[^3]: 제가 올렸던 초기 제안에서는 이를 활성화 키(Activation Key)라고 불렀습니다. 이후 기획 의사 결정에 따라 개명되었습니다.
[^4]: 개인적으론, 초대 코드를 완전히 철폐하고 이더리움이나 비트코인처럼 공통 자산으로 수수료를 내는 안을 더 지지하는데, 초대 코드 발행/인센티브 설계가 복잡하고, 별도 메커니즘(i.e., AP 순환 시스템)이 어차피 필요하며, 여전히 활성화 액션에 대한 헛점이 남아있기 때문입니다.
[^5]: 한편 무료 플레이의 가치를 지지하는 측에선, 초대 코드 발행 프로토콜화 + AP 순환 시스템을 지지하는 편입니다.
[^6]: 때문에, 당시에는 온보딩 포탈을 P2E(Play To Earn) 포탈이라고 부르기도 했습니다.
[^7]: 이는 초기 작업자였던 JC가 파이썬 웹개발이 가장 익숙했기 때문으로 추정됩니다.
[^8]: 포탈이 나오기 전 초대 코드는 메일링 리스트에 대기 중인 사람들의 이메일로 전송되었습니다.
[^9]: 수수료 없이 계정당 자연 회복되는 AP에만 의존하는 Libplanet/나인 크로니클의 설계 상, 별도의 고려가 되어있지 않다면 이는 치명적인 문제가 됩니다.
[^10]: 아주 엄밀히 이야기하면, 이런 클라이언트 수준의 자동화와 구현을 통째로 새로 만드는 일, 그리고 프로토콜에 제안하는 일은 각각 다른 성격의 일이긴 합니다.
[^11]: 뒤에 소개할 글들에 대한 복선이자 변명이지만, 다양한 일들이 있긴 했습니다. 하지만 이 우선순위 선정만은 명백하게 실수라고 생각합니다.
[^12]: 나인 크로니클은 JC가 작성한 [Nekoyume]에서 많은 컨셉을 따와 만들어졌지만, 이름이 정해진 건 한참 뒤의 일이었습니다.
[^13]: 영입 단계에서 평가시 유독 평가가 엄하다고 지적받는 저이지만, 적어도 이 부분에 있어서는 타협이 어려운 이유이기도 합니다.
[^14]: 과거형으로 적혀있지만, 현재 진행형이기도 합니다.
[^15]: 물론 저도 마세라티를 직접 사본 적은 당연히 없기에 그게 정확히 어떤 기분인진 모르며 그저 추측할 뿐입니다.
[^16]: 사람마다 동기 자체는 다 제각각이기에 "동기" 자체는 목표로 적합하지 않을 수 있습니다. 정확히는 "동기가 부여될 만큼의 서사"가 필요하다는게 맞겠네요.
[^17]: 다른 각주에서 밝힌 것처럼, 저는 초대코드 존치와 인센티브 설계보다 (설령 일반적인 게임성을 일부 희생하더라도) 전역 자원에 의한 제한을 지지합니다.
[^18]: 일본의 만화 [죠죠의 기묘한 모험(ジョジョの奇妙な冒険)][ジョジョの奇妙な冒険] 시리즈 7부인 [스틸 볼 런(スティール・ボール・ラン)][スティール・ボール・ラン]에서 주인공의 조력자(정확히는 조력자의 아버지)가 한 말[^19]입니다.
[^19]: "네트에 걸려서 튀어오른 공은 운명이니 사람이 관여할 것이 아니다." 라는 지론을 가진 줄 알았던 아버지가, 사실은 모순적이게도 기적을 바라는 마음도 가지고 있었다는 내용입니다.

[Bitcoin]: https://bitcoin.org
[Ethereum]: https://ethereum.org/
[EOS]: https://eos.io/
[PoW]: https://en.wikipedia.org/wiki/Proof_of_work
[dApp]: https://en.wikipedia.org/wiki/Decentralized_application
[신뢰하지 않을 자유]: https://gist.github.com/longfin/019e0067275d134f4302539d2ddbff06
[1]: https://github.com/planetarium/libplanet/issues/546
[2]: https://support.google.com/a/users/answer/9282734
[Sybil Attack]: https://en.wikipedia.org/wiki/Sybil_attack
[Twitter]: https://twitter.com
[geth]: https://geth.ethereum.org/
[Nethermind]: https://nethermind.io/
[Flask]: https://flask.palletsprojects.com/
[aimbot]: https://en.wikipedia.org/wiki/Cheating_in_online_games#Aimbots_and_triggerbots
[Nekoyume]: https://nekoyu.me/
[MSA]: https://microservices.io/
[Failover]: https://ko.wikipedia.org/wiki/%EC%9E%A5%EC%95%A0_%EA%B7%B9%EB%B3%B5_%EA%B8%B0%EB%8A%A5
[Backpressure]: https://medium.com/@jayphelps/backpressure-explained-the-flow-of-data-through-software-2350b3e77ce7
[ECDSA]: https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm
[Maserati Problem]: https://www.quora.com/Whats-a-Maserati-Problem
[ジョジョの奇妙な冒険]: https://ja.wikipedia.org/wiki/%E3%82%B8%E3%83%A7%E3%82%B8%E3%83%A7%E3%81%AE%E5%A5%87%E5%A6%99%E3%81%AA%E5%86%92%E9%99%BA
[スティール・ボール・ラン]: https://ja.wikipedia.org/wiki/%E3%82%B9%E3%83%86%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%BB%E3%83%9C%E3%83%BC%E3%83%AB%E3%83%BB%E3%83%A9%E3%83%B3
