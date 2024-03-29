+++
title = 'Web3적인, 너무나도 Web3적인'
date = 2022-10-21
draft = false
+++

이 글에서는 [Web3]라고 불리는 개념에 대해 제가 이해하고 있는 바와 사람들의 기대에 대해 소개하고, 그를 달성하기 위한 필요한 것들에 대해 적어두려 합니다. 물론 제 주장이나 견해가 주가 되겠지만, 이 글의 목적은 그것들을 여러분에게 관철시키는 것이 아닙니다. 오히려 저는 지금으로선 이 글이 다양한 논의의 시발점이 되길 바라는 마음이 더 크기에, 될 수 있으면 여러 시각을 균형있게 소개하고 싶습니다.

여담으로, 이 글의 제목은 [요코미조 세이시(横溝正史)][横溝正史] [^1]의 추리소설 [옥문도(獄門島)][獄門島]의 마지막 장 제목[^2]에서 따왔습니다. 때문에 흔히 이야기하는 번역투이기도 하고, 지나치게 수사적이고 때문에 비꼬는 느낌까지 들어 썩 좋기만한 제목은 아닙니다. 하지만 요코미조 세이시가 전후 일본 사회를 봉건성을 다양한 측면에서 해석하여 자신의 추리소설의 소재로 삼았던 것처럼, 우리가 흔히 "Web3적이다"라고 이야기 할때 Web3에 기대되는 것 또한 다양할 수 있겠다는 생각에 따오게 되었습니다.

[Web3]: https://ethereum.org/en/web3/
[横溝正史]: https://ja.wikipedia.org/wiki/%E6%A8%AA%E6%BA%9D%E6%AD%A3%E5%8F%B2
[獄門島]: https://ja.wikipedia.org/wiki/%E7%8D%84%E9%96%80%E5%B3%B6

[^1]: 이제는 "소년 탐정 김전일의 할아버지"로 더 유명한 긴다이치 시리즈의 작가입니다.
[^2]: 봉건적인, 너무나도 봉건적인(封建的な、あまりにも封建的な)

# 개념들

(이 단락의 내용은 [신뢰하지 않을 자유]라는 제 이전 글에서의 내용을 이미 읽으셨다고 가정하고 작성하였습니다. 혹시 그렇지 않으신 분이 계시다면, 먼저 그 글을 읽고 읽어주시길 권합니다.)

이전 글에서 밝혔듯, [이더리움][Ethereum] 지지자들은 본래 서비스의 "소유권(Ownership)"을 사용자들에게 돌려주는 것이야말로 종래의 웹과  Web3가 가장 크게 다른 점이라고 주장합니다. "Read-Write-Own" 이라는 [어떤 트윗][1]의 문구는 이러한 관점을 가장 잘 나타내는 것입니다. 그런데 여기에 대해서 좀 더 자세히 살펴보려면 주권(Sovereignty), 혹은 소유권(Ownership)를 어떻게 정의하는가가 중요하겠죠. [4가지 핵심 아이디어][2]를 다시 살펴보죠.

> - Web3 is **decentralized**: instead of large swathes of the internet controlled and owned by centralized entities, ownership gets distributed amongst its builders and users.
> - Web3 is **permissionless**: everyone has equal access to participate in Web3, and no one gets excluded.
> - Web3 has **native payments**: it uses cryptocurrency for spending and sending money online instead of relying on the outdated infrastructure of banks and payment processors.
> - Web3 is **trustless**: it operates using incentives and economic mechanisms instead of relying on trusted third-parties.

> - Web3는 **탈중앙화 되어있습니다**: 중앙화 되어 있는 주체에 의해 통제/소유되는 인터넷의 많은 영역 대신, 소유권은 빌드와 사용자들에게 분산되어 있습니다.
> - Web3는 **무허가형입니다**: 모든 사람은 Web3에 참여할 수 있는 동등한 액세스 권한을 가지며, 누구도 제외되지 않습니다.
> - Web3는 **자체 결제 수단을 갖습니다**: 은행이나 지불 처리자의 기타 뒤떨어진 인프라에 의존하는 대신, 온라인에서 소비하고, 송금하는데에는 암호 화폐(Cryptocurrency)를 사용합니다.
> - Web3는 **무신뢰형입니다**: 어떤 신뢰하는 제 3자에 의존하는 대신, 인센티브와 경제적 메커니즘을 사용하여 운영합니다.

무허가형이나 무신뢰를 얘기하는 것을 보면, [오픈 소스 소프트웨어(Open Source Software)][OSS]를 전제로 하는 사용자의 권리 보장을 떠올릴 법하고, 실제로 이 둘은 궁합이 꽤 좋습니다. 제 다른 이전 글인 [오픈소스, 블록체인 그리고 탈중앙 애플리케이션]에 이 관점에서의 주장이 남아있기도 하죠. 하지만 "오픈 소스"라는 특성이 Web3의 충분 조건일까요?


[신뢰하지 않을 자유]: https://gist.github.com/longfin/019e0067275d134f4302539d2ddbff06
[Ethereum]: https://ethereum.org
[1]: https://twitter.com/himgajria/status/1266415636789334016
[2]: https://ethereum.org/en/web3/#core-ideas
[OSS]: https://en.wikipedia.org/wiki/Open-source_software


## 네트워크의 소유권

오픈 소스 소프트웨어, 그리고 근간이 되는 자유 소프트웨어 운동이 벌어지던 시기의 소프트웨어는 단일 저작물로 완결된 경우가 많았습니다. 워드 프로세서, 웹브라우저, 그리고 싱글 플레이 게임 같은 것들 말이죠. 이런 소프트웨어들은 보통 단일한 소프트웨어의 소스 코드를 얻고, 거기에 대해서 개작할 수 있으면 그 소프트웨어의 모든 기능에 접근할 수 있죠. 그렇기에 소스 코드만으로 충분했습니다.

하지만 참여자들에 의해 가치가 형성되는 네트워크라면 얘기가 달라집니다. 네트워크를 통해 그 사용자에게 제공하는 가치가 단순히 그 네트워크를 구동하는 소스 코드만으론 얻을 수 없는 것이기 때문입니다. [^29] 이런 네트워크에서, 사용자들은 다른 사용자과 연결되어 서로의 상태에 대해 상호 작용하기에, 오픈 소스가 보장하는 소프트웨어 저작물의 소유권 뿐 아니라, 네트워크 자체에 대한 소유권이 따로 필요하게 됩니다. 그런데 네트워크를 "소유"한다는 것은 정확히 어떤 의미일까요?

