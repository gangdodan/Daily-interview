- 쿼리 return 타입을 settlement로 변경한 후 projections.constructor 로 조회하니 레포에 저장하지 않았는데도 데이터 저장되는 이슈 ***→ constructor 동작 확인해봐 무조건 객체 생성인지***
    - projections.bean으로 하면 생성자 필드에 id 값 없어서 The given id must not be null 에러 발생 → auto increments 값은 어케해
        - 아님!!!!!!아예 객체필드가 null
        - setter(bean)를 통해 데이터를 인젝션 해주며 **기본 생성자가 무조건 필요하다는데 noargument 있는데 왜 안되지?**
        - projections.fields 는 setter 없어도 된다니까 `as()`를 이용해 매핑할 필드 이름을 맞춰주자
    - 저장은 안되는데 왜 조회 후에 insert 쿼리 나가고 state null이라면서 쿼리 실패하는거지?
        
        ```sql
        insert
        into
        settlement
        (created_at, last_modified_at, amount, host, meeting_id, payment_id, reservation_id, state)
        values
        (?, ?, ?, ?, ?, ?, ?, ?)
        ```
        
    - 일단 if문 false라 foreach 안타고 saveAll() 로 가는듯
    - 아싸리 예외 처리로 잡아줌 ***→ 이래서 적절한 예외 처리가 필요하구나~ 다시 한 번 느낌***
