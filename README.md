### 🙋‍♂️ 안녕하세요, 장현준입니다.

> **"사용자의 관점에서 고민하고, 팀과 함께 도전하며 성장하는 백엔드 개발자입니다."**
> <br/>단순히 기능이 동작하는 것을 넘어, 유지보수성과 확장성을 고려한 견고한 설계를 지향합니다.
> <br/>문제 발생 시 근본적인 원인을 집요하게 파고들어 해결하며, 그 과정을 팀과 공유하여 함께 성장하는 것을 즐깁니다.

### 🛠️ Tech Stack

**Backend**
<br/>
<img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" /> <img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" /> <img src="https://img.shields.io/badge/Spring Data JPA-6DB33F?style=flat-square&logo=spring&logoColor=white" /> <img src="https://img.shields.io/badge/QueryDSL-0078D4?style=flat-square&logo=microsoft&logoColor=white" />

**Database**
<br/>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" /> <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" /> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" /> <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" />

**Infra & Monitoring**
<br/>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white" /> <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" /> <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" /> <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" />

<br/>

### 🚀 Projects

<details>
  <summary><strong>📚 THIP: 기록 중심 독서 공유 플랫폼</strong> (2024.12 ~ 진행 중)</summary>
  <div markdown="1">
  <br/>

  **한이음 공모전(과학기술정보통신부 주최) 장려상 / KUIT 데모데이 최우수상**
  <br/>책을 읽으며 남긴 기록을 공유하고 소통하는 SNS 서비스입니다.
  <br/>👉 [GitHub Repository](https://github.com/THIP-TextHip/THIP-Server) | [Service Link](https://thip.co.kr/) | [App Link](https://play.google.com/store/apps/details?id=com.texthip.thip&hl=ko)

  - **Role**: Backend Developer
  - **Environment**: Java 17, Spring Boot, MySQL, Redis, Flyway, AWS(EC2/RDS), Docker
  - **Key Engineering Achievements**:
    
    **1. 헥사고날 아키텍처(Hexagonal Architecture) 도입** [헥사고날 아키텍처 도입기: 레이어드 아키텍처에서 헥사고날 아키텍처로.. ](https://animated-starfish-f32.notion.site/2d9536eb0a08802bb856d181c893ccd9?source=copy_link)
    - **문제**: 기존 Layered Architecture의 계층 간 강결합으로 인해 도메인 로직이 분산되고 테스트 작성이 어려움.
    - **해결**: 도메인(POJO)과 인프라(JPA)를 철저히 분리. Port/Adapter 패턴을 적용하여 외부 의존성을 역전시킴.
    - **성과**: 비즈니스 로직의 순수성을 확보하여 단위 테스트 커버리지 증대 및 유지보수성 향상.

    **2. 동시성 제어 및 데드락(Deadlock) 해결** [팔로잉 API 동시성 이슈 문제 확인 및 원인 정리](https://animated-starfish-f32.notion.site/API-2da536eb0a088011bec4e2f24eb5b5ad?source=copy_link)
    - **이슈**: 팔로우/언팔로우 동시 요청 시 FK 검증(S-Lock)과 Update(X-Lock) 충돌로 인한 데드락 발생.
    - **해결**: 트랜잭션 분석 후 낙관적 락 대신 비관적 락(Pessimistic Lock, `SELECT FOR UPDATE`)을 적용하여 경합 자체를 제어.
    - **성과**: 부하 테스트 시 데드락 0건, 응답 속도 50% 개선.

    **3. 대용량 조회 성능 최적화 & 캐싱 전략** 
    - **Redis**: Sorted Set(ZSet)을 활용해 실시간 랭킹 집계 로직을 개선하고, **Look-aside & Two-Phase(ID 조회 → 상세 캐싱)** 전략으로 Cache Miss 비용 최소화.
    - **Query Optimization**: 300만 건 더미 데이터 환경에서 복합 인덱스 설계 및 커버링 인덱스 활용으로 정렬 조회 속도 **7s → 0.23s (약 29배)** 단축. 
    - **Pagination**: Offset 방식에서 **Cursor 기반 페이지네이션**으로 전환하여 후반부 조회 성능 40% 개선.
    - **관련 정리 글**: [기록장 조회 성능 문제 인식](https://animated-starfish-f32.notion.site/2ee536eb0a08805abc64ea027e17f586?source=copy_link), [JPA 상속 전략에 의한 복잡한 쿼리 개선](https://animated-starfish-f32.notion.site/JPA-2e1536eb0a08800d8fc1c1116b0beaf4?source=copy_link), [기록장 조회 성능 개선을 위한 쿼리 튜닝](https://animated-starfish-f32.notion.site/2ee536eb0a08805fbad5f7f7f21cab1f?source=copy_link)
  </div>
</details>

<details>
  <summary><strong>🚚 Chacall: 푸드트럭 중개 및 매칭 플랫폼</strong> (2025.07 ~ 진행 중)</summary>
  <div markdown="1">
  <br/>

  **건국대학교 드림학기제 최우수상 (총장상)**
  <br/>푸드트럭 사장님과 축제 기획자를 연결하는 B2B 매칭 서비스입니다.
  <br/>👉 [GitHub Repository](https://github.com/CHA-CALL/ChaCall-Server)

  - **Role**: Backend Developer
  - **Environment**: Spring Boot, PostgreSQL, MongoDB, WebSocket, AWS S3
  - **Key Engineering Achievements**:

    **1. Facade 패턴을 통한 복잡도 관리**
    - **문제**: 컨트롤러에 검증/조합 로직이 혼재되어 비대해짐(Fat Controller).
    - **해결**: **Facade Layer**를 도입하여 진입점을 통일하고, 하위 도메인 서비스(Info/Menu/Image)를 조립하는 형태로 리팩토링.
    
    **2. 보안과 성능을 고려한 파일 업로드**
    - **해결**: **AWS S3 Presigned URL**을 적용하여 클라이언트가 직접 업로드하도록 변경(서버 부하 감소). CloudFront(CDN)를 통해 S3 직접 접근을 차단하고 보안 강화.
    
    **3. 실시간 채팅 시스템 구축**
    - **구현**: WebSocket(STOMP) + MongoDB 조합으로 실시간 채팅 구현. 채팅 메타데이터(Unread Count 등)를 NoSQL로 분리하여 RDB 부하 분산.
  
  </div>
</details>

<br/>

### 💼 Experience

**건국대학교 학생회 ITZI 개발국원** (2024.02 ~ 2024.12)
- 신입생 성격 유형 검사 및 학생회비 납부 프로그램 개발

**KUIT (건국대학교 개발 동아리) Server 파트원 & 파트장** (2024.08 ~ 2025.08)
- **코드 리뷰**: PR 기반의 상세한 코드 리뷰 문화를 정착시켜 팀의 기술적 성장 견인.
- **리더십**: 서버 파트 세션 기획 및 운영 총괄, 해커톤/데모데이 심사.
- **멘토링**: "객체지향과 테스트 코드", "리팩토링 실전" 세션을 진행하며 파트원들의 코드 퀄리티 향상 주도.

**삼성 청년 SW 아카데미 (SSAFY) 15기** (2026.01 ~ 진행 중)
- Java/Spring 기반 백엔드 교육 과정 수료 중
