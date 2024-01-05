# 20Conventions
안드로이드 개발시 내가 사용하는 컨벤션들에 대해 정리합니다.(Kotlin 기준)

## Project Setting

### Naming
- 카멜 표기법 사용

### Resource Naming

#### Layouts

\(what)_(where\)

- what : activity, fragment, view, item, etc..
- where : main, setting, etc...

##### example
- acitivty_main : MainActivity의 뷰
- framgent_detail : DetailFragment의 뷰
- dialog_main : MainActivity에서 사용될 다이얼로그
- item_location : LocationRecyclerview에 들어갈 아이템 뷰

#### IDs
(what)\_(where\)_(description)

- what : textview, button, etc...
- where : main, setting, etc..
- description : result, name, etc...

##### example
- textview_main_result : MainActivity의 결과값을 보여주는 textview

#### Strings

\(where)_(description\)  
- where : main, setting, all, etc..
- description : title, content, etc...

##### example
- main_title : MainActivity의 title에 사용
- all_content : 모든 뷰에서 content에 사용

#### Drawables

(what)\_(where)\_(description\)_(size)
- what: background, icon, etc..
- where : main, setting, all, etc...
- description : info, alert, etc...
- size : 24dp, 36dp, etc...

##### example
- main_info_24dp : MainActivity에서 사용될 24dp 크기의 info 이미지
- all_alert_36dp : 모든 뷰에서 사용될 36dp 크기의 alert 이미지

#### Styles
스타일에서 크기와 공백같이 디자인을 보면서 작업해야하는 것들은 아이템에서 제외한다.
ex) android:layout_marginTop="16dp"

(what)_(description\)_(etc)
- what: tv, et, etc..
- description: background, logo, etc...
- etc: top, bottom, left, right, orange, black, etc..

##### example
- main_background_black : MainActivity에서 사용될 검정색 배경의 스타일
- setting_logo_top : SettingActivty에서 위쪽에 위치한 로고의 스타일

#### Colors
palette와 color를 나눔 

palette -> (what)\_(where\)_(description)
- what : button, textview, etc..
- where : main, setting, etc..
- description : text, background, etc..

##### example
- button_main_text : MainActivity의 버튼에서 사용될 text의 색

color -> (color)_(detail)
- color : black, blue, orange, etc..
- detail : light, dark, etc..

##### example
- black_dark : 검정색중에 어두운 색

##### usage
```xml
// palette
<color name="button_main_text">@color/black_dark</color>

// color
<color name="black_dar">#000000</color>
```
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
- mvvm 사용시 model에 해당하는 클래스들
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
