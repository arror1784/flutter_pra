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

