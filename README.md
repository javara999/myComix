<h1 id="mycomix">myComix</h1>

<p><br></p>

<h2 id="phpcomicsviewer">PHP Comics Viewer</h2>

<p><br>
PHP7 이상 버전 및 php-zip, php-gd 설치된 웹서버 필요.</p>

<p>자신의 환경에 맞게 config.php 수정하라. 아래의 두가지 변수를 설정하면 된다.</p>

<pre style="background-color: #DDDDDD;"><code class="php language-php">$base_dir = "/myComix"; //만화가 있는 절대경로
$maxview = "18"; //한페이지에 보여줄 만화 갯수(폴더도 이 숫자만큼만 한 화면에서 보여진다)
</code></pre>

<p>아이폰 등 사파리 브라우저를 사용하는 경우, 뒤로가기/다른페이지로 이동 등을 눌러서는 자동북마크 저장이 되지 않는다.<br>
홈으로 돌아가는 등 사파리를 백그라운드로 돌리면 북마크가 저장되므로, 가급적 수동으로 북마크 저장하기를 권한다.</p>

<p><br></p>

<hr />

<p><br></p>

<h2 id="">대표적인 문제</h2>

<p><br></p>

<ul>
<li>북마크나 썸네일 생성이 안되는 경우, 권한을 확인한다.</li>
</ul>

<p>폴더에 쓰기권한이 있어야 썸네일을 생성할 수 있다. 대부분의 경우 707 내지 777을 주어야한다. <br />
<code>chmod -R 777 /만화책폴더</code> <br />
<code>chmod -R 777 /myComix폴더</code> <br />
<br></p>

<ul>
<li>rclone 이용시 반응이 많이 느리다.</li>
</ul>

<p>하위폴더가 있는 폴더와 없는 폴더를 구분하기 위해 디렉토리확인이 잦기 때문. <br />
썸네일 생성시에도 매우 느린데, 이 문제는 썸네일을 한번만 만들고나면 해결된다. <br />
폴더 이름 앞에 "rclone_" 을 붙이거나, 관리자페이지에서 is_remote설정으로 썸네일 생성과 하위디렉토리 확인 예외설정이 가능하다. <br />
<br></p>

<ul>
<li>화면에 아무것도 뜨지 않는다.</li>
</ul>

<p>이는 대부분 권한이 없거나, PHP모듈이 설치되어있지 않아 발생한다. <br />
<code>php-zip</code>, <code>php-gd</code> 모듈이 로드되고 있는지 확인하라.</p>

<p><br></p>

<hr />

<p><br></p>

<h2 id="-1">업데이트 정보</h2>

<p><br></p>

<ul>
<li>index 0.470 </li>
</ul>

<p>
PDF와 이미지 폴더의 제목줄이기 함수가 사용되지 않은 것 수정<br>
PDF파일의 확장자가 대문자가 섞인 경우 목록이 제대로 출력되지 않던 문제 수정
</p>


<p><br></p>

<ul>
<li>index 0.469 </li>
</ul>

<p>
PC의 경우 PDF파일을 지원, 휴대폰에서는 PDF를 다운로드 받도록 안내한다.<br>
리스트커버사용시 딜레이 발생은 광고차단앱을 끄면 해소된다.<br>
이미지 폴더의 경우, 다음파일 이전파일을 지원하지 않고 있던 것을 발견하여 수정했다.
</p>


<p><br></p>

<ul>
<li>index 0.468 </li>
</ul>

<p>
리스트커버이미지 사용설정시 목록 2단으로 출력.<br>
현재 리스트커버 이미지사용시 이유를 알 수 없는 딜레이가 심하게 발생하므로 사용하지 않는 것을 권장함.<br>
그 외, 몇화인지가 괄호 안에 들어간 경우에 대응하기 위해 제목을 줄이는 함수에 약간의 수정이 있었다. 
</p>


<p><br></p>

<ul>
<li>index 0.467 </li>
</ul>

<p>
UI수정 과정에서 발생한 일부 버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.466 </li>
</ul>

<p>
GIF지원
</p>


<p><br></p>

