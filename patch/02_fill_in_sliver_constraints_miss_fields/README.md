## 资料
- 相关[PR](https://github.com/flutter/flutter/pull/143661)

## 使用

> 此补丁仅针对 Flutter 2.5.3 版本，其它版本请自行测试或根据上述 PR 的内容进行调整。

```shell
# 进入你的 flutter 目录，比如我用的是 fvm 下载的 2.5.3
# 记得将 cd 后面的路径换成你自己电脑上的~
cd /Users/lxf/fvm/versions/2.5.3

# 下载补丁
curl -O https://raw.githubusercontent.com/LinXunFeng/flutter_assets/main/patch/02_fill_in_sliver_constraints_miss_fields/patch_flutter_2_5_3.diff

# 应用补丁
git apply patch_flutter_2_5_3.diff
```

## 补丁内容
```diff
// packages/flutter/lib/src/rendering/sliver.dart

class SliverConstraints extends Constraints {
     assert(other.debugAssertIsValid());
     return other.axisDirection == axisDirection
         && other.growthDirection == growthDirection
+        && other.userScrollDirection == userScrollDirection
         && other.scrollOffset == scrollOffset
+        && other.precedingScrollExtent == precedingScrollExtent
         && other.overlap == overlap
         && other.remainingPaintExtent == remainingPaintExtent
         && other.crossAxisExtent == crossAxisExtent
```