힌트를 얻기 위해, 다시 오픈 소스 소프트웨어로 돌아가보죠. 오픈 소스 소프트웨어에서는 자유로이 사용할 수 있을 뿐 아니라, 복사하고 수정하여 (일정한 조건 하에) 재배포할 권리를 보장하죠. 이 중 사용에 대한 것은 비교적 간단합니다. 하지만 네트워크(정확히는 프로토콜)를 수정하게 되면, 수정한 사용자 외의 다른 사용자들도 영향을 받게 됩니다. 모두가 원하는 기능 추가라면 괜찮지만, 세상엔 그렇지 않은 일이 훨씬 많습니다. 하지만 그렇다고 수정을 못하는 네트워크를 내가 "소유"하고 있다고 말하는 것은 어폐가 있습니다. 일종의 중재, 즉 거버넌스(Governance)가 필요하다고 말하는 것도 바로 이 지점입니다.

* 이 문제에 대한 가장 단순한 방법은 [포크(Fork)][Fork]입니다. 하지만 네트워크의 가치는 프로토콜과 구현 외에도 참여자들에게서도 나오기 때문에, 온전한 재현을 위해선 추가적인 노력이 필요하며 포크가 거듭될 수록 줄어듭니다. [^3]
* 현실 세계에서의 많은 문제들처럼, 투표를 통해 이 문제를 해결하려고 하기도 합니다. 어떤 프로토콜에 변경이 있을 때 그것을 수용할지 말지 네트워크 참여자들이 투표를 통해 결정하자는 것이죠.
  * 뒤에서 다룰 인센티브에 대한 고민과 투표권을 결합하여, 많은 사람들이 이 방향을 지지합니다.
  * "투표를 통한 공약 이행 강제성을 얼마나 두어야 하는가"는 논쟁적인 부분이긴 합니다.
    * 어떤 사람들은 비허가형 네트워크에서 포크 가능성이 존재하는 이상 이런 이행 강제성이 큰 의미가 없다고 주장하지만, 네트워크의 가치에 의해 포크가 억제되기도 하기 때문에 괜찮다는 주장도 있습니다.
    * 하지만 현실적으로는 현재 많은 투표가 이더리움이나 오프 체인에서 아주 단순한 형태로만 진행되기 때문에, 자동화를 하기 어려운 것은 사실입니다.


[^3]: 이런 불리한 점이 있지만, [이전 주장][3]처럼 저는 비허가형 네트워크에는 여전히 포크를 감내하는 오픈 소스 개발 모델이 필요하다고 생각합니다. 하지만 반대로 허가형 네트워크라면 굳이 할 필요는 없기도 할 것입니다.
[^29]: https://gist.github.com/longfin/7d5e1a2e7c84642a45ea400bb891d88c#%EC%A0%9C%EC%9E%91%EA%B3%BC-%EC%9A%B4%EC%98%81


[Fork]: https://en.wikipedia.org/wiki/Fork_(blockchain)
[3]: https://gist.github.com/longfin/0951c39b566e58e4e0a80faf513bb4b1#%EC%9A%94%EC%95%BD


## 주권 (Sovereignty)

주권은 보통 국가의 권한이란 뜻으로 많이 쓰이지만, 탈중앙 네트워크에서는 그보다 "주요한 권리"라는 본래의 뜻으로 더 많이 쓰입니다. 그런데 "주요한 권리" 라는 것만으론, 무엇에 대한 권리인지 바로 알 기 어렵습니다. 그리고 저는 이 주권이 어떤 권한이나 대상을 정한 다음 따라온 개념이 아니라, 어떠한 행위에서 연상되어 후행적으로 사용되는 용어라고 생각합니니다. 바로 위에서 본 투표[^30]죠. 

주권이 위에서 살펴 본, 프로토콜 개정에 대한 투표권이라면 "소유권"과 비슷한 뜻일 것입니다. 하지만 어떤 프로젝트들은 이런 네트워크의 "소유권"을 선택적[^31]으로 부여하고 싶어하기에, 모든 투표가 프로토콜의 모든 부분에 적용할 수 있는 것은 아니기도 합니다.

[^30]: 투표라는게 현실 세계에서도 주로 정치에 관련된 의사 결정(i.e., 선거)에 많이 사용되다 보니 다들 자연스럽게 국가 권한인 "주권"이란 말을 쓰는 게 아닌가란 개인적인 추측이 있습니다.
[^31]: 이 시점에서 일반적인 Web3의 정의에는 딱 들어맞지 않습니다. Web3라는게 [GPL]처럼 딱히 전염성이 있는 라이선스는 아니니, "이러면 Web3가 아니다." 라고 하기에도 애매한 부분이겠지만요.

[오픈소스, 블록체인 그리고 탈중앙 애플리케이션]: https://gist.github.com/longfin/0951c39b566e58e4e0a80faf513bb4b1
[GPL]: https://www.gnu.org/licenses/gpl-3.0.html


# 소유의 종말 [^28]

2022년 1월, Signal의 창업자인 Moxie가 개제한 [Web3에 대한 내 첫인상("My first impressions of web3")][My first impressions of web3]라는 글이 엔지니어들 사이에서 큰 화제가 되었습니다. 이 글은 중앙화 된 종래의 웹서비스[^4]의 개발과 운영에 익숙한 저자가 자신의 Web3에 대한 의문과 회의감을 해결하기위해서, 직접 이더리움 네트워크에서 [ERC-721] 규격으로 [NFT]과 그 토큰이 쓰이는 [분산 애플리케이션(dApp)][dApp]을 만들어 배포한 경험을 옮긴 것입니다. 다양한 관점과 작업 과정을 다루고 있는 꽤 긴 내용이기 때문에, 전체 요약을 하는 것보다는 이 단락에서 함께 살펴봤으면 부분을 꼽아서 인용하는 것이 효과적일 것입니다.[^6] 

> We should accept the premise that people will not run their own servers by designing systems that can distribute trust without having to distribute infrastructure.

> 우리는, 사람들이 아무런 인프라 분산 없이도 신뢰를 배포할 수 있는 시스템을 설계해도 그들의 서버를 직접 운영하지 않을 것이란 전제를 받아들여야 합니다.

다른 주장들에 대해서 반론도 있긴 하지만[^7], 유독 이 통찰만은 저에게 꽤 무겁게 다가왔습니다. 왜냐면 반박하기 어려웠기 때문이죠. 게다가 당장 Moxie만의 주장도 아닌 것이, 이런 서비스 공급자/소비자를 나눴을 때 순수하게 사용성/시장성 측면에서 더 효과적이고 효율적인 부분들이 보통 더 많습니다. 많은 소프트웨어 회사들이 라이선스를 직접 판매하고 사용권[^8]을 통으로 넘겨주는 대신, 그나마도 구독형으로 전환하여 사용권을 제한합니다. 이건 공급자 관점에선 채산성이 높은 일이니 원하는 것이 당연할 뿐 아니라 소비자 입장에서도 당장 저렴한 비용으로, 그것도 사후 관리를 편하게 받을 수 있다는 점에서 매력적인 조건입니다. 이런 압도적 편리성을 포기하고 눈에 보이지 않는 소유권을 쟁취하라고만 호소하는 것은, 대상이 되는 시장이 극단적으로 줄어드는 결과가 될 겁니다.[^9]