<ul>
<li>index 0.465 </li>
</ul>

<p>
지난 업데이트에서 커버이미지를 설정할 수 있도록 했으나 리스트 화면에서 높이가 달라지는 관계로 화면이 미려하지 못한 문제가 있었다.<br>
이 문제를 해결할 방법을 고민했으나 부트스트랩에 익숙하지 않아 당장 해결하기 어려우므로 목록에서 커버이미지를 썸네일 형태로 보여줄지 여부와 폴더커버이미지를 보여줄지 여부를 분리하여 설정하도록 했다.<br>
폴더커버를 사용으로 설정하면, 만화책 목록이 나오는 페이지에서 상단에 커버이미지를 출력하며, 리스트커버를 사용으로 설정하면, 디렉토리 목록의 제목 옆에 커버이미지가 작게 표시된다.<br>
뷰어에서 해당 파일의 첫번째 이미지를 대표이미지로 교체 설정할 수 있다.
</p>


<p><br></p>

<ul>
<li>index 0.46 </li>
</ul>

<p>
버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.46 </li>
</ul>

<p>
폴더 커버이미지 사용여부를 관리자페이지에서 선택할 수 있다. 설정하는 경우, 만화책파일이 있는 폴더의 [cover].jpg파일을 출력한다.<br>
만일 커버이미지 파일이 없는 경우, 만화 폴더에 진입시 자동으로 폴더의 첫번째 파일의 썸네일을 [cover].jpg 파일로 저장한다.<br>
이 커버이미지는 사용자가 교체할 수 있다. (파일명은 모두 소문자로 써야한다.)
</p>


<p><br></p>

<ul>
<li>index 0.459 </li>
</ul>

<p>
총 북마크 갯수, 총 자동저장 갯수를 관리자페이지에서 수정할 수 있도록 했다.
</p>


<p><br></p>

<ul>
<li>index 0.458 </li>
</ul>

<p>
뷰어에서 목록으로 나갈 때, 페이지 유지 안되던 문제 수정
</p>


<p><br></p>

<ul>
<li>index 0.457 </li>
</ul>

<p>
북마크 관련 버그 수정<br>
북마크 삭제시 북마크가 날아가버리는 치명적인 버그 수정<br>
자동저장된 북마크도 삭제할 수 있도록 수정
</p>


<p><br></p>

<ul>
<li>index 0.455 </li>
</ul>

<p>
뷰어를 떠날 때, 북마크가 자동저장된다(오류가능성이 있다). 자동북마크는 세개까지 저장하며, 삭제할 수 없다.(느낌표 표시)<br>
북마크 자동저장기능을 도입함과 동시에, 북마크 불러오기 화면을 조금 바꾸게 되었다.
</p>


<p><br></p>

<ul>
<li>index 0.454 </li>
</ul>

<p>
config.php파일의 설정을 관리자페이지에서 수정할 수 있도록 함
</p>


<p><br></p>

<ul>
<li>index 0.45 </li>
</ul>

<p>
압축되지 않은 만화책 폴더를 압축된 파일처럼 처리.<br>
폴더 01, 02, 05, 07 파일 03.zip, 04.zip, 06.zip 이 있는 경우, 01-02-03.zip-04.zip-05-06.zip-07 순서로 정렬한다.<br>
0.451에서 이미지폴더 못읽는 버그 바로 수정
</p>


<p><br></p>

<ul>
<li>index 0.446 </li>
</ul>

<p>
파일 정렬방식 개선
</p>


<p><br></p>

<ul>
<li>index 0.445 </li>
</ul>

<p>
PC에서 작은 이미지 여러개가 한줄로 나오는 문제 수정
</p>


<p><br></p>

<ul>
<li>index 0.444 </li>
</ul>

<p>
뷰어화면 상단 내비바 정리. 기어버튼 누르면 북마크와 밝기조절 메뉴가 뜨도록 수정함<br>
전체화면보기 모드의 북마크 동작 방식 수정. 전체화면 모드가 아닐 때에도 스크롤 위치 확인하여 북마크 정상동작
</p>


<p><br></p>

<ul>
<li>index 0.441 </li>
</ul>

