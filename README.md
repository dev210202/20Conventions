# 20Conventions
안드로이드 개발시 내가 사용하는 컨벤션들에 대해 정리합니다.(Kotlin 기준)

## Project Setting

### Naming
- 카멜 표기법 사용
- 함수 이름은 일반적으로 동사
- 변수 이름은 일반적으로 명사

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
what에 사용하는 UI 컴포넌트는 줄임말을 사용한다. 
- what : tv(textview), btn(button), etc...
- where : main, setting, etc..
- description : result, name, etc...

##### example
- tv_main_result : MainActivity의 결과값을 보여주는 textview

#### Strings

\(where)\_(what)_(description\)  
- where : main, setting, etc..
- what : tv, btn, etc..
- description : title, content, etc...

##### example
- main_title : MainActivity의 title에 사용
- all_content : 모든 뷰에서 content에 사용

#### Drawables

(what)\_(where)\_(description\)_(size)\_(color)
- what: background, icon, etc..
- where : main, setting, all, etc...
- description : info, alert, etc...
- size : 24, 36, etc...
- color: black, white, etc...

##### example
- main_info_24 : MainActivity에서 사용될 24dp 크기의 info 이미지
- all_alert_36_black : 모든 뷰에서 사용될 36dp 크기의 alert 이미지의 black

#### Styles
스타일에서 크기와 공백같이 디자인을 보면서 작업해야하는 것들은 아이템에서 제외한다.
ex) android:layout_marginTop="16dp"

(what)_(description\)_(etc)
- what: tv, et, etc..
- description: background, logo, etc...
- etc: 색, 위치 등 -> top, bottom, left, right, orange, black, etc..

##### example
- main_background_black : MainActivity에서 사용될 검정색 배경의 스타일
- setting_logo_top : SettingActivty에서 위쪽에 위치한 로고의 스타일

#### Colors
Material 혹은 디자인 시스템을 기반으로 네이밍

(color\)_(brightness)
- color: black, white, etc..
- brightness: 10, 20, 200, 300, etc..
