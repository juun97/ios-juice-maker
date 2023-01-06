# 쥬스메이커🧃

## STEP 1 소개
> 쥬스를 만드는 JuiceMaker 와 과일을 관리하는 FruitStore 타입을 정의합니다.

_요구사항_


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


## 팀원을 소개합니다👀
무리 | 릴라 | 세홍
--- | --- | ---
--- |<img width="200" alt="image" src=https://cdn.discordapp.com/attachments/1054218081787973662/1058207490296262665/KakaoTalk_Image_2022-12-23-11-04-10.png> | <img width="200" alt="image" src=https://i.imgur.com/Eu4tzfs.png> 




## 타임라인


| STEP  | 날짜             | 타임라인                                                                                                                                                                     |
| --------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|STEP1| **2023.01.02** | - fruitStore타입 정의 </br>- Menu, Recipe enum 타입 정의 </br> -  Juice타입 파일 분리, 원시값 설정 </br> - 쥬스 만드는 함수 구현, fruit 타입 파일 분리 </br> - error타입 정의 및 에러처리 </br> - 문서 헤더 수정 |                                          |
|    STEP1   | **2023.01.03** | - fruitStore 초화 함수 구현  </br>- 과일재고 확인 함수 구현 </br>- 재고 확인 함수 구현 및 에러 처리 </br>- 쥬스 만드는 함수 구현, 쥬스 완성 안내문 함수 구현 </br>- 접근제어자 지정, 변수명 수정 |         |                                               |
|    STEP1   |**2023.01.04~05**| - 컨벤션 수정 및 변수명 수정</br> - 메서드명, 전달인자 이름 변경 

-----



## 구현할 메서드

STEP 1

JuiceMakeer 
- 쥬스제조 메서드 : makeJuice
- 에러제어 메서드 : handleStockError
- 주문완료 안내문 출력 메서드 : printCompleteMessage

FruitStore
- Singleton Pattern
- 인스턴스 생성시 과일 재고 초기화 메서드 : initializeDefaultStock
- 재고 확인 메서드 : checkStock
- 재고 차감 메서드 : useFruit
- 잔여 재고 확인 메서드 : checkRemainStock






## 트러블슈팅

### 1️⃣ Fruits의 Initialize
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


## Reference
- [Singleton 정리 블로그](https://cheershennah.tistory.com/223)
- [Initialization 공식문서](https://docs.swift.org/swift-book/LanguageGuide/Initialization.html)
