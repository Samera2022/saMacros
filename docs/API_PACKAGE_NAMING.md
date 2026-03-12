# API 包文件命名说明

## 文件命名变更

### GitHub Release 下载文件
在GitHub Release页面，API包文件使用了更友好的命名格式：

| 旧命名格式                            | 新命名格式                            | 说明    |
|----------------------------------|----------------------------------|-------|
| `samacros-api-2.0.0.jar`         | `saMacros-API-2.0.0.jar`         | API主包 |
| `samacros-api-2.0.0-sources.jar` | `saMacros-API-2.0.0-sources.jar` | 源码包   |
| `samacros-api-2.0.0-javadoc.jar` | `saMacros-API-2.0.0-javadoc.jar` | 文档包   |

### Maven 仓库
在GitHub Packages的Maven仓库中，包名保持Maven标准命名：
- `samacros-api-2.0.0.jar`
- `samacros-api-2.0.0-sources.jar`
- `samacros-api-2.0.0-javadoc.jar`

## 对开发者的影响

### ✅ 无影响的场景

#### 1. 使用 Maven/Gradle 依赖
如果你通过Maven或Gradle的依赖管理系统引入API，**完全没有影响**：

**Maven:**
```xml
<dependency>
    <groupId>io.github.samera2022</groupId>
    <artifactId>samacros-api</artifactId>
    <version>2.0.0</version>
    <scope>provided</scope>
</dependency>
```

**Gradle:**
```gradle
dependencies {
    compileOnly 'io.github.samera2022:samacros-api:2.0.0'
}
```

Maven/Gradle使用的是坐标（groupId:artifactId:version），不依赖文件名。

#### 2. 已配置的 GitHub Packages 仓库
如果你已经配置了GitHub Packages仓库，继续使用上述依赖配置即可，无需任何修改。

### 📝 需要注意的场景

#### 手动下载并导入 IDE
如果你从GitHub Release页面手动下载jar包，然后添加到IDE项目中：

**变化**：
- 下载的文件名从 `samacros-api-2.0.0.jar` 变为 `saMacros-API-2.0.0.jar`
- 这只是文件名的改变，jar包内容完全相同

**影响**：
- ✅ IDE自动识别jar包，无需特殊配置
- ✅ 新命名更清晰，与应用包保持一致的命名风格
- ⚠️ 如果你的构建脚本硬编码了文件名，需要更新脚本

## 实现方式

### Workflow 实现
在GitHub Actions workflow中，我们添加了一个"Prepare API Packages for Release"步骤：

```yaml
- name: Prepare API Packages for Release
  shell: pwsh
  run: |
    $ver = "${{ env.APP_DISPLAY_VERSION }}"
    $apiDir = "samacros-api/target"
    $outputDir = "output/api"
    
    # 复制并重命名API jar文件
    Copy samacros-api-{version}.jar → saMacros-API-{version}.jar
    Copy samacros-api-{version}-sources.jar → saMacros-API-{version}-sources.jar
    Copy samacros-api-{version}-javadoc.jar → saMacros-API-{version}-javadoc.jar
```

### 为什么这样设计？

1. **GitHub Release的文件名** - 使用友好的命名（`saMacros-API-xxx.jar`）
   - 更直观易懂
   - 与主应用包命名风格一致
   - 便于用户识别和下载

2. **Maven仓库的文件名** - 保持标准命名（`samacros-api-xxx.jar`）
   - 符合Maven命名规范
   - 与artifactId保持一致
   - 不破坏现有的依赖管理

3. **实现方式** - 复制重命名而非修改POM
   - 不影响Maven构建流程
   - 不影响GitHub Packages发布
   - 只在最后一步为Release准备友好的文件名

## 迁移指南

### 如果你使用 Maven/Gradle
✅ **无需任何操作**，继续使用现有的依赖配置即可。

### 如果你手动下载jar包
1. 从GitHub Release页面下载新命名的jar包
2. 如果你的项目引用了旧文件名，有两个选择：
   - **推荐**：下载后重命名为你期望的文件名
   - 或者：更新项目配置以使用新文件名

### 如果你有自动化脚本
如果你的CI/CD脚本从GitHub Release下载API包，更新下载URL中的文件名：

**旧的**:
```bash
curl -L https://github.com/user/repo/releases/download/2.0.0/samacros-api-2.0.0.jar
```

**新的**:
```bash
curl -L https://github.com/user/repo/releases/download/2.0.0/saMacros-API-2.0.0.jar
```

## FAQ

### Q: 为什么要改文件名？
**A:** 为了让下载文件的命名更直观、更一致。`saMacros-API` 比 `samacros-api` 更容易识别，且与主应用包 `saMacros-{version}.jar` 保持一致的风格。

### Q: 我能继续使用旧的文件名吗？
**A:** 如果你从GitHub Packages（Maven仓库）获取依赖，文件名仍然是标准的Maven格式。只有从GitHub Release页面手动下载时才会看到新命名。

### Q: 这会破坏现有的Maven依赖吗？
**A:** 不会。Maven依赖使用的是坐标（groupId:artifactId:version），与jar文件的实际文件名无关。

### Q: javadoc和sources包也改名了吗？
**A:** 是的，三个包都统一使用了新的命名格式：
- `saMacros-API-{version}.jar`
- `saMacros-API-{version}-sources.jar`
- `saMacros-API-{version}-javadoc.jar`

### Q: 如果我需要特定的文件名怎么办？
**A:** 下载后可以随意重命名jar文件，jar包的内容不受文件名影响。

## 总结

✅ **对大多数开发者无影响** - Maven/Gradle用户无需任何改动

✅ **更好的用户体验** - 手动下载的用户获得更清晰的文件名

✅ **向后兼容** - Maven仓库保持标准命名，不破坏现有依赖

✅ **实现简洁** - 只在发布阶段重命名，不影响构建流程

