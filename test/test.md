# 마크다운 테스트
# Title
***
## 대주제
text
**boldtext**

### 소주제
text
**boldtext**
>들여쓰기
  >들여쓰기2
    >들여쓰기3

#### 이미지첨부
<p align="center">
  <img src="https://camo.githubusercontent.com/3073829860a866037e0ca12f244a9eb5462e4cfa/687474703a2f2f696d6167652e6b796f626f626f6f6b2e636f2e6b722f696d616765732f626f6f6b2f786c617267652f3333302f78393738383936303737373333302e6a7067">
</p>
#### 코드
```java
@SpringBootTest
@TestConstructor(autowireMode = TestConstructor.AutowireMode.ALL)
@Transactional
class JpqlTest(
    private val em: EntityManager,
    private val teamRepository: TeamRepository
) {

    @Test
    fun `JPQL 조회 테스트`() {
        //given
        val teamA = Team(name = "teamA")
        em.persist(teamA) // teamA 저장

        // insert into member (id, age, team_id, username) values (null, ?, ?, ?)
        val member1 = Member(username = "member1", age = 10, team = teamA) // member1에 teamA 연결해서 저장
        // insert into member (id, age, team_id, username) values (null, ?, ?, ?)
        val member2 = Member(username = "member2", age = 20, team = teamA) // member2에 teamA 연결해서 저장
        em.persist(member1)
        em.persist(member2)

        //when
        // select team0_.id as id1_1_0_, members1_.id as id1_0_1_, team0_.name as name2_1_0_, members1_.age as age2_0_1_, members1_.team_id as team_id4_0_1_, members1_.username as username3_0_1_, members1_.team_id as team_id4_0_0__, members1_.id as id1_0_0__ from team team0_ inner join member members1_ on team0_.id=members1_.team_id where team0_.name=?
        val team = teamRepository.findFetchJoinBy("teamA")

        //then
        then(team.members).hasSize(2)
    }
}
```
