## 资料
- [相关文章](https://juejin.cn/post/7349124917378695180#heading-5)

## 使用
```shell
# 进入你的 flutter 目录，比如我用的是 fvm 下载的 3.19.3
# 记得将 cd 后面的路径换成你自己电脑上的~
cd /Users/lxf/fvm/versions/3.19.3

# 下载补丁
curl -O https://raw.githubusercontent.com/LinXunFeng/flutter_assets/main/patch/01_rollbak_3_19_routes_change/0001-Roll-back-changes-to-routes.dart.patch

# 应用补丁
git apply 0001-Roll-back-changes-to-routes.dart.patch
```

## 补丁内容
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
