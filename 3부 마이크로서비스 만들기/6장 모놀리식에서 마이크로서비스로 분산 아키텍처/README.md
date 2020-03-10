# 6장. 모놀리식에서 마이크로서비스로 : 분산 아키텍처

- 토폴로지 : 컴퓨터 네트워크를 구성할 때 링크, 노드 등을 이용해 물리적으로 연결하는 방식

  - 버스형 : 전체 노드가 하나의 공통 연결선에 연결된 구조

    ![image-20200310193458330](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200310193458330.png)

    - 노드 간 간섭이 없어 안정적이다. (버스만 안정적이라면)
    - 노드 추가, 삭제가 쉽다.
    - 버스에 부하가 발생하면 전체 성능이 저하된다.

  - 트리형 : 여러 버스 토폴로지를 결합한 구조

    ![image-20200310193631390](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200310193631390.png)

  - 링형

    ![image-20200310193756572](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200310193756572.png)

    - 부하가 집중되는 노드가 없어 병목이 발생하지 않음.
    - 한 노드의 장애가 전체 장애로 이어진다.

  - 성형

    ![image-20200310193927619](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200310193927619.png)

    - 중앙 집중식으로 노드 확장이 쉽다.
    - 노드 수가 증가할수록 효율이 떨어진다.

  - 망형 : 그물 모양으로 각 노드를 1 : 1로 연결하는 구조

    ![image-20200310194135359](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200310194135359.png)

    - 장애에 가장 안정적이다.
    - 구현이 어렵다.



- 자바스크립트 String.prototype.charAt(index)

  - 문자열에서 특정 인덱스에 위치하는 유니코드 단일문자를 반환한다.

  ~~~javascript
  const str = 'Javascript study';
  
  console.log(str.charAt(5)); // 'c'
  ~~~



- 마이크로서비스 아키텍처는 마이크로서비스, 게이트웨이, 분산 처리 서버로 구성할 수 있다.