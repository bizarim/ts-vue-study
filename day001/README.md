## vue 란?
Evan You가 만들었으며, 2014년 릴리즈를 시작으로 꾸준히 발전하고 있는 자바스크립트 프레임워크입니다.
컨트롤러 대신 뷰 모델을 가지는 MVVM(Model-View-ViewModel) 패턴을 기반으로 디자인되었으며,
재사용이 가능한 UI들을 묶어서 사용할 수 있습니다.


## vue의 주요 컨셉
처음 vue를 사용 할 때 의식해야 하는 것은, 
화면을 렌더링하는 구조 자체는 DOM이 아니라 자바스크립트 데이터라는 것입니다.
DOM이 먼저 존재하고, 
이것을 읽어 들인 후에 조작하는 것이 아니라 
데이터가 먼저 존재하고 이데이터를 기반으로 적절한 DOM을 구축한다는 것입니다.

데이터의 상태에 따라 렌더링이 변경되며, 때에 따라서는 자동으로 액션을 일으키기도 합니다.
이처럼 데이터를 중심으로 하는 애플리케이션 설계를 데이터 지향이라고 부릅니다.

이해하기 쉬운 템플릿
