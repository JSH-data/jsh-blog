---
{"dg-publish":true,"permalink":"/design-pattern/what-is-design-pattern/"}
---

# What is Design Pattern

![Pasted image 20231104161524.png](/img/user/assets/Pasted%20image%2020231104161524.png)
**디자인 패턴**이란 소프트웨어 디자인 과정에서 자주 발생하는 문제들에 대한 일반적인 해결책입니다. 코드에서 반복적으로 되풀이되는 문제점들을 '규약'을 통해 정의하여 방지합니다.

### Difference with Algorithm
[[알고리즘\|알고리즘]]과 디자인 패턴은 의미론적으로 보면 비슷한 기능을 하는 것처럼 보이지만 실제로 다른 개념입니다. 
두 가지 개념의 차이점은 다른 수준의 해결방식을 제공하는 것에 있습니다.
알고리즘은 어떤 목표를 달성하기 위한 명확한 절차를 해결책으로 제시하는 반면, **디자인 패턴**은 **더 상위 수준의 해결책을 제시**합니다. 알고리즘처럼 목표를 달성하기 위한 기능 및 결과를 제시하면서, 더 자세한 구현 단계 및 순서를 사용자가 임의로 결정할 수 있도록 합니다.

### Difference with Architectural Pattern
[[Design Pattern/Architecture Pattern\|Architecture Pattern]]도 디자인 패턴과 비슷하기 때문에 헷갈리는 주제 중 하나 입니다. **Architectural Pattern**은 디자인 패턴보다 더 상위 수준의 개념으로 시스템의 기본 구조 구성에 관한 개념입니다. Flux Pattern, MVC Pattern, MVVM Pattern 등이 대표적인 Architectural Pattern입니다. 

## Why We need Design Pattern
우리가 **디자인 패턴**을 배워야하는 이유 중 핵심적인 이유는 다음과 같습니다.

1. 문제 해결
	- 디자인 패턴은 선배 개발자들이 현업에서 치열한 고민 끝에 특정 문제들을 해결하기 위해 고안한 규약입니다. 디자인패턴을 이해하고 적재적소에 사용할 수 있다면 이미 검증이 끝난 안전한 방향으로 개발할 수 있을 것입니다.

2. 협업 효율성 증대
	- 디자인 패턴은 코드 디자인을 사전에 정의한 것입니다. 팀원 모두가 디자인 패턴에 대해 알고 있다면 코드 개발 방향에 대한 상호 질문을 획기적으로 줄일 수 있을 것입니다. 

## Design Pattern's Category
![Pasted image 20231104162529.png](/img/user/assets/Pasted%20image%2020231104162529.png)

[GoF(1994)](https://ko.wikipedia.org/wiki/%EB%94%94%EC%9E%90%EC%9D%B8_%ED%8C%A8%ED%84%B4_(%EC%B1%85))에서 디자인 패턴을 활용 목적에 따라 [[Design Pattern/Creational Pattern\|Creational Pattern]], [[Design Pattern/Structural Pattern\|Structural Pattern]], [[Design Pattern/Behavioral Pattern\|Behavioral Pattern]] 총 3가지로 분리하였습니다. 
## Real Case of Design Pattern
디자인 패턴은 우리가 이미 익숙하게 사용하고 있는 유명한 [[Design Pattern/Library와 Framework\|Library와 Framework]]등에서 실제로 사용되고 있습니다. Node.js에서 인증 미들웨어를 구축할 수 있도록 도와주는 [Passport.js](https://www.passportjs.org/)는 [[Design Pattern/Strategy Pattern\|Strategy Pattern]]으로 설계되었습니다. 

### Reference
- https://stackoverflow.com/questions/4243187/whats-the-difference-between-design-patterns-and-architectural-patterns
- https://refactoring.guru/ko