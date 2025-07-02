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