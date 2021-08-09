# flutter_pra

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
# flutter_pra
예제 코드들

https://github.com/flutter/website/tree/master/examples


build() 함수는 리엑트에서 render() 함수와 비슷한 역활을 하는듯 하다.

Stateless Widget - 로드될때 한번만 그려지는 위젯 데이터 변경이 없는 위젯

Stateful Widget - 데이터 변경이 필요한 위젯


scaffold - 간편하게 화면을 그려주는 위젯 (앱 바, 바디 등등)

# stateful widget

두개의 클래스가 페어로 동작함
```class 
class test extends StatefulWidget {
  @override
  _testState createState() => _testState();
}

class _testState extends State<test> {
  @override
  Widget build(BuildContext context) {
    return Container(
      // setState({})
    );
  }
}
```
test에선 변경하지 않은 변수 선언 _testState 에서 변경가능한 변수 선언

setState 함수가 내부 변수를 변화 시키고 이를 프레임워크에 알려줘 다시 그릴수 있도록함

widget 함수는 현재 상태를 구성하는 임시 객체

CounterDisplay와 CounterIncrementor를 stateless widget 으로 구분하여 좀더 캡슐화를 진행할수 있음

# layout

layout 또한 위젯임

row - 양옆

column - 위 아래

기본 layout 종류 - Container, GridView, ListView, Stack
매테리얼 위젯 - Card, ListTile

# route

화면

Navigator 를 통해 페이지를 바꿈

```route
onPressed: () {
  Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => SecondRoute()),
  );
}

onPressed: () {
  Navigator.pop(context);
}
```

# named route

리액트 코드에서 주소로 화면을 전환하는것과 유사함
```
routes: {
      // When we navigate to the "/" route, build the FirstScreen Widget
      // "/" Route로 이동하면, FirstScreen 위젯을 생성합니다.
      '/': (context) => FirstScreen(),
      // "/second" route로 이동하면, SecondScreen 위젯을 생성합니다.
      '/second': (context) => SecondScreen(),
    },

Navigator.pushNamed(context, '/second');

```
위 코드로 라우트 등록
그 다음 코드로 이동

# file

path_provider 플러그인을 통해 파일을 읽고 쓸수 있음

getTemporaryDirectory(), getApplicationDocumentsDirectory() 등 여러 경로를 얻을수 있음

```쓰기
Future<File> writeCounter(int counter) async {
  final file = await _localFile;

  return file.writeAsString('$counter');
}
```
```읽기
Future<int> readCounter() async {
  try {
    final file = await _localFile;

    String contents = await file.readAsString();

    return int.parse(contents);
  } catch (e) {
    return 0;
  }
}

```

# shared_preferences

싱글톤의 형태로 key-value를 저장하고 읽을수 있음

```
SharedPreferences prefs = await SharedPreferences.getInstance();
_counter = (prefs.getInt('counter') ?? 0) + 1;
_counter = (prefs.getInt('counter') ?? 0);
```