<p>
뷰어 화면에서 화면 밝기를 위 아래 각 5단계로 조절할 수 있도록 수정.<br>
각 단계마다 대비는 10%(0.1)씩, 밝기는 4%(0.04)씩 각 조절된다.<br>
0.442 - 안드로이드 전체화면모드에서 밝기조절이 유지되지 않던 버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.434 </li>
</ul>

<p>
lazyload 개선
</p>


<p><br></p>

<ul>
<li>index 0.42 </li>
</ul>

<p>
뷰어에 밝기와 대비를 높여주는 버튼을 넣었다. 스캔만화를 볼 때 효과적이다.
</p>


<p><br></p>

<ul>
<li>index 0.411 </li>
</ul>

<p>
아주 미묘하게 속도 향상. 당분간은 기능추가 등의 업데이트보다 작동방식을 최적화 할 예정이다.
</p>


<p><br></p>

<ul>
<li>index 0.41 </li>
</ul>

<p>
update.php 파일이 변경되었다.<br>
기존에 업데이트의 정상처리 여부를 가져온 용량/기록한 용량으로 체크하였는데, 권한문제로 기록이 되지 않았음에도 기록한 용량은 정상으로 표시되고 있다는 문제가 있었다.<br>
그리하여 기록한 파일의 해시값과 가져온 파일의 해시값을 비교하는 방식으로 정상처리여부 확인방법을 바꿨다.<br>
혹시 업데이트를 눌렀을 때 해시값을 비교하는 화면이 나오지 않는다면 수동으로 새파일로 교체하라.
</p>


<p><br></p>

<ul>
<li>index 0.407 </li>
</ul>

<p>
사용자 그룹관리 안되던 것 수정. <br>
깃허브에 수정된 파일을 올렸다고 굳게 믿고 있었는데, 안올린걸 몇시간이 지나 알았다..
</p>


<p><br></p>

<ul>
<li>index 0.404 </li>
</ul>

<p>
bookmark.json파일과 user.php 파일을 src 라는 하위폴더를 만들어 그 아래에 위치하도록 수정.<br>
깃허브에 파일 올리다가 실수하는 일이 없도록 수정했다. 사용자는 그냥 사용하면 저절로 폴더를 만들고 파일을 이동한다.
</p>


<p><br></p>

<ul>
<li>index 0.402 </li>
</ul>

<p>
보안 향상. 기존사용자는 업데이트를 위해 사용자그룹수정을 한번 실행하라.
</p>


<p><br></p>

<ul>
<li>index 0.4 </li>
</ul>

<p>
북마크 저장시 읽던 모드를 함께 저장하여 다른 사람이 읽기모드 바꿔도 무관하게 수정(기존 북마크는 이용가능)<br>
파일 정렬방식 다소 수정하여 띄어쓰기와 언더바 제거하고 정렬하도록 수정.
</p>

<p><br></p>

<ul>
<li>index 0.395 </li>
</ul>

<p>급작스런 버그수정 및 파일명에 띄어쓰기대신 언더바(_)가 있는 경우 띄어쓰기가 있는 파일보다 먼저 정렬되는 문제 수정</p>

<p><br></p>

<ul>
<li>index 0.393 </li>
</ul>

<p>북마크 처리방식 변경, 이제 북마크버튼 누르면 북마크되는 페이지가 표시된다.</p>

<p><br></p>
<ul>
<li>index 0.392 </li>
</ul>

<p>폴더이름에 "."이 있어도 권한설정 가능</p>

<p><br></p>
<ul>
<li>index 0.39 </li>
</ul>

<p>로그인처리 세션으로 변경, 그 밖의 소소한 수정.</p>

<p><br></p>

<ul>
<li>index 0.36 </li>
</ul>

<p>admin페이지에서 버전업 정보를 읽을 수 있도록 함. admin페이지 변경.</p>

<p><br></p>

<ul>
<li>index 0.35 </li>
</ul>

<p>페이지이동 PC에서 드롭다운되던 것 위로 드롭업되도록 수정, 관리자페이지에서 폴더를 리모트지정할 수 있도록 수정</p>
