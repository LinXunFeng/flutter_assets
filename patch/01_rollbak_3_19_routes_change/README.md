
- [相关文章](https://juejin.cn/post/7349124917378695180#heading-5)

```diff
// packages/flutter/lib/src/widgets/routes.dart

abstract class ModalRoute<T> extends TransitionRoute<T> with LocalHistoryRoute<T> {
  ...
  @override
  void didChangeNext(Route<dynamic>? nextRoute) {
    super.didChangeNext(nextRoute);
+    // changedInternalState();
  }

  @override
  void didPopNext(Route<dynamic> nextRoute) {
    super.didPopNext(nextRoute);
+    // changedInternalState();
  }
}
```
