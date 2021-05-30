# 20Conventions
안드로이드 개발시 내가 사용하는 컨벤션들에 대해 정리합니다.(Kotlin 기준)

## Project Setting

### Naming
- 카멜 표기법 사용

#### Resource Naming

----------------------------------------------
### Package
자주 사용하는 패키지
#### *apdater*
- Recyclerview에 사용하는 어댑터 클래스들
#### *base*
- activity, fragment, viewmodel등 베이스로 사용될 추상클래스
#### *db*
- DB작업에 사용되는 클래스들
#### *extension*
- bindingAdapter를 사용하는 클래스들
#### *factory*
- 팩토리 패턴을 사용하기 위해 생성된 클래스들
#### *model*
- mvvm 사용시 model에 해당하는클래스들
#### *network*
- retrofit에서 사용할 인터페이스들
#### *repository*
- repository 패턴을 사용하기 위해 생성된 클래스들  
└─  singleton 패턴을 적용함
#### *ui*
- activity, fragment 관련된 클래스들  
└─ 하위 패키지는 activity or fragment의 이름을 따서 지음  
└─ mvvm 패턴 사용시 viewModel 포함

---------------------------
## Layout 관련

### 이벤트 처리
레이아웃에서 이벤트가 발생했을때 처리방식
#### 버튼
##### 일반적인 버튼 
- extension에서 bindingAdapter를 통해 이벤트처리
##### 리사이클러뷰에 속해져있는 버튼
- 해당 리사이클러뷰의 adapter에서 onclickListener를 통해 이벤트처리


----------------------------
## 코드 관련
### viewModel
#### UI와 관련된 데이터
- 데이터를 받아오면 MutableLiveData에 저장하고 LiveData에서 해당 MutableLiveData를 받음  
└─ 캡슐화를 통해서 데이터를 보호
- LiveData에 옵저버를 달아주고 데이터 변경시 처리를 activity or fragment에서 처리
