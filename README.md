# 쥬스메이커🧃

## 팀원을 소개합니다 👀
|<center>[무리](https://github.com/parkmuri)</center> | <center> [릴라](https://github.com/juun97)</center> | <center>[세홍](https://github.com/sehoong0429)</center>|
|--- | --- | ---|
|<img width="200" alt="image" src=https://i.imgur.com/U7TmXby.jpg> |<img width="200" alt="image" src=https://cdn.discordapp.com/attachments/1054218081787973662/1058207490296262665/KakaoTalk_Image_2022-12-23-11-04-10.png> | <img width="200" alt="image" src=https://i.imgur.com/Eu4tzfs.png>| 

## 그라운드 룰 

<details>
<summary>Ground Rule</summary>
    
1. 변수 설정할 시 타입 명시 다 해주기
2. 코드 한 줄에 100자 이상 넘어갈 시 [참고](https://google.github.io/swift/#line-wrapping)해서 컨벤션 해주기

### 활동 시간
1. 활동학습 있는날에는 점심먹고 2시부터 진행, 없는 날에는 9시 30분 ~ 18시
2. 필요 시) 수요일 23:00 이후에 간단하게 1-2시간 회고 Time

### 짝프로그래밍 역할 순서

순서| 감시자 | 네비게이터 | 드라이버
---|---|---|---
1|세홍 | 릴라 | 무리
2|무리 | 세홍 | 릴라
3|릴라 | 무리 | 세홍


### Karma Style
- Commit message subject type
- feat : 기능 구현
- refactor : 네이밍 수정
- docs : 문서 추가, 수정
- chore : 중요하지 않은(생산적이지 않은) 내용 수정

### Commit 단위
하나의 기능 별로 나눠서 커밋하기
</details>

## STEP 1 소개 🔎
> 쥬스를 만드는 JuiceMaker 와 과일을 관리하는 FruitStore 타입을 정의합니다.

<details>
<summary>요구사항</summary>

- FruitStore는 다음의 조건을 충족해야 합니다.

   - FruitStore가 관리하는 과일의 종류 : 딸기, 바나나, 파인애플, 키위, 망고
   - 각 과일의 초기 재고 : 10개
   - 각 과일의 수량 n개를 변경하는 기능이 있습니다.
   - 이 외에 더 필요한 기능, 특성, 타입이 있으면 자유롭게 추가해도 좋습니다.
 - JuiceMaker는 FruitStore의 과일을 사용해 과일쥬스를 제조합니다.
     - 딸기쥬스 : 딸기 16개 소모
     - 바나나쥬스 : 바나나 2개 소모
     - 키위쥬스 : 키위 3개 소모
     - 파인애플 쥬스 : 파인애플 2개 소모
     - 딸바쥬스 : 딸기 10개 + 바나나 1개 소모
     - 망고 쥬스 : 망고 3개 소모
     - 망고키위 쥬스 : 망고 2개 + 키위 1개 소모
   - 과일의 재고가 부족하면 과일쥬스를 제조할 수 없습니다.
   - JuiceMaker는 FruitStore를 소유하고 있습니다.
</details>


## STEP 2 소개 🔎
> 쥬스 메이커 앱을 실행시키는 데에 필요한 초기화면의 기능을 구성합니다.

<details>
<summary>요구사항</summary>

- 재고수정’ 버튼을 터치하면 ‘재고 추가’ 화면으로 이동합니다.
    - 이동 방식은 어떤 방식이 적절할까요? 
- 각 주문 버튼 터치 시
    - 쥬스 재료의 재고가 있는 경우 : 쥬스 제조 후 “*** 쥬스 나왔습니다! 맛있게 드세요!” 얼럿 표시
    - 쥬스 재료의 재고가 없는 경우 : “재료가 모자라요. 재고를 수정할까요?” 얼럿 표시
        - ‘예’ 선택시 재고수정화면으로 이동
        - ‘아니오’ 선택시 얼럿 닫기
- 과일쥬스를 제조하여 과일의 재고가 변경되면 화면의 적절한 요소에 변경사항을 반영합니다.
</details>

## STEP 3 소개 🔎
> 쥬스 메이커 앱에서 과일의 재고를 관리하는 기능을 추가합니다.

<details>
<summary>요구사항</summary>
    
- 화면 제목 ‘재고 추가’ 및 ‘닫기’ 버튼 구현
- 닫기를 터치하면 이전화면으로 복귀
- 화면 진입시 과일의 현재 재고 수량 표시
    - -, + 를 통한 재고 수정
- iPhone 12 외에 다른 시뮬레이터에서도 UI가 정상적으로 보일 수 있도록 오토레이아웃 적용

</details>




## 타임라인 ⏰

<details>
    <summary>타임라인</summary>

| STEP  | 날짜             | 타임라인                                                                                                                                                                     |
| --------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|STEP1| **2023.01.02** | - fruitStore타입 정의 </br>- Menu, Recipe enum 타입 정의 </br> -  Juice타입 파일 분리, 원시값 설정 </br> - 쥬스 만드는 함수 구현, fruit 타입 파일 분리 </br> - error타입 정의 및 에러처리 </br> - 문서 헤더 수정 |                                          |
|    STEP1   | **2023.01.03** | - fruitStore 초화 함수 구현  </br>- 과일재고 확인 함수 구현 </br>- 재고 확인 함수 구현 및 에러 처리 </br>- 쥬스 만드는 함수 구현, 쥬스 완성 안내문 함수 구현 </br>- 접근제어자 지정, 변수명 수정 |         |                                               |
|    STEP1   |**2023.01.04~05**| - 컨벤션 수정 및 변수명 수정</br> - 메서드명, 전달인자 이름 변경 
|    STEP2   |**2023.01.09**| - 뷰컨트롤 라벨에 과일 재고 연결</br> - 화면전환 메서드 구현</br> - 화면연결, UI정렬 및 버튼 추가</br> - 쥬스만들기 버튼 액션 구현</br> - notificationName파일 추가</br> - 쥬스제조 성공과 실패에 따른 Notification post</br> - 코드 공백제거
|    STEP2   |**2023.01.10**| - final키워드, 접근제어자 추가</br> - 버튼 아울렛 생성, 연결</br> - 쥬스 제조버튼 로직 수정</br> - 데이터 전달방식 변경, 필요없는 함수 제거</br> - EditStockViewController의 identifier 선언</br>
|    STEP3   |**2023.01.11**| - 버튼 아울렛 생성 후 화면과 연결</br> - 쥬스 제조버튼 액션 로직 수정</br> - 데이터 전달방식 변경, 필요없는 함수 제거</br> - EditStockView의 identifier 선언|
|    STEP3   |**2023.01.12**| - stackView로 정렬 |
|    STEP3   |**2023.01.13**| - EditStockVC UIOutlet 연결 및 Stepper 초기설정 메서드 구현</br> - stepper 액션 구현</br> - 반복문 로직 수정, 코드 위치 정리 </br> - delegate파일 생성</br>- EditStockView 화면종료시 데이터전달 로직 구현  |
|    STEP3   |**2023.01.16**| - 오토레이아웃 설정, 네비게이션 바 구현</br> - 레이아웃 제약 X,Y축으로 변경 |
|    STEP3   |**2023.01.17**| - 네이밍 변경, EditStockViewController 내 딕셔너리 반복문 로직 수정 |

</details>


-----


## 파일구조 🌲

<details>
    <summary>파일구조</summary>

```
JuiceMaker
|
├── Controller
│   ├── AppDelegate.swift
│   ├── EditStockViewController.swift
│   ├── JuiceMaker.swift
│   ├── SceneDelegate.swift
│   └── ViewController.swift
├── Model
│   ├── Fruit.swift
│   ├── FruitStore.swift
│   ├── Juice.swift
│   ├── JuiceMakeError.swift
│   └── JuiceMaker.swift
└── View
    ├── Assets.xcassets
    │   ├── AccentColor.colorset
    │   │   └── Contents.json
    │   ├── AppIcon.appiconset
    │   │   └── Contents.json
    │   └── Contents.json
    └── Base.lproj
        ├── LaunchScreen.storyboard
        └── Main.storyboard
```

</details>
    
## Class Diagram 🗺

<details>
    <summary>Class Diagram</summary>

<img width="1000" alt="image" src=https://i.imgur.com/vcdKVxs.png> 

</details>

## 실행화면 🎬
<details>
    <summary>실행 화면 1️⃣~4️⃣</summary>
    
### 1️⃣ 주문 성공
<img width="600" alt="image" src=https://i.imgur.com/6LVDyUk.gif>

- 초기 실행시 인터페이스 label 과 과일재고 데이터 연결
- 주문 성공시 Alert 띄우고 재고 차감


### 2️⃣ 재고수정 화면이동
<img width="600" alt="image" src=https://i.imgur.com/R7da9qD.gif>

- 재고수정시 다른 뷰컨트롤러를 불러와 화면이동
- 재고수정화면의 label 도 과일재고 데이터와 연결

### 3️⃣ 주문 실패 (아니요)
<img width="600" alt="image" src=https://i.imgur.com/e4hFcJ1.gif>

- 재고가 부족할 시 Alert 띄워주기
- 아니요를 클릭시 아무 액션을 취하지 않고 Alert 종료

### 4️⃣ 주문 실패 (예)
<img width="600" alt="image" src=https://i.imgur.com/E5ED7V1.gif>

- 재고가 부족할 시 Alert 띄워주기
- 예를 클릭시 재고수정 화면으로 이동하기
    
</details>
    
### 5️⃣ 재고 추가
<img width="600" alt="image" src=https://i.imgur.com/2pjH1ST.gif>

- Stepper 클릭시 버튼에 맞는 재고추가 혹은 감소 
- 바뀐 값은 Label 에 실시간으로 업데이트

### 6️⃣ 재고수정 후 초기화면으로 이동
<img width="600" alt="image" src=https://i.imgur.com/5PwhLMG.gif>

- 수정이 완료된 재고를 초기화면에서 업데이트

## STEP1 트러블슈팅 🚀
<details>
<summary>STEP1 트러블 슈팅</summary>
    
### 1️⃣ 과일재고 딕셔너리의 초기화
```swift
// 초반 작성 코드
class FruitStore {
    private var strawberry: Int = 10 
    private var banana: Int = 10
    private var pineapple: Int = 10
    private var kiwi: Int = 10
    private var mango: Int = 10    
}
```
- 처음 작성한 방향에서는 과일들을 각각의 프로퍼티로 `FruitStore` 에 생성하였으나 `JuiceMaker` 와 데이터를 주고 받는 과정에서 계속해서 switch문으로 어떤 과일인지 식별해줘야 하는 큰 번거로움이 있었습니다. 
- 이를 개선하기 위해 `Dictionary` 사용을 결정했습니다. 저희 조는 `Magic Number` 사용을 지양하기 위해 처음 Dictionary 각각의 Key(String)값의 Value(Int) 를 init()에 Value를 프로퍼티로 할당을 하려했으나 프로퍼티들이 `initialize` 되기전에는 할당을 할 수 없다는 에러가 발생해 다른 방법을 고민했습니다.

```swift
 private(set) var fruits: [Fruit : Int] = [:]

 private init() {
        initializeDefaultStock()
    }
    
    private func initializeDefaultStock() {
        let defaultStock = 10
        for fruit in Fruit.allCases {
            fruits[fruit] = defaultStock
        }
    }
```
- 기존 `FruitStore`에 존재하던 프로퍼티들은 `Enum` 타입으로 새로 정의하고 `FruitStore` 내에서는 `Dictionary[Fruit : Int]`만을 프로퍼티로 갖게 수정했습니다. 또한 `initialize` 될 때 각각의 과일 일때의 `Value` 값에 접근하여 `default` 값인 10을 할당 해주었습니다.


### 2️⃣ 각 주스별 recipe
```swift
// 초반 recipe 구현부분
enum Recipe {
        static let usingStrawberry = 16
        static let usingBanana = 2
// ...
        static let usingMixMango = 2
        static let usingMixKiwi = 1
    }

```
```swift
// Nested 타입을 사용한 Juice타입 내 구현 부분
    var recipe: [Fruit : Int] {
        switch self {
        case .strawberryJuice:
            return [.strawberry : 16]
        case .bananaJuice:
            return [.banana : 2]
// ...
        case .strawberryBananaJuice:
            return [.strawberry : 10, .banana : 1]
        case .mangoKiwiJuice:
            return [.mango : 2, .kiwi : 1]
        }
    }
```
- 초반에는 모든 경우에 맞춰 하나하나`Recipe`타입을 따로 정의하여 진행했습니다. 해당 과일쥬스에 `Int`값으로 소모되는 과일의 갯수는 할당해주었지만 **어떠한 과일인지** `Fruit`타입은 사용할 수 없었습니다.
- 그래서 열거형의 연산 프로퍼티와 딕셔너리를 활용해 `recipe`마다 `Fruit`타입의 과일이 몇개 소모되는지를 구현할 수 있었습니다.

### 3️⃣ Singleton
- `JuiceMaker의` 경우 `FruitStore의` 인스턴스를 소유하고 있어 `JuiceMaker` 가 생길때마다 새로운 `FruitStore`의 인스턴스도 같이 생성돼 재고관리에 어려움이 있었습니다. `class FruitStore` 같은 경우 처음 인스턴스화 되고 나서 그 인스턴스가 다른 인스턴스로 변경이 되면 재고의 초기값도 새로 적용이 되어 인스턴스를 단 하나만 생성해 사용해야 겠다고 생각 했습니다. 그렇기 때문에 단 하나의 인스턴스만을 보장하는 `Singleton` 패턴을 사용하여 문제를 해결했습니다.
</details>
    
## STEP2 트러블슈팅 🚀
<details>
<summary>STEP2 트러블 슈팅</summary>

### 1️⃣ 화면 전환
- 화면 전환 시 다음과 같은 오류를 겪었습니다.
> Thread 1: "Storyboard (</UIStoryboard: 0x60000232ea00>) doesn't contain a view controller with identifier
- 스토리보드에서 연결을 시켜주었다고 생각했는데 오류를 보니 뷰컨트롤러의 identifier가 설정되어있지 않아서 발생하는 오류였습니다. 스토리보드에서 `Storyboard ID`를 설정해주니 오류가 사라지고 정상적으로 작동하는 모습을 볼 수 있었습니다.


### 2️⃣ 중복되는 코드의 축약
- 주문받은 쥬스를 만드는 과정에서 "어떤 쥬스에 대해 주문이 들어왔는지" 식별하기 위해 switch문을 사용했습니다. 결과적으로 약 20줄 가까이 되는 코드로 표현이 되었습니다.
```swift 
guard let senderID = sender.restorationIdentifier else { return }
        switch senderID {
        case "OrderStrawberryBanana":
            juiceMaker.makeJuice(.strawberryBananaJuice)
        // ...
        case "OrderMangoKiwi":
            juiceMaker.makeJuice(.mangoKiwiJuice)
        default:
            return
        }
```
- 리뷰 중 중복으로 사용되는 코드가 많아 간단하게 줄일 수 있는 방법과 `Restoration ID`의 사용에 대해 고민해보라는 내용이 있어 팀원들과의 상의 끝에 `tag`를 사용해보기로 했습니다.
```swift
@IBAction func makeJuiceButtonDidTap(_ sender: UIButton) {
        let juiceMaker = JuiceMaker()
        
        for juice in Juice.allCases {
            guard sender.tag == juice.rawValue else { continue }
            juiceMaker.makeJuice(juice)
        }
    }
```
- `Juice`타입의 원시값과 버튼들의 태그값을 동일하게 설정 후 `Juice`타입을 for문을 돌려 확인하는 방향으로 수정하게되었습니다.

### 3️⃣ 데이터전달을 위한 notification의 사용에 대하여
- 수정 전 STEP2에서는 notification center를 이용해 데이터 전달을 하고있었습니다. 리뷰 후 notification을 사용하게되면 필요없는 뷰에도 이벤트가 전달되는 문제가 있다고하여 다양한 다른 방법들을 고민해보았습니다.
- 맨 먼저 KVO의 사용에 대해 고민해보았는데, `KVO` 적용 시 이미 `ViewController`가 `UIViewController`상속을 받고있기 때문에 적용이 어려웠습니다.
- 다른 방법으로 `delegate`를 사용하려고 했습니다. 하지만 `delegate`의 인스턴스가 생성되는 시점이 `ViewController`의 `viewDidLoad()`보다 앞선 시점이라 해결이 어려웠습니다. 또 질문을 통해 이렇게되면 Singleton, (성공/실패 알람을 위한)notification에 delegate까지 사용하게되어 비효율적이라는 말을들었습니다.
- 따라서 선언해놓은 Singleton을 최대한 이용하는 방향으로 진행하게 되었습니다.

### 4️⃣ String으로 선언한 Identifier
- 처음 작성했던 코드 중 일부입니다.
```swift
func changeStockView() {
        guard let editStockView = self.storyboard?.instantiateViewController(withIdentifier:
                                                                                "EditStockViewController") else { return }
```
`identifier`를 `"EditStockViewController"`스트링 값으로 입력 해놓았습니다. 리뷰 중 철자가 잘못되면 관련된 곳에서 모두 수정해야하는 문제가 있을것이라는 피드백이 있었습니다.
- 수정 후 코드 중 일부입니다.
```swift
// EditStockViewController.swift
final class EditStockViewController: UIViewController {
    static let identifier = "EditStockViewController"

// viewController.swift
func changeStockView() {
    guard let editStockView = self.storyboard?.instantiateViewController(withIdentifier:
                                                                                EditStockViewController.identifier ) else { return }
```
 `EditStockViewController`의 `identifier`를 전역상수로 선언해준 뒤 사용하여 문제를 해결했습니다.


</details>

## STEP3 트러블슈팅 🚀
    
### 1️⃣ 오토 레이아웃
- 생각보다 오토 레이아웃을 적용시키는데에 시간이 많이 소요되었습니다..👀 예제를 볼때는 쉽다고 느껴졌는데 현재 프로젝트에 적용시키면서 어려움을 겪었습니다. 
- 프로젝트의 `맛있는 쥬스를 만들어 드려요! Scene`을 참고하여 제약을 걸어주었습니다. leading, trailing을 각각 Safe Area에, top을 `Navigation Bar`의 bottom에 제약을 걸어주면서 정상적으로 작동하는 모습을 볼수있었습니다. 하지만 이렇게 되면 상대적으로 큰 화면인 기기에서는 너무 위쪽에 위치해있을수도 있다는 생각이 들었고 X축, Y축 정렬을 함께 써 정 가운데 정렬이 되는 방향으로 사용했습니다.
    
### 2️⃣ presentedViewController＆presentingViewController
- `Navigation Bar`를 새로 만들어 `닫기`버튼에 대한 액션을 구현 하며 `Navigation Bar`가 있는 `EditStockView`에서 `dismiss`를 해주었습니다. 
  ```swift
  @IBAction func dismissButtonDidTapped(_ sender: UIButton) {
        dismiss(animated: true, completion: nil)
  }
  ```
- 링고의 리뷰에서 `presentedViewController`와 `presentingViewController` 프로퍼티에 대해 알게되었고 `뷰를 띄운 객체가 띄운 뷰를 dismiss하는 책임을 가져야한다`코멘트를 참고하여 코드를 다시 작성하게 되었습니다.
   ```swift
   @IBAction func dismissButtonDidTapped(_ sender: UIButton) {
        presentingViewController?.dismiss(animated: true)
    }
   ```
> `presentedViewController` : **자신이 호출한** ViewController
`presentingViewController` : **자신을 호출한** ViewController

### 3️⃣ 과일 종류에 맞는 Stepper 와 Label 의 연결
- EditStockViewController 내에서 사용한는 각각의 Fruit에 해당하는 Stepper 와 Label 을 Fruit 와 `연관성` 을 만들어주는 부분에서 많은 고민을 했습니다. 
- 코드를 볼때 개발자의 경우 네이밍을 통해 분류를 할 수 있겠지만 컴파일러는 객체 사이의 `연관성` 을 파악할 수 없는 것이 문제 였습니다.

그래서 생각한 것이 Fruit 와 Stepper 그리고 Fruit와 Label 을 엮은 `딕셔너리` 를 만들어 컴파일러도 둘 사이의 `연관성` 을 인지할 수 있게 만들었습니다.
```swift 
func findEachFruitStepper(of fruit: Fruit) -> UIStepper? {
        let stepperDictionary: [Fruit: UIStepper] = [.strawberry: strawberryStepper,
                                                     .banana: bananaStepper,
                                                     .pineapple: pineappleStepper,
                                                     .mango: mangoStepper,
                                                     .kiwi: kiwiStepper]
        guard let stepper = stepperDictionary[fruit] else { return nil }
        return stepper
    }    
```    
위 로직을 사용해 과일을 전달하면 해당 과일에 맞는 Stepper 와 Label 이 무엇인지 알 수 있게 되었습니다.
### 4️⃣ Stepper의 Value 설정
- Stepper의 Value 는 타입은 Double 이었기에 Double 타입으로의 형변환이 필요했습니다. 그래서 처음 생각한 것이 고차함수를 이용한 Value 들의 형변환 이었습니다.
```swift
guard let fruitStock = fruitStore.fruits.mapValues{ Double($0) } else { return } 
```
- 위 방식으로 접근을 해봤으나 오류로 인해 다른 방법을 시도해 보았습니다. 다시 생각해본 흐름으로는  `FruitStore` 클래스에서 과일을 받으면 해당 과일에 해당하는 재고를 Int 타입으로 반환하는 메서드를 만든 후 EditStockViewController 에서 받은 값을 Double 로 변환해 할당을 하는 것이었습니다. 
정상작동은 하고 있었지만 아래와 같은 문제가 발생했습니다.
> 1. 반환타입이 있었기에 매직넘버가 생겼습니다.
> 2. 이를 해결하기 위한 throw 문이 필요했습니다.
> 3. throw문이 있는 메서드를 실행하기 위해 try 문이 필요했습니다.
 
그저 재고의 Int 값이 필요했을 뿐인데 배보다 배꼽이 더 커져 버리게된 상태에서 링고의 피드백을 받아 개선된 로직을 짤 수 있었습니다.
```swift
   func setStepper() {
        fruitStore.fruits.forEach { fruit, amount in
            guard let fruitStepper = findEachFruitStepper(of: fruit) else { return }
            
            fruitStepper.value = Double(amount)
            fruitStepper.minimumValue = 0
            fruitStepper.autorepeat = true
        }
    }
```
`foreach` 문을 통해 다른 메서드를 거치지 않고 바로 딕셔너리내에서 `바인딩` 이 된 `value` 값을 사용할 수 있게되어 한 메서드안에서 모든걸 다 처리할 수 있게 되었습니다.


## Reference
- [Singleton 정리 블로그](https://cheershennah.tistory.com/223)
- [Initialization 공식문서](https://docs.swift.org/swift-book/LanguageGuide/Initialization.html)
- [화면전환 오류해결 참고 링크](https://velog.io/@junsuboy/Swift-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0-doesnt-contain-a-view-with-identifier)
- [presendtedViewController, presentingViewController 1](https://yoojin99.github.io/app/presentedViewController,-presentingViewController/)
- [presendtedViewController, presentingViewController 2](https://velog.io/@leedool3003/iOS-dismiss-%ED%95%98%EA%B3%A0-present-%EB%84%98%EC%96%B4%EA%B0%80%EA%B8%B0-Presented-vs-Presenting-ViewController)
---

## 스텝 수행 중 핵심 경험
<details>
    <summary>스텝별 핵심경험</summary>
    
### STEP 1
- [x]  Swift API Design Guide에 따른 이름짓기
- [x]  소스코드에 불필요한 코드 및 코멘트 남기지 않기
- [x]   메서드의 기능단위 분리
- [x]   요구사항에 따른 타입의 정의
- [x]   타입의 캡슐화/은닉화
- [x]   상황에 알맞은 상수/변수의 올바른 선택
### STEP2
- [x]   내비게이션 바 및 바 버튼 아이템의 활용
- [x]   얼럿 컨트롤러 활용
- [x]   Modality의 활용
- [x]   화면 사이의 데이터 공유
### STEP3
- [x]   내비게이션 바 및 바 버튼 아이템의 활용
- [x]   얼럿 컨트롤러 활용
- [x]   Stepper 활용
- [x]   Modality의 활용
- [x]   화면 사이의 데이터 공유
- [x]   오토레이아웃 시작하기
    
</details>
    
## 팀 회고

<details>
    <summary>🥹팀회고 펼쳐보기</summary>

### 무릴라홍이 잘한 점
1. 의견을 말하는걸 겁내지 않고 활발하게 대화를 나눴어요👍🏻
2. 빠름에 집착하지 않고 초조해 하지 않으려고 노력했어요🤡
3. 사정이 있어 빠지는 팀원들이 있었음에도 서로 잘 챙겨주며 스텝을 진행했어요🫶
4. 서로에 대한 칭찬과 격려를 아끼지않았어요👏
### 무릴라홍의 아쉬운 점
1. 팀원이 많다보니 서로 시간맞추기가 어려웠어요😢
2. 그라운드 룰에서 정한 활동시간을 종종 바꾸곤 했어요😂 

### 서로에게 건내는 한 마디
- To 무리
    - 무리 우선 3주동안 너무 고생 많았어요!! 중간에 일 생겨서 잠깐 참여 못했지만은 그만큼 더 메꾸려고 노력하신게 너무 대단하십니다!! 저 였으면 그 차이를보고 힘이 쭉 빠져서 의욕을 좀 잃었을거 같은데 무리의 의지 존경합니다🥹 
    From 릴라
    
    - 3주동안 수고 많으셨어요! 무리는 프로젝트를 진행하는 동안에 부족한 개념이나 모르는 부분에 대해서 항상 의문점을 가지고 계속 배우려는 태도가 너무 멋있다고 생각했어요! 다음 프로젝트에서는 지금 보다 더 잘해내는 모습 너무 기대됩니다 ㅎㅎㅎ 3주동안 너무 감사드려요! 
    From 세홍

- To 릴라
    - 릴라!! 함께 3주동안 고생 많으셨습니다. 이해못한 코드 자세하게 설명해주신점 너무 감사했습니다👏 항상 유쾌하셔서 같이 팀프로젝트 하는동안 너무 재밌었어요!! 다음번에 또 같은팀이 된다면 레벨업해서 저도 열심히 도움이 되겠습니다☺️ 
    From 무리

    - 릴라 프로젝트 하는 동안 수고 너무많으셨어요.저의 개인적인 일로 도움이 되지 못한 것 같아서 너무 죄송한 마음이 듭니다.앞으로 릴라가 하는 것처럼 저도 열심히 배우고 공부해서 다음에 프로젝트를 같이 하게 된다면 많은 도움이 될 수 있도록 해볼게요! 3주동안 이끌어주셔서 정말 감사했습니다!  
    From 세홍

- To 세홍
    - 세홍!! 3주동안 고생 많으셨습니다! 저도 세홍도 중간에 집안사정이 겹쳐서 힘들었을텐데... 위로해주셔서 감사했어요! 정말 큰 도움이 됐답니다🥲🫶 또 초반에 서로 의견을 나누는데 있어서 제가 너무 딱딱했던것같아서 죄송합니다🥲 하지만 이야기하면서 더 좋은방향으로 찾아갔다고 생각해요!! 3주동안 감사했습니다☺️ 
    From 무리

    - 세홍도 3주 동안 너무 고생 많았습니다!!! 한번씩 제가 무심결에 놓치고 당연하게 생각했던것들에 대한 날카로운 질문들은 저를 그 문제에 대해 다시 한번 돌아보게 만들었어요! 중간에 사정이 생겨 잠시 참여 못했지만 다시 와서 열심히 하시는 모습 너무 보기 좋았습니다👍🏻
    From 릴라

</details>
