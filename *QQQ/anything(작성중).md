## 질문과 고민 모음
1. Spring Data JPA 에서 Entity에 기본 생성자가 필요한 이유는 동적으로 객체 생성 시 Reflection API 를 활용
2. embedded in embedded -> elmentcollection
  - emebeded에 elementCollection 맵핑해도 되는가?
  - I believe `@ElementCollection`
  - is mainly for mapping non-entities (embeddable or basic) while `@OneToMany`
  - is used to map entities. So which one to use depend on what you want to achieve.

3. Jpa 레포에 엔티티 지정 상관없이 다른 테이블 조회해도 문제 없나?
