# 7장. 모놀리식에서 마이크로서비스로 : 마이크로서비스 만들기

- 결합도 : 코드의 한 요소가 다른 요소와 얼마나 의존적인지 나타내는 정도.
  - 결합도가 높을 때 문제점
    - 다른 요소가 변경되면 더불어 변경해야 한다.
    - 수정하는 요소를 이해하기 위해 연관된 요소를 함께 이해해야 한다.
    - 다른 프로그램에서 요소를 재사용하기 힘들다.
- 응집도 : 프로그램의 한 요소에 얼만큼의 연관된 책임과 아이디어가 뭉쳐있는지 나타내는 정도.
  - 응집도가 낮을 때 문제점
    - 요소를 이해하기 힘들다.
    - 재사용하기 힘들다.
    - 유지보수하기 힘들다.
    - 다른 요소의 변화에 민감하다.
  - 응집도가 높은 요소의 특징
    - 메소드의 개수가 상대적으로 적다.
    - 다른 요소와 협력하여 혼자 많은 일을 하지 않는다.