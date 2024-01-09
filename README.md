# EscapeFromNaeBaeCam_Code
### 내배캠 프로젝트 당시에 작성한 코드 모음

**Controller**
- AnimationController -> 애니메이션 파라미터를 hash값으로 미리 변환하여 이벤트에 등록하는 역할을 합니다.
- CharacterController -> 캐릭터의 공격, 스킬 딜레이를 관리하고 이벤트의 실행을 담당하는 역할을 합니다.
- PlayerInputController -> InputSystem 으로 입력값을 받아 값에 맞는 행동을 실행시키는 역할을 합니다.
- MeleeAttackController -> 근접 공격 기능 역할을 합니다. OverlapBoxAll 로 충돌체를 체크하여 공격하는 방식으로 구현했습니다.
- MeleeSkillController -> 근접 스킬을 관리하는 역할을 합니다. 스킬 데이터를 받아 스킬을 코루틴으로 실행합니다.
- RangedAttackCotroller -> 원거리 공격을 관리하는 역할을 합니다. 스크립터블 오브젝트 데이터에 따라 지속시간 동안 날아가거나 데미지를 주는 역할을 합니다.
- RangedSkillCotroller -> 원거리 스킬 공격을 관리하는 역할을 합니다. 

**Entities**
- AimRotation -> 캐릭터의 회전과 무기의 회전을 담당합니다.
- CharacterStats -> 플레이어와 몬스터 스탯의 공통점을 묶은 스크립트입니다.
- CharacterStatsHandler -> 캐릭터의 스탯을 관리하는 역할을 합니다. 추가 스탯 스크립터블 오브젝트로 만들고 리스트에서 관리하는 식으로 구현했으며, 스탯의 업데이트나 리미트를 거는 기능을 가지고있습니다.
- DieBehavior -> 애니메이션 종료 시점에 Destroy 해야 할 경우 사용하는 스크립트입니다. 애니메이션 이벤트로 스크립트를 등록해 사용했습니다.
- DisappearOnDeath -> 캐릭터 사망시 처리를 담당하고 있습니다. 애니메이션을 실행시키고 천천히 사라지는 연출등을 보여줍니다.
- HealthSystem -> 체력에 따른 처리를 담당합니다. 현제 체력을 따로 설정하고 힐, 데미지, 사망시 처리등을 합니다.
- Movement -> 캐릭터의 이동을 관리합니다. 이동이 가능한 상태인지 체크하고 이동,넉백 등을 실행합니다.
- Shooting -> 투사체를 만들어 ObjectPoolManager를 실행하는 역할을 합니다. 스크립터블 오브젝트로 정보를 받고 정보를 바탕으로 투사체를 설정한뒤 ObjectPoolManager로 생성합니다.

**Manager**
- ObjectPoolManager -> 오브젝트 풀링을 관리하는 역할을 합니다. 사운드와 투사체를 풀링하여 필요한 프리팹을 반환합니다.
- SelectManager -> 셀렉트씬과 관련된 씬이동을 관리하는 역할을 합니다.
- SoundManager -> 사운드를 관리하는 매니저 스크립트입니다. Clip 을 받아 효과음을 실행하거나 BGM 을 교체하는 기능등이 있습니다.
- SoundSource -> 스피커 기능을 하는 스크립트입니다. 프리팹에 SoundSource 컴포넌트와 함께 장착해 오브젝트 풀링해두는 식으로 사용했습니다.
