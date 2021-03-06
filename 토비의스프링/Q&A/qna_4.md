# 4주차  
#### :bulb: 질문은 여기에  
대답은 여기에  
내용 끝나면 아래쪽에 라인 넣어줍시다.

--------

#### :bulb: 템플릿/콜백 패턴에 대해 설명해 주세요 by. 태현

- 전략 패턴이지만 전략을 client측에서 용도에 맞게 바꿀 수 있는 패턴으로, 변하지 않는 흐름(context)은 템플릿으로, 자주 변하는 부분은 콜백이라 합니다. 자주 변하는 부분의 전략을 템플릿 내의 흐름에서 필요한 곳에 주입받은 콜백을 호출하도록 하며, 일반적으로 콜백은 메서드 전달이 목적이기 때문에 메서드를 하나만 갖는게 일반적이다. 템플릿 내에서는 콜백을 호출하는 부분을 인터페이스로 처리하며, 외부에서 1회성으로 주입하는 콜백의 경우 익명 클래스, 템플릿과 결합해 자주 호출된다면 템플릿 내부에 선언하도록 책에선 권장한다.

--------

#### :bulb: 템플릿/콜백 패턴를 만드는 방법에 대하여 설명해 주세요 by. 주연  
- 인터페이스를 구현한 익명 내부 클래스를 사용해서 매번 전략을 새로 만들어 사용하고, 컨텍스트 호출과 동시에 전략 DI를 수행하는 방식입니다.

--------

#### :bulb: 네거티브 테스트에 대하여 설명해 주세요 by. 주연
- 예외적 조건으로 문제를 야기하는 테스트를 먼저 작성한다. 일반적으로 프로그래머들은 빠르게 테스트를 통과해 다음으로 나아가고자 하는 본능적 욕구가 있기 때문에, 테스트를 완전하게 작성하기 위한 방법이다.

--------

#### :bulb: ResultSetExtractor와 RowMapper의 공통점과 차이점을 설명해 주세요 by. 태현
- 공통 적으로 ResultSetExtracor과 RowMapper 둘 다 ResultSet을 받아서 추출하고 원하는 타입으로 리턴하는 역할을 합니다. 차이점으로는 ResultSetExtractor는 ResultSet을 한 번 전달받아 알아서 추출 작업을 모두 진행하고 최종 결과만 리턴해주면 되는 데 반해, RowMapper는 ResultSet의 Row 하나를 매핑하기 위해 사용되기 때문에 여러 번 호출될 수 있습니다.


--------

#### :bulb: callback이 왜 클래스여야 하는지, 왜 책에서 callback은 메서드를 하나만 담고 있어야 하는지, Java의 한계에 대하여 함수형 패러다임에서 Javascript와 비교하시오 by. 대연  
- Java는 클래스 형태만 객체로 취급하기 때문에 콜백 함수를 만들기 위해 함수형 클래스를 생성해야 하는 부분에서 번거로움이 있지만,  
JavaScript는 함수도 일급 객체로 취급하기 때문에 더욱 간편하게 함수형 프로그래밍을 할 수 있습니다. 

--------

#### :bulb: 책에서 제시한 제네릭의 예시 중 하나로 string concatenate를 제시하였는데, 이 예시의 문제점과 이를 개선하는 방법은 무엇이 있을지 제시하세요.  by. 대연

- 일반적으로 연산자나 메서드가 겹치는 경우가 자주 없을 것이며, 이 경우엔 그냥 제네릭 대신 인터페이스를 사용하는게 바람직하다고 생각한다.
String + String은 비효율적이며, StringBuilder를 통해 작성하는게 효율적이며 이 연산을 처리하기 위해서 또 템플릿/콜백을 적용하면 복잡함만 증가한다. 편하게 쓰자고 제안하는 Java의 언어적 기능이지만 불필요하다고 생각한다.

--------

#### :bulb: nested class에 대해서 아는대로 설명해 주세요 by. 정수 
- 스태틱 클래스(static) 
  outer class와 관련 없이 독립적으로 인스턴스를 만들 수 있는 클래스이다. 
- 내부 클래스(inner) 
  독립적으로 객체를 생성할 수 없으며, public private와 관계없이 외부에서 내부 클래스의 객체를 만들 경우에는, 외부 클래스도 함께 만들어주어야 한다. 외부 클래스를 생성할 때 마다 내부 클래스의 메타 정보가 들어가므로 외부 클래스의 메모리 공간 점유에도 영향을 미친다.
  - 멤버 내부 클래스(member inner class)
    멤버 필드처럼 선언되며 object 스코프를 갖는다.
  - 로컬 클래스(local class)
    메서드 내부에 선언되는 클래스를 이르며 method 내부에서만 사용 가능한 스코프를 갖는다.
  - 익명 내부 클래스(anonymous inner class)
    이름을 갖지 않는다. scope는 선언된 위치에 따라 다르다. 인스턴스는 스코프의 시작점에서 생성되고 스코프가 끝날 때 gc된다.
    
--------
