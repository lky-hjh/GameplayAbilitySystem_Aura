 这里是aura的开发日志，顺便学习学习md
## 2025.7.2
### 1.导入了主角的骨骼，绑定武器。
AAuraCharacterBase::AAuraCharacterBase()  
{  
    PrimaryActorTick.bCanEverTick = false;  
  
    Weapon = CreateDefaultSubobject<USkeletalMeshComponent>("Weapon");  
    Weapon->SetupAttachment(GetMesh(), FName("WeaponHandSocket"));  
    Weapon->SetCollisionEnabled(ECollisionEnabled::NoCollision);  
}
- 禁用了 Tick（`PrimaryActorTick.bCanEverTick = false`）。
    
- 创建了一个名为 `Weapon` 的 Skeletal Mesh 组件：
    
    - 并附加到了角色骨骼网格的名为 `"WeaponHandSocket"` 的插槽上。
        ``
    - 默认关闭了碰撞。
### 2.哥布林蓝图
- 1. Based on Aura Enemy (BP_Gobin_Spear)
- 2. Set the Mesh
- 3. Weapon Socket
- 4. Find Spear Asset
## 2025.7.3~2025.7.10
### 1.Animation Blueprint
- 1. Create Aura Animation Blueprint.
  - idle walk run state machine.
  - get Ground Speed from Character Movement Velocty Length XY.
- 2. Create Enemy Animation Blueprint.
  - idle walk run state machine.
- 3. Create Spear Goblin Animation based on Enemy Animation Blueprint.
- 4. Create SlingshotGoblin 
  - Based on Aura Enemy(Bp_Goblin_Slingshot)
  - Create SlingshotGoblin Animation Blueprint
## 2025.7.11
### Enhanced Input
Input Action:the way that we link this to our character.
1. create IA_Move
2. create IMC_AuraContext(input mapping context)
3. based Player Controller
   1. create AuraPlayerController.cpp
   2. Create a Plater folder
