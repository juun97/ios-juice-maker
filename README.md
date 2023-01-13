# 쥬스메이커🧃

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


## 팀원을 소개합니다 👀
무리 | 릴라 | 세홍
--- | --- | ---
<img width="200" alt="image" src=https://i.imgur.com/U7TmXby.jpg> |<img width="200" alt="image" src=https://cdn.discordapp.com/attachments/1054218081787973662/1058207490296262665/KakaoTalk_Image_2022-12-23-11-04-10.png> | <img width="200" alt="image" src=https://i.imgur.com/Eu4tzfs.png> 




## 타임라인 ⏰


| STEP  | 날짜             | 타임라인                                                                                                                                                                     |
| --------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|STEP1| **2023.01.02** | - fruitStore타입 정의 </br>- Menu, Recipe enum 타입 정의 </br> -  Juice타입 파일 분리, 원시값 설정 </br> - 쥬스 만드는 함수 구현, fruit 타입 파일 분리 </br> - error타입 정의 및 에러처리 </br> - 문서 헤더 수정 |                                          |
|    STEP1   | **2023.01.03** | - fruitStore 초화 함수 구현  </br>- 과일재고 확인 함수 구현 </br>- 재고 확인 함수 구현 및 에러 처리 </br>- 쥬스 만드는 함수 구현, 쥬스 완성 안내문 함수 구현 </br>- 접근제어자 지정, 변수명 수정 |         |                                               |
|    STEP1   |**2023.01.04~05**| - 컨벤션 수정 및 변수명 수정</br> - 메서드명, 전달인자 이름 변경 
|    STEP2   |**2023.01.09**| - 뷰컨트롤 라벨에 과일 재고 연결</br> - 화면전환 메서드 구현</br> - 화면연결, UI정렬 및 버튼 추가</br> - 쥬스만들기 버튼 액션 구현</br> - notificationName파일 추가</br> - 쥬스제조 성공과 실패에 따른 Notification post</br> - 코드 공백제거
|    STEP2   |**2023.01.10**| - final키워드, 접근제어자 추가</br> - 버튼 아울렛 생성, 연결</br> - 쥬스 제조버튼 로직 수정</br> - 데이터 전달방식 변경, 필요없는 함수 제거</br> - EditStockViewController의 identifier 선언</br>


-----










## 실행화면 🎬

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
### 1️⃣ 화면 전환
- 화면 전환 시 다음과 같은 오류를 겪었습니다.
> Thread 1: "Storyboard (<UIStoryboard: 0x60000232ea00>) doesn't contain a view controller with identifier
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

## Reference
- [Singleton 정리 블로그](https://cheershennah.tistory.com/223)
- [Initialization 공식문서](https://docs.swift.org/swift-book/LanguageGuide/Initialization.html)
- [화면전환 오류해결 참고 링크](https://velog.io/@junsuboy/Swift-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0-doesnt-contain-a-view-with-identifier)

---