이 현상을 독점성(Monopoly)이라는 개념을 두고 설명하려는 시도도 있습니다. 중앙화라는 현상은 중앙화된 주체에 의해 독점적으로 운영되기 때문이기에, 이 독점적 운영을 없애면 탈중앙화를 이룰 수 있다는 것입니다. 가령 이더리움에는 [Infura]와 같은 노드 공급자가 있지만, 네트워크 자체는 무허가형이므로 독점성이 없고, 그러니 이는 이더리움이 여전히 탈중앙화되어있다는 것이죠. 그리고 이건 꼭 노드 공급자에만 한정된 것이 아니라, 프로토콜에 맞춘 구현을 사용자들에게 제공하는 소프트웨어 엔지니어링 전반에 걸쳐 적용할 수 있다고도 이야기 됩니다.

하지만 설령 프로토콜 수준에서 독점성을 없애서, 노드 공급자들이 활동할 수 있게 있더라도 문제는 남아있습니다. 그것이 사용자들에게 연결할 노드를 고르게 할 수 있는 옵션은 될 지언정, 그들이 노드를 직접 운영하거나 프로토콜에 직접 기여 할 인센티브로는 이어지지 않으니까요. 이런 탈독점성은, 소유권이 있다는 것을 기계적으로 증명할 수 있는 명분은 되지만, 기존 중앙화된 시스템과의 비교 우위는 여전히 만들지 못합니다.

[^4]: 흔히 Web3 종사자나 지지자 분들은 이를 Web2라고 부르곤 합니다. 하지만 저는 개인적으론 이 표현에 동의하지 않기[^5]에 여기선 늘여서 적습니다.
[^5]: 저 개인이 사용하지 않는 것을 넘어 업계 사람들이 사용을 멈추는 게 좋겠다는 극단적(?)인 생각을 했던 적이 있는데, 여기에 대해선 Web3에 대한 생각을 정리하기 전까진 주장을 유보하고 있습니다.
[^6]: 물론 글 자체는 꽤 재밌기 때문에, 시간이 되신다면 읽어보시는 것을 추천합니다.
[^7]: 가령 저는, Web3에 암호화가 거의 관련되어 있다는 주장에는 동의하기 어렵긴 합니다.
[^8]: 소프트웨어 제품에 대해 소유권 자체를 이양하는 회사는 생각보다 그리 많지 않습니다.
[^9]: "게임이 대체 언제부터 탈중앙화에 관심 있었냐"라는 비판은 이런 맥락에서는 꽤나 시장을 잘 드러내고 있다고 생각합니다.
[^28]: 미래학자 [제러미 리프킨(Jeremy Rifkin)][Jeremy Rifkin]이 2000년 출간한 저서인 [The Age of Access]의 한국어 제목에서 따왔습니다. 자원과 서비스에 대한 소유 중심 사회에서, 필요할 때에만 접근 하는 접속 중심 사회로 발전할 것이라는 주장이 주요 내용입니다.

[My first impressions of web3]: https://moxie.org/2022/01/07/web3-first-impressions.html
[ERC-721]: https://ethereum.org/ko/developers/docs/standards/tokens/erc-721/
[NFT]: https://en.wikipedia.org/wiki/Non-fungible_token
[dApp]: https://en.wikipedia.org/wiki/Decentralized_application
[Infura]: https://infura.io
[Jeremy Rifkin]: https://en.wikipedia.org/wiki/Jeremy_Rifkin
[The Age of Access]: https://en.wikipedia.org/wiki/The_Age_of_Access


# 시장에서 태어난 인센티브

토큰, 그리고 인센티브란 것에 대해 유독 Web3 진영에서 많은 관심을 가지고, 또 고도화 된 것은 아마 이런 비교 우위를 만들기 위한 목적이 컸을 것입니다. 그간 다른 서비스들의 소유권에 대해서 크게 생각하지 않았던 사람들조차도, "이게 그동안 플랫폼 사업자들이 떼어가던, 여러분의 주권입니다."라며 토큰으로 인센티브를 제시할때 강력한 서사가 만들어집니다. 왜냐하면, "소유권" 이라는 것에 대해 사람들이 둔감했던 이유 중 하나가 보이지 않기 때문이기도 하거든요. 지난 수십년간 서비스 제공자들은 소유권을 가져가고 내야 할 돈을 가리는 일들을 생존을 위해 해왔고, 소비자들은 그것을 인지하였든 하지 못했든 거기에 대한 비용을 지불하고 있었습니다. [^10] 거기에 이런 인센티브는 [비트코인][Bitcoin]과 이더리움 모두 돈을 다루는 탈중앙 네트워크였기 때문에 구현에 특별히 부담이 더 드는 것도 아니었습니다.

그런데, 이런 인센티브의 도출 과정이 순수하게 논리적인 필요에서 시작된 것이 아니라, 중앙화 시스템과의 비교 우위를 형성하기 위해서 진행되었기에, Web3의 무신뢰성을 이야기할 때 말하는 인센티브와는 동음이의어가 되는 경우가 많습니다. 다음은 그 예입니다.

- 이더리움 네트워크의 수수료(Gas)는 무신뢰성(혹은 거기서 파생되는 비독점성)을 유지하기 위해서 필요합니다. 즉 검증인(Validator)[^11]들에게 다른 의도(그것이 선의건 악의건간에) 대신 순수히 경제적 동인을 보장하는 장치죠. 하지만 이는 트랜잭션을 만드는 사용자 입장에선, 중앙화 시스템과 비교 했을때 이득을 주기는 커녕 도리어 손해만 납니다.
- 2022년 5월, Terra 프로젝트에서 지분 증명(PoS)에 쓰이는 암호화폐인 LUNA의 가격이 폭락함에 따라, 블록 거버넌스에 대한 공격[^12]이 우려되기에 신규 검증인 추가를 막는 일이 발생합니다. 물론 이런 블록 거버넌스가 LUNA의 유일한 쓰임은 아니었으나[^13], 적어도 블록 거버넌스에 대해서는 대표성이 없어질 수 있다는 것이죠.

