# Spring Security, JWT 개념 

## Spring Security
스프링 시큐리티는 스프링 기반 어플리케이션의 보안(인증과 인가)을 담당하는 스프링 하위 프레임 워크이다.

- 보안과 관련해서 많은 옵션들을 제공해준다. ( 보안 관련 로직을 작성하지 않아도된다 )

스프링 시큐리티는 많은 기능을 편리하게 적용할수 있게 하지만 사용법입 쉽지 않다.

## JWT
JWT ( JSON Web Token )은 사용자의 정보를 담아 이를 암호화한 JSON 객체이다.

기존의 쿠키와 세션은 각각 보안 취약점과 stateless 위반의 문제가 있었지만 JWT는 이를 해역하기 위해 등장했다.

-> JWT는 암호화 알고리즘을 통해 디지털로 서명하기 때문에 인증되었고, 신뢰할 수 있는 토큰이다.(JWT는 공개키 암호방식(PKC) 즉 비대칭키 방식이다.)

# JWT 구조
JWT는 Header, Payload, Signature 3가지 부분으로 구성된다.
- <b>Header</b> / Header은 두가지 정보를 담고 있다.<br>
(서명에 사용할 암호화 알고리즘 관련 정보 , 토큰의 유형)

- <b>Payload</b> / Payload는 Claims라는 정보들을 가지고 있다.(Claims은 사용자와 같은 엔티티들이나 추가 정보들의 상태를 뜻한다.Registered, Public, Private가 있다.)
    - Registered / 미리 정의된 클레임 세트. JWT 발급자,토큰 제목,토큰 만료 시간,토큰 활성 날짜 등 다양한 정보가 포합됨

    - Public / 사용자가 정의할 수 있는 클레임이다. 사용자가 직접 정의하기 때문에 이 클레임에서 충돌이 발생할 수도 있다.(Public 클레임의 이름은 보통 URI로 정의해야함)

    - Private / 사용자가 정의할수 있는 클레임. 통신 당사자 간의 정보를 공유하기 위해 만든어진 클레임(사용자가 특정할 수 있는 정보를 담음) 

- <b>Signature</b> / Signature는 토큰에 포합된 정보들이 통신 과정에서 변경되지 않았다는 것을 검증하는 부분

### JWT 예시
```
eyJhbGci0iJIUzI1NiIsInR5cCI6IkpXVCJ9. -> Header

eyJzdWIi0iIxMjM0NTY30DkwIiwibmFtZSI6IkpvaG4
gRG91IiwiaXNTb2NpYWwiOnRydWV9. -> Payload
 
4pcPyMD09o1PSyXnrXCjTwXyr4BsezdI1AVTmud2fU4 -> Signature
```

### JWT 발급과 인증 과정
1. JWT는 클라이언트가 인증 요청(로그인 시도)을 하면 서버가 가지고 있는 secret Key를 통해 Token을 발급한다.

2. 클라이언트는 서버로부터 받은 토큰을 쿠키나 저장소에 저장하고

3. 서버에 요청을 보낼 때부터 저장해둔 토큰을 같이 전달합니다.

    - 서버는 클라이언트로 전달받은 토큰을 검증(복호화)하고 만약 토큰이 변조되지 않았다는게 검증되면 클라이언트의 요청을 수행한다.
    
    - 서버는 `Refresh Token`과 `Access Token` 두가지를 보내는데 Access Token은 요청에 대한 다양한 정보를 담고 실질적 인증 역할을 하며, Refresh Token은 Access Token의 만료 기간을 조정하는 역할을 합니다.

    