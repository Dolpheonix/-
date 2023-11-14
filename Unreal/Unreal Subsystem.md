# Unreal Subsystem
객체의 수명 cycle이 보장되므로, SubSystem을 상속받게 되면 해당 모듈의 생성, 소멸 시에 같이 생성, 소멸된다.

## 1. Engine Subsystem
GEngine의 생성 주기와 같이 행동

## 2. Editor Subsystem
GEditor의 생성 주기와 같이 행동

## 3. GameInstance Subsystem
UGameInstance와 같이 행동

## 4. LocalPlayer Subsystem
ULocalPlayer와 같이 행동

## 언제 사용할까?
만약 UGameInstance를 파생한 커스텀 게임 인스턴스 클래스를 사용한다고 해보자. 그 경우, UGameInstance를 파생하기 위해 다양한 함수를 오버라이드해 구현해야 한다.
하지만, 그럴 필요 없이 그저 몇 가지 기능만 추가하고, 이러한 기능이 UGameInstance의 라이프타임동안 유지되도록 하고 싶다면, UGameInstanceSubSystem를 상속받아 
Initialize(), DeInitialize() 함수만 오버라이드 하게되면 끝난다.

## 어떻게 접근할까?
각 메인 객체에서 접근 가능<br>
```GetGameInstance()->GetSubsystem<UMyGameInstanceSubsystem>();```