그렇지만 아직 모든 인센티브 구조가 그렇다고 증명된 것은 아닙니다. 그렇기에 사람들은 "토큰의 사용처"[^14]를 찾아야 한다고 주장하며 여러가지 시도를 해왔습니다. 그렇기에 토큰 경제(Token Economy)는 마케팅의 영역에서 기획되어, 탈중앙성/탈독점성은 일종의 비용으로 다뤄지는 경우도 잦습니다.

[^10]: 아주 일반론이지만 저는 이런 서비스 제공자들이 특별히 더 악하다고 보지도 않고, 반대로 더 보호 받아야 한다는 생각도 없습니다.
[^11]: The Merge 이전엔 채굴자(Miner)
[^12]: 당시엔 공격이란 표현이 적절치 않다는 생각도 들었지만 마땅히 더 좋은 표현이 없기도 하고, 대표성이 없다는 주장을 하면서 저게 공격이 아니라고 하는 것도 모순이라는 생각에 공격으로 표기합니다.
[^13]: 당시의 LUNA 폭락은 다른 요인으로 발생한 것이었고, 이 글의 주제와도 직접적인 연관은 없어 길게 적지 않습니다.
[^14]: 처음 들으면 퍽 이상한 얘기이지만, 이런 문맥을 고려하면 사람에 따라서 불편할 순 있어도, 그렇게 마냥 이상한 얘기는 아닙니다.

[Bitcoin]: https://bitcoin.org


# DAO, 그리고 커뮤니티

[탈중앙화된 자율 조직(DAO)][DAO]과 거버넌스 토큰을 오롯이 사용성 인센티브라는 관점에서만 다루는 것은 악의적일지도 모릅니다. 앞서 살펴 본 것처럼, "네트워크의 소유권"을 탈중앙화 하기 위해선 거버넌스가 필요했고, 그걸 잘 다룰 수 있는 것이 DAO이기도 하기 때문이죠. 하지만 사용성 인센티브라는 성격도 남아있기에, 많은 DAO는 사용자들에게 방해가 되는 프로토콜 인센티브, 즉 트랜잭션 수수료를 아끼기 위해 오프 체인 투표를 하거나, 온체인 투표를 하더라도 아주 복잡한 구현에 대해서 자동화 하는 것을 꺼리는 경향이 있습니다. [^15]

어찌되었거나 투표에 대한 책임, 그리고 그것을 준수하여 구현을 해야하는 역할은 커뮤니티에게 넘어갑니다. 거버넌스 토큰으로 사용성 인센티브를 충족하며 자동화 수준을 억제한, 위와 같은 DAO 모델에서 커뮤니티는 크게 3가지 성격을 지닙니다.

* 거버넌스 토큰을 초기 발행자로 부터 구매하여 네트워크의 소유권을 이양 받는 초기 고객
* 거버넌스 토큰을 통해 네트워크의 프로토콜을 개정하는 입법자
* 개정된 프로토콜을 구현하여 네트워크에 해당 구현체를 제공하는 빌더(Builder)

DAO의 자동화 수준이 높을 수록 빌더가 해야 할 일은 그리 많지 않을겁니다. 표결이 가결 되어 프로토콜이 가결되는 순간 자동으로 네트워크에 구현이 반영될테니까요. 하지만 우리가 다루고 있는 많은 DAO들이 그렇지 않기에, 우리는 커뮤니티에서 이런 "신뢰할 수 있는 빌더"를 가정[^16]해야 하는데, 이는 공급자/소비자 중 소비자로서의 위치가 익숙한 참여자상과 퍽 달라집니다. 때문에 초기 개발팀이 이 역할을 계속 맡는 경우도 종종 있고, 이 현상 자체가 DAO에 대한 비판의 대상이 되기도 합니다. 그리고 이런 특정 팀의 개발 독점성을 극복하기 위해 커뮤니티의 개발 역량을 늘리게끔 돕는 게 탈중앙화에 중요하다는 의견도 있죠. 그럼에도 불구하고 우리가 고려해야 할 점은, 이 빌더들과 입법자들이 네트워크에 다른 의도로 참여할 수 있다는 것이겠네요.

이를 보다 일반화해서 구성원 전체의 총의를 얼마나 잘 드러낼 수 있는지에 대해 진지하게 고민하는 사람들도 늘어 났습니다. 재밌는 것은 이런 투표 방법을 고도화 하는 과정에서, 거버넌스 토큰 등으로 교환 가능한 토큰을 사용하는 그다지 바람직하지 않다는 주장[^17]들도 있다는 점입니다. 이런 방향의 논의는 "네트워크의 소유권"을 잘 나누기 위해서 필요하지만, 사용성 인센티브로서의 거버넌스 토큰을 필요로 하는 이들에겐 고민이 되기도 하는 주제겠지요.

[^15]: 최근까지 저는 DAO에 대해 한 가지 큰 오해를 하고 있었습니다. 바로 "충분히 자율화되지 않은 것은, EVM과 타깃이 되는 dApp들의 낮은 복잡도를 따라갔기 때문이다."라는 것이죠. 이는 이유 중 하나가 될 순 있어도, 가장 큰 이유나 유일한 이유는 아닙니다. 현재 제가 생각하는 가장 큰 이유는, "참여자들이 그걸 원하지 않기 때문이다." 입니다. 그리고 이게 맞다면, 설령 복잡도 문제를 해결한 아주 빠른 분산 합의 기술이 나오더라도 사람들은 그걸로 자신의 제안을 직접 구현하기보다, 누군가를 믿고 제안에 투표하는 것을 택할 사람이 더 많을 것이고, 그런 사람들에게 잘 들어맞는 제품이 더 널리 쓰일 것입니다. [^18]
[^16]: 물론 이런 빌더들에게 적절한 인센티브를 주는 것으로 무신뢰성이 어느 정도 달성될 수도 있지만, 저는 여기서 신뢰를 아예 없애는 것은 불가능할 것이라고 봅니다. 만약 완전히 신뢰를 없앨 수 있을 만큼 빌더의 작업물을 평가해서 인센티브를 제공할 방법이 있다면, 그걸 자동화 하는 것도 가능할 것인데, 자동화를 포기하는 시점에서 그렇지 않게 보이기 때문입니다.
[^17]: 대표적으론 비탈릭 부테린의 [소울 바운드(Soul Bound)](https://vitalik.ca/general/2022/01/26/soulbound.html)가 있겠네요.
[^18]: 이전 글에서 [자동화된 행정]에 대한 낙관과 다른 비관적 전망이라 혼란스러우신 분도 계실 것 같습니다. 이는 뒤에 자세히 밝히겠지만, 이 글이 다른 글들에 비해 가지고 있는 큰 차이에 기인합니다.

[DAO]: https://en.wikipedia.org/wiki/Decentralized_autonomous_organization
[자동화된 행정]: https://gist.github.com/longfin/019e0067275d134f4302539d2ddbff06


# 막간) 인필드 플라이(Infield Fly)[^19]

이 글에서는 업계, 시장, 그리고 DAO에 걸쳐 저는 사용자의 상(Persona)를 다음과 같이 가정해왔습니다.

* 중앙화된 서비스만큼의 사용성을 요구하거나 그만큼을 다른 인센티브(사용성 인센티브)로 보전하길 원함
* 무신뢰성이나 소유권에 대한 인센티브(프로토콜 인센티브)에는 크게 관심 없거나 지출을 꺼림
* 프로토콜에 대해 의사 결정을 하는 것엔 어느 정도 적극적

세상사 모든 일이 다 그렇듯이, 이런 구도는 경향성을 어림 짐작하려 쓰이는 근사일 뿐이고 반드시 어느 한 쪽만을 취해야만 하는 것은 아닙니다. 대부분의 게이머들이 소유권에 관심이 없다 한들, "여러분의 아이템은 여러분이 가진 게 아닙니다."라고 로그인 화면에 적힌 게임을 보면서 불쾌하지 않을 사람은 없겠죠. 양자 택일의 문제가 아니라, 정도나 수준의 문제라고 볼 수도 있고, 아직 미처 사람들이 꺠닫지 않은 시장이나 확신의 크기에 대한 문제라고 볼 수도 있습니다.

하지만 이런 수준이나 정도에 대한 여러 아이디어를 더 편하게, 더 자주 이야기 하기 위해선, 역설적이게도 때로는 그 수준이나 정도를 포괄하는 큰 수준의 경계를 명확하게 정의하는게 보탬이 되는 경우가 많습니다. 제안하는 쪽에서 최소한의 점검을 해볼 수 있다던지, 검토하는 쪽과의 인식을 빠르게 맞출 수 있다던지 하니까요.

[^19]: [인필드 플라이(Infield Fly][Infield Fly]는 주자가 있을 때 내야 뜬공이 나오면 내야수가 그것을 잡건 잡지 못하건 타격 시점에 아웃 카운트가 올라가는 야구 규칙입니다. 아웃 카운트가 빠르게 올라간다는 점에서 수비를 위한 규칙 같지만, 고의 낙구를 이용한 병살타를 막는 효과가 있는, 즉 공격자를 보호하기 위한 규칙입니다.

[Infield Fly]: https://en.wikipedia.org/wiki/Infield_fly_rule


# 이제 와서 탈중앙화라 해도[^20]

어찌되었건간에, 그렇다고 마냥 부정할 수도 없는 이런 시장의 상을 가정해가며 겨우 도달한 DAO나 신뢰에 기반한 거버넌스에서, 다시 출발지인 Web3를 돌이켜보면 막막하고 먼 느낌이 드는 것은 어쩔 수 없습니다. 어쩌면 하나씩 내려두고 싶은 생각마저 듭니다. 무신뢰성과 오픈 소스를 내려두면, 아마 여러가지 염려가 사라지고 기성 기술과의 접점이 늘어날 겁니다. 상대적으로 사용자 수가 그렇게 많지 않은 자체 결제 수단[^21]보단 인 앱 결제(iAP)와 같은 것을 붙이는게 직접 매출엔 더 기여할 것입니다. 어쩌면 탈중앙화라는 건 이렇게 몇몇 엔지니어들만 근심과 걱정을 해가면서 달성해야 할 일이 아니라, 인간 본연의 창조성과 가능성에 주목해야 하는, 일종의 사회 운동과 같은 일일지도 모릅니다. 하지만 동시에, 사회 전체나 일반적인 조직 활동 전반에 걸친 탈중앙화에는 무신뢰성이나 블록체인 기술이 그리 많은 기여를 할 수 없다는 생각도 크게 바뀌진 않았습니다.

보다 쉽게 이해하기 위해 가상의 게임 회사[^22] [^23]들을 가정해보죠. 일종의 사고 실험이므로 이 게임 회사들은 모두 제시한 목표만을 지향하며, 다른 부가적인 이득(i.e., 단기 토큰 판매 수익)은 고려하지 않으며, 기망 행위도 하지 않는다고 가정합니다. 또한 모든 게임 회사는 각자 원하는 바를 충분히 만들 역량이 있다고도 가정합니다.

## 가정 1) 커뮤니티에게 보답하고 싶은 게임 회사 이야기

게이머 커뮤니티는 게임이 얼마나 탈중앙화 되었는가와는 무관하게 이전부터 쭉 있었습니다. 종래의 중앙화된 서비스로서의 게임은 이런 커뮤니티와의 관계가 공급자와 소비자이기에, 커뮤니티의 의견은 소위 ["고객의 소리(Voice of the customer, VoC)"][VoC]로서 취급됩니다.

하지만 게임이 가상 사회로서의 위치를 가지고 또 그 중 어떤 게임들이 대체 불가능한 위치가 되면서, 문제가 더 복잡해집니다. 아주 단순하게 보면 공급자는 소비자의 선택만을 고려해서 이익을 극대화 하길 원합니다. 그런데 의존성이 생기면서 게임사가 공급자로서 소비자를 수탈한다고까지 보이는 구도가 펼쳐진겁니다. [^24] [^25]

아무튼 이런 게임사의 공급자로서의 행태에 반감을 갖는 것은, 비단 게이머 뿐만은 아닙니다. 그래서 어떤 게임 제작사들은, 진정으로 커뮤니티와 함께 만들어가는 그런 게임을 만들고 싶다고 합니다. 구체적으로는 게임의 밸런스나 규칙, 그리고 사업 모델 (BM)까지도 커뮤니티에서 투표를 통해 결정하는 그런 게임을 만들고 싶다고 합니다.


## 가정 2) 오픈 소스가 하고 싶은 게임 회사 이야기

어떤 게임 팀은 지난 오랜 세월 동안 게임 구현을 독점적으로 공급하는 것에 환멸을 느끼기도 했습니다. MMORPG 같은, 거대한 메타포(e.g. 세계, 대륙)를 게임의 배경이나 요소로 차용하는 제작자들은 여기서 영감을 얻기도 하죠. 그래서 프로토콜과 핵심 구현을 오픈 소스로 공개하여 보다 많은 개발자들이 거기에 자유로이 기여할 수 있는 그런 게임을 꿈꿉니다. [^26]

오픈 소스 운동이 소프트웨어 저작물에 대한 사용자의 권리 보장에서 출발했다는 걸 생각해보면, 주권이란 주제와 Web3와는 잘 맞아보입니다. 앞서 언급했듯이 탈중앙성을 확보하는 가장 "떠올리기 쉬운" 방법은, 코드를 공개하고 포크를 장려하는 것일 테니까요.


## 아주 강경한 버전부터

아주 확실하고 강경한 버전은, 프로토콜 전체, 즉 네트워크의 소유권을 전부 탈중앙화 하는 것입니다. 이런 관점에서 첫 번째 회사를 다시 보면...

* 커뮤니티에서 투표를 언급하고 있는 점에서 DAO 형태로 운영될 것이란 가정이 가능합니다.
* 하지만 "주권"에 대한 단락에서 언급한 것처럼, DAO가 투표를 하는 것만으로 네트워크의 소유권이 탈중앙화 된 것은 아닙니다. 바꾸어 이야기하면 표결 내용들만 탈중앙화 되어 있다고 봐도 될 것입니다.
* DAO의 이행 관점에선, 코드가 공개 되어 있지 않다면 구현을 전적으로 개발사에 의존하게 됩니다.

두 번째 회사에 대해서도 생각해보죠.

* 오픈 소스로 코드를 공개할 의지가 있다는 점에서, 적어도 포크 가능성은 확보가 되었다고도 볼 수 있습니다.
* 하지만 동시에 시장 수용성을 고려하면서 프로토콜 개정에 포크를 바라지 않는 경우엔 DAO, 거버넌스 토큰을 사용할 수도 있습니다.
* 이행 관점에서 빌더 커뮤니티를 만들 순 있기 때문에 유리한 점이 있습니다.

이렇게만 보면, 네트워크 소유권의 탈중앙화엔 오픈 소스 여부가 큰 역할을 합니다. DAO를 한다고 해도 빌더 커뮤니티를 키울 수 있고, 또 DAO가 없더라도 최소한 포크는 가능하니까요. 하지만 이 포크 가능성은 역으로 전통적인 매출 구조와 잘 맞지 않는다는 치명적인 문제가 있습니다. 극히 일부의 예외를 제외하고는 중앙화된 일반적인 온라인 게임은 [사설 서버][Private server]에 대해서 적대적인데, 주된 이유는 매출이 감소하기 때문입니다. 바꾸어 이야기하면 이런 게임들의 BM은 포크에 취약하다고 볼 수 있기에 함께 고려되어야 합니다.

## Web3 리니지

탈중앙화라는 것에 정도가 있고[^33], 이를 조금씩 내려서 보는 시도를 한다고 생각해보죠. 아마 가장 적절한 지점은 DAO에서 표결을 붙이는 항목을 제한하는 것일 겁니다. 거버넌스 토큰도 필요할테니 사용자를 위한 인센티브도 확보되고, 또 전체를 한번에 하지 않아도 되니 부담도 덜합니다. 어쩌면 "어떤 걸 탈중앙화 하는 게 좋을까요?"라고, 이 항목 조차도 커뮤니티에 묻고 싶기도 합니다. [^34] [^35] [^36]

하지만 이건 진짜로 우리가 원하는 답이 아닙니다. 왜냐하면, 이 기준을 아주 극단적으로 적용하면..

> 한정된 접속권과 아이템에 대한 한정적인 사용권을 허가 해주는 종래의 게임들

이런 게임들도 DAO를 사용하기만 한다면 Web3 게임의 범주의 넣어야 합니다. "사용권", 혹은 "접속권" 을 원하는 만큼 주고 있고, 또 그 한도는 게임마다 다른 법이니까요. 또 이 기준을 아주 극단까지 밀어붙이면 의결 과정에서 DAO가 아예 필요치 않을 수 있는데, 이렇게 되면 거버넌스 토큰은 정말로 인센티브의 역할만 하게 됩니다.

즉 우리가 탈중앙화의 정도와 그에 대한 합의를 할 때에 진짜 관심을 두어야 할 것은, 어떻게 투표를 해야하는가 보다 "무엇을 탈중앙화 할 것인가."에 대한 것일 것입니다.


[^20]: [요네자와 호노부(米澤穂信)][米澤穂信]의 소설 [이제 와서 날개라 해도(いまさら翼といわれても)][いまさら翼といわれても]에서 따왔는데, 엄격한 가풍에 얾매이던 등장인물이 그런거 이제 신경쓰지 않고 살아도 된다는 얘기를 들어도 어쩔 줄 모르겠다고 토로하는 내용이 생각이 나 인용했습니다.
[^21]: 자체 결제수단은 암호 화폐를 이야기 합니다.
[^22]: 제가 최근 만나본 중앙화 애플리케이션을 하던, 그리고 탈중앙 애플리케이션에 관심이 있는 서비스 제공자들이 게임회사이기 때문입니다.
[^23]: 실제로 제가 만난 몇몇 팀들에서 모티브를 따오긴 했지만, 이 단락에서 주장하고 싶은 부분을 위해 과장하였습니다. 즉 실존하는 어떤 특정 팀의 이야기가 아닙니다.
[^24]: 소위 "꼬우면 접어라" ("꼬접")를 둘러싼 논란을 생각하시면 얼추 맞습니다.
[^25]: 물론 여기에는 단순히 공급자의 지위를 활용한 것을 넘어서 일종의 소비자 기만행위가 있는 경우가 있지만 주요 주제가 아니니 길게 다루진 않겠습니다.
[^26]: 눈치 채신 분도 많으시겠지만, 이건 "나인 크로니클" 이야기이기도 합니다.
[^33]: 주로 비트코인 지지자들은 이런 의견에 자체에 반대하지만, 글의 전개상 여기서 길게 다루진 않습니다.
[^34]: 뒤의 주장에 동의하시더라도, 이 탈중앙화 정의의 탈중앙화(?)에 매력을 느끼시는 분도 있으리시라 생각합니다.
[^35]: 하지만 저는 프로젝트를 제안하는 쪽에서 거버넌스 토큰을 무상으로 제공한다면 모를까, 판매를 하는 입장에서 그 효용에 대해서 먼저 생각하지 않는 것은 책임감이 없는 거라고 생각합니다.
[^36]: 한편으론 이런 거버넌스 토큰의 쓰임에 대해서 커뮤니티가 잘 정하지 못할 것 같다는 불안이나 회의도 있습니다. 투표 방식에 대해서도 이런 저런 연구가 나오는 걸요.

[米澤穂信]: https://ja.wikipedia.org/wiki/%E7%B1%B3%E6%BE%A4%E7%A9%82%E4%BF%A1
[いまさら翼といわれても]: https://ja.wikipedia.org/wiki/%E3%81%84%E3%81%BE%E3%81%95%E3%82%89%E7%BF%BC%E3%81%A8%E3%81%84%E3%82%8F%E3%82%8C%E3%81%A6%E3%82%82
[VoC]: https://en.wikipedia.org/wiki/Voice_of_the_customer
[Private server]: https://en.wikipedia.org/wiki/Private_server


# 커뮤니티 주도는 답이 아니라, 물음의 연장선

Web3의 DAO 혹은 포크를 통한 소유권의 탈중앙화는 대부분 커뮤니티를 가정합니다. 단일 사용자 대상의 소프트웨어가 아니라 네트워크를 다루기에 이는 당연한 것 같지만, 이런 네트워크의 커뮤니티는 네트워크보다 먼저 만들어지는 경우도 있습니다. 때문에 이런 경우엔, 단순히 참여자의 집합을 일컫는 게 아니라 특정한 목적을 가지고 모인 공동체로 이해하는 것이 타당하겠죠. 그래서 어떤 사람들은 아예 이런 커뮤니티를 먼저 만들어 자금을 조달하고, 네트워크의 프로토콜과 구현을 만든 다음 런칭하는 일련의 흐름을 커뮤니티 주도(Community Driven)이라고 명명하고 제안합니다.

아직 만들어지지 않은 제품에 대한 일종의 사전 판매라는 측면에서 [크라우드 펀딩(Crowdfunding)][Crowdfunding]과도 흡사하지만, 이 제작 모델에선 판매하는 내용이 네트워크의 소유권(혹은 주권)이라는 점이 주된 차이[^37]입니다. 그런데 이 "네트워크이 소유권"이 바로 우리가 방금 전까지 찾던, 그 주제입니다. 즉 이건 어떤 답이 아닌 물음의 연장선입니다. 우리가 단순한 크라우드 펀딩의 아종을 기대하는 것이 아닐 것이니까요.

[^37]: 때문에 탈중앙성을 보장하는 내용이 적으면 적을 수록, 가상 자산을 통한 지급 결제가 필요한 이유도 같이 줄어듭니다.

[Crowdfunding]: https://en.wikipedia.org/wiki/Crowdfunding


# 선택하지 않은 길 [^38]

중간에 잠깐 언급하긴 했지만, 지금까지의 내용을 읽으시며 이런 위화감이 드시는 분도 계실 것입니다.

> 이전 글들에 비해서 기술의 역할/비중보다 다른 걸 강조하는 것 같다.

서론에 밝혔듯이 이 글은 제 맥락에서 쓰여지지만, 결국 다른 견해들을 이해해나가는 과정이기도 했습니다. 그리고 여기에는 그동안 언급을 미뤄둔 어떤 요인을 추가했는데 그것이 바로 "시장"입니다. 그리고 이런 "시장"에서 탈중앙 애플리케이션들은 다음 2가지 측면에서 심각한 도전에 직면합니다.

* "소유의 종말"에서 밝힌 것처럼, 애플리케이션이 달성하려는 쓰임만 놓고보면, 많은 경우에 사람들은 "소유"에 그리 민감하지 않습니다. 비싸기도 하고, 이미 중앙화된 서비스들에서도 충분히 잘 나눠서 주고 있기 때문에 필요를 크게 느끼지 못하죠.
* DAO건 포크 가능성이건, 우리는 빌더 커뮤니티를 필요로 하지만, 이들이 "시장" 전체에서 그리 큰 비중을 차지하지 않습니다.

결국 우린 그저 또 다른 버전의 Facebook이나, 트위터를 만들고 있는 것뿐[^39]일까요? 여기서부터는 주로 제 생각의 지분을 높여서 적어보겠습니다.

## 희망의 부정

이 글을 적으면서 나름대로 여러 의견을 듣고 싶은 것도 있고 그리고 만들고 있는 [나인 크로니클]의 여러 현안[^40]들도 있었기에, 여러 사람들과 탈중앙성에 대해서 이야기를 했습니다. 그리고 그 과정에서 어떤 종류의 인정하지 않을 수 밖에 없지만 뭔가 꺼림찍한, 그런 가정을 하나 접하게 됩니다.

> 참여자들의 선의의 합은 언젠가 공동체의 공공선에 도달한다.

우리 모두가 알고 있듯이, 당장의 현실은 그렇지 않습니다. 애초에 저 "공공선"이라고 말하는 것의 정의가 모호하고 불가능하다고까지 보는 사람들이 있는 것이고, 저 언젠가에 대한 전망도 모호합니다. 우리는 아직 "선의의 합"을 이끌어내는 방법[^42] 역시 모르고요. 때문에 다음과 같은 생각할 점들이 생깁니다.

- 원칙적으로는, "선의의 합"은 "공공선"을 완전히 포함해야 합니다. "공공선"에서 "선의의 합"으로 설명이 안되는 부분이 생기면, 그건 다른 어떤 의도나 권한을 암시하는 거니까요. 
  - 근데 보통 어떤 사항을 온전히 이룩하는 것은, 단순히 "선의의 합"만으로는 달성하기 어려운 경우가 많아 이런 공백은 아주 발생하기 쉽습니다.
  - 때문에 여기서 "위임"[^44]이란 개념을 드는데, 이 "위임" 과정에서 우리가 그동안 수익이나 가치의 원천으로 여기며 배제해왔던 중간자들이나 신뢰 비용도 다시 등장합니다.
  - 이런 신뢰 관계 자체가 부적절하며, 이 시점에서 배제해야 한다는 차원의 이야기는 아닙니다. 다만 탈피하고자 하는 기존 체제와 다를 것이 없어진다는 점은 생각할 지점입니다.
- 어떤 분들은 "공공선"이란 것이 너무나 추상적이기에 판단을 보류하고 "선의의 합"과 분리하여 생각하기도 합니다. (i.e., 저흰 결정 자체엔 책임이 없으며, 이 또한 커뮤니티의 뜻입니다.)
  - 가치가 있다고 믿는 사람들이 있다면, 설령 우리가 그걸 믿건 안믿건 거기에 가치는 있는 거라는 생각에는 동의합니다.
  - 하지만 "공공선"을 이룩할 것이라는 믿음이 없는 상태에서 "선의의 합"을 정교하게 만드는 것이 가능할지에는 다소 회의적입니다.
- 보통 저 주장은 공동체의 안녕이 위협받는 것이 자명한 순간에는 강하게 재기(i.e., 일단은 살고 봐야지)[^41]되어 선명해지고, 그로 인해 필요 이상으로 더 많은 권한을 얻기도 합니다. 
- 한편으로 그렇지 않은 대다수의 경우엔 되려 모호해지는데, 그 모호함에서 권한이 싹트게 됩니다.

사실 사이퍼펑크들이 이야기 하는 개인의 권리 보장이나, 무신뢰성이 비독점과 탈중앙에 기여한다는 논리는 저걸 부정하는데에서 시작하기도 합니다. 그런 시각에선 "공공선"이라는게 애초에 없거나, 혹은 이바지 할 수 없는 경우가 분명히 생기는데, 그럴 땐 내 소유이 더 중요하다는 거죠.[^46] 그리고 이게 더 가치있다고 주장하는 사람들은, 어떤 상황에 처한 사람들에겐 그런 소유권을 보호하는 것이야말로, (설령 "시장"이 그걸 원하지 않는다 하더라도) 오히려 더 큰 기회를 낳는 토대라고도 이야기 합니다. 하지만 이 역시 아래와 같은 한계가 드러납니다.

- "선의의 합"을 모으는 방법이 어려운 것만큼이나 (혹은 그 이상으로), 무신뢰성과 비허가성을 양립시키는 네트워크의 개발이 어렵고, (현재로선) 쓰임이 한정적입니다. [^48]
- "시장"의 참여자들은 이런 무신뢰/비허가성을 중시하는 네트워크에 비해, "공공선"을 가정하는 네트워크에 친화적인 것처럼 보입니다.
- 무허가/비허가성을 갖춘 네트워크는 모호한 권한을 견제하는 데에는 효과적일 수 있으나, 죽음을 담보해야하는 경우를 넘기기 어렵습니다. [^43]

결국 저는 이 글을 적는 22년 10월 현재까지 여기에 대해 100% (결국 옳은지 그른지 판단할 자신은 없기에) 마음에 드는 이치는 아직 찾지 못했습니다. [^45]


## 바라트 성계 자치령 [^47]

여기에 있어서 대답하기 쉬운 것중 하나는 둘다 하기겠죠. 한 쪽은 한계가 명확히 보이지만 안전하고, 다른 한 쪽은 한계를 뛰어넘을 수 있을 듯 하지만 너무나 불안하니까요. 구체적으로 이야기하자면, "선의의 합" -> "공공선" 을 믿으면서 이런 저런 걸 하되 여기에 대한 부정을 전제로 한 파괴적 혁신에도 배팅하자. 이런 얘기일 것입니다. 

(TBD)




[^38]: [해리 터틀도브(Harry Turtledove)][Harry Turtledove]의 SF소설 [The Road Not Taken]의 정식 한국어판 제목에서 따왔습니다. (반전이 있는 소설이라 내용을 자세히 소개드릴 순 없지만) 작은 차이로 인해 크게 달라진 외계 종족간의 처지가 침략 전쟁을 통해 드러난다는 내용으로, 제가 엔지니어로서 Web3를 바라보는 희망(혹은 절망)과 비슷한 부분이 있습니다.
[^39]: 어떤 분들은 이런 비관적인 견해에 대해, 위의 커뮤니티 주도형 담론과 결합하여 "탈중앙성 자체에 장점이 없다한들, 프로젝트의 모금에 기여하여 빠른 부트스트래핑을 돕는다."라는 주장을 하시기도 하는데, 저는 여기에 대해선 사업으로서 성립하나 이 글의 본질적인 물음의 답은 아니라고 생각합니다.
[^40]: 여기에 대해서도 다른 글에서 자세히 소개하려 합니다.
[^41]: 현실 정치에서 군부 독재 쿠데타들이 일어나는 양상을 보면 얼추 비슷하지 않나 싶습니다.
[^42]: DAO의 입법 활동등에 관심이 많으신 분들의 궁극적인 목표 같은 거라고 생각합니다.
[^43]: 이걸 이룩했다고 일컬어지는 비트코인에 대한 평가도 따지고보면 사후적인 평가니까요.
[^44]: 위임자와 위탁자의 관계나 구도를 드러내는 것은 아닙니다. 기업에서 관리자가 실무자에게 업무를 지시하는 것도 일종의 "위임"이기 때문이죠.
[^45]: 역설적이게도, 이것 때문에 저는 DAO 구현 자체엔 꽤 적극적입니다.
[^46]: 이는 어찌보면 위에서 이야기한 "소프트웨어의 소유권"과 "네트워크의 소유권"은 다르다. 와 모순되는 주장처럼 보입니다. 하지만 "네트워크의 소유권"이 "네트워크의 기능"에 기인하고, 그 기능이 어떤 이유로 망가졌다면, 오히려 "소프트웨어의 소유권"이 더 중요해지는 상황도 발생할 순 있습니다.
[^47]: [다나카 요시키(田中芳樹)][田中芳樹]의 소설 [은하영웅전설(銀河英雄伝説)][銀河英雄伝説]에 나오는 세력 이름입니다. 후반부 전개와 관련된 내용이라 내용을 자세히 소개할 순 없지만, "제국주의 내에서 민주주의의 보루"라는 상징성이 있다는 것 정도만 언급하고 싶습니다.
[^48]: 여기서 쓰임을 한정하더라도 무신뢰성/무허가성을 유지하고 싶은 것이 비트코인 지지자들이라면, 쓰임을 넓히되 무신뢰성/무허가성에 대한 전제를 수정하길 원하는 것이 DAO에 친화적인 Web3 지지자들일 것입니다.

[Harry Turtledove]: https://en.wikipedia.org/wiki/Harry_Turtledove
[The Road Not Taken]: https://en.wikipedia.org/wiki/The_Road_Not_Taken_(short_story)
[田中芳樹]: https://ja.wikipedia.org/wiki/%E7%94%B0%E4%B8%AD%E8%8A%B3%E6%A8%B9
[銀河英雄伝説]: https://ja.wikipedia.org/wiki/%E9%8A%80%E6%B2%B3%E8%8B%B1%E9%9B%84%E4%BC%9D%E8%AA%AC


# 결론

* Web3는 네트워크 소유권에 관한 문제 의식에서 출발했습니다.
  * 네트워크 소유권은 구현의 소유권을 보장하는 것 이상의 개념입니다.
* 대중성 있는 Web3를 위해 사람들은 이런 소유권으로만으로는 부족하며 다른 인센티브가 필요하다고 판단했습니다.
  * 이를 위해 설계된 토큰 경제상의 인센티브는 프로토콜의 무신뢰성을 유지하기 위한 인센티브와 다를 때도 있습니다.
* DAO와 거버넌스 토큰은 네트워크 소유권에 대한 문제 의식과 사용성 인센티브를 동시에 만족시키기 위해 사용됩니다.
* DAO의 존재만으로 탈중앙성이 반드시 증명되는 것은 아니기에, 어떤 부분을 탈중앙화 하느냐에 대한 정의는 여전히 중요합니다.
* 커뮤니티 주도는 네트워크 소유권에 대한 사전 판매이기에, 어떤 부분을 탈중앙화 하느냐에 대한 직접적인 답이 아니며, 여전히 같은 의문을 공유합니다.
* "선의의 합"과 "공공선"에 대한 인식 차이는 탈중앙성에 대한 각기 다른 특성으로 이어집니다.
