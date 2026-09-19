# Protégé 汉化与多语言贡献指南 / Protégé Localization & Multilingual Contribution Guide / Guide de Contribution à la Localisation de Protégé

[中文](#中文版本) | [English](#english-version) | [Français](#version-française)

---

## 中文版本

欢迎来到 Protégé 国际化（多语言）开源贡献指南！本文档旨在为全球有志于参与 Protégé 多语言支持（如中文、法语等）的朋友提供清晰、标准的操作流程。

### 1. 多语言架构与 Locale 选择机制

在 Protégé 的 OSGi 模块化架构中，国际化（i18n）资源统一在 **`protege-common`** 模块中集中管理。

* **核心优势**：`protege-common` 是底层公共依赖，所有上层功能插件均可安全地共享和加载该模块中的资源。
* **Locale 选择机制**：Java 的 `ResourceBundle` 根据当前的运行 `Locale` 自动匹配对应的后缀文件。
  * 默认/英文：`Messages.properties`
  * 中文（简体）：`Messages_zh_CN.properties`
  * 法语：`Messages_fr_FR.properties`

* **核心资源路径**：
  * `protege-common/src/main/resources/i18n/Messages.properties` (Default / English)
  * `protege-common/src/main/resources/i18n/Messages_zh_CN.properties` (Chinese)
  * `protege-common/src/main/resources/i18n/Messages_fr_FR.properties` (French)

### 2. 代码层面的适配方法

在各功能模块的代码中，如需对 UI 元素进行国际化，请统一使用 `I18n.get()` 方法：

```java
// 通过 I18n 动态获取对应语言环境的文本
AbstractOWLTreeAction<OWLClass> addSubClassAction = new AbstractOWLTreeAction<OWLClass>(I18n.get("action.add.subclass"), ...);
```

### 3. 在属性文件中添加多语言词条

根据您想要贡献的语言，修改对应的 `.properties` 文件：

* **中文 (`Messages_zh_CN.properties`)**：
  ```properties
  action.add.subclass = 添加子类
  ```
* **法语 (`Messages_fr_FR.properties`)**：
  ```properties
  action.add.subclass = Ajouter une sous-classe
  ```

### 4. 编译、打包与运行调试指南

#### 4.1 执行 Maven 全量编译安装
```powershell
mvn clean install -DskipTests=true
```

#### 4.2 指定 Locale 运行参数
在启动或 IDE 运行配置（VM options）中，通过 JVM 参数指定您要测试的目标语言环境：
* **测试中文环境**：`-Duser.language=zh -Duser.region=CN`
* **测试法语环境**：`-Duser.language=fr -Duser.region=FR`

### 5. 提交 Pull Request 贡献指南

1. **Fork 本仓库** 并创建您的特性分支。
2. 提交对 `protege-common` 中相应 `Messages_*.properties` 文件的修改。
3. 发起 **Pull Request**，并在描述中附上对应语言的 UI 运行截图。

---

## English Version

Welcome to the Protégé internationalization (multilingual) contribution guide! This guide outlines the standard workflow for contributing translations (such as Chinese, French, etc.) to the Protégé desktop application.

### 1. Multilingual Architecture & Locale Selection Mechanism

Internationalization (i18n) resources are centralized within the **`protege-common`** module.

* **Locale Selection Mechanism:** Java's `ResourceBundle` automatically matches resource files based on the active runtime `Locale`:
  * Default / English: `Messages.properties`
  * Chinese (Simplified): `Messages_zh_CN.properties`
  * French: `Messages_fr_FR.properties`

* **Resource File Paths:**
  * `protege-common/src/main/resources/i18n/Messages.properties`
  * `protege-common/src/main/resources/i18n/Messages_zh_CN.properties`
  * `protege-common/src/main/resources/i18n/Messages_fr_FR.properties`

### 2. Code-Level Implementation

Use the `I18n.get()` utility for dynamic string lookup:

```java
AbstractOWLTreeAction<OWLClass> addSubClassAction = new AbstractOWLTreeAction<OWLClass>(I18n.get("action.add.subclass"), ...);
```

### 3. Adding Multilingual Entries

* **French (`Messages_fr_FR.properties`)**:
  ```properties
  action.add.subclass = Ajouter une sous-classe
  ```

### 4. Build, Package & Testing with Locales

#### 4.1 Maven Build
```powershell
mvn clean install -DskipTests=true
```

#### 4.2 Setting Runtime Locale via JVM Arguments
* For Chinese: `-Duser.language=zh -Duser.region=CN`
* For French: `-Duser.language=fr -Duser.region=FR`

### 5. Submitting a Pull Request
Submit your PR with the updated `.properties` files and include verification screenshots.

---

## Version Française

Bienvenue dans le guide de contribution à l'internationalisation (multilingue) de Protégé ! Ce guide décrit le flux de travail standard pour contribuer aux traductions (telles que le chinois, le français, etc.).

### 1. Architecture Multilingue & Mécanisme de Sélection de la Locale

Les ressources i18n sont centralisées dans le module **`protege-common`**.

* **Mécanisme de sélection :** Le `ResourceBundle` de Java charge automatiquement le fichier approprié en fonction de la `Locale` active :
  * Par défaut / Anglais : `Messages.properties`
  * Chinois : `Messages_zh_CN.properties`
  * Français : `Messages_fr_FR.properties`

### 2. Utilisation dans le Code

```java
AbstractOWLTreeAction<OWLClass> addSubClassAction = new AbstractOWLTreeAction<OWLClass>(I18n.get("action.add.subclass"), ...);
```

### 3. Ajout de Traductions

* **Français (`Messages_fr_FR.properties`)** :
  ```properties
  action.add.subclass = Ajouter une sous-classe
  ```

### 4. Compilation et Test avec la Locale

#### 4.1 Compilation Maven
```powershell
mvn clean install -DskipTests=true
```

#### 4.2 Configuration de la Locale via les arguments JVM
* Pour le français : `-Duser.language=fr -Duser.region=FR`

### 5. Soumission d'une Pull Request
Soumettez votre PR avec les fichiers de propriétés mis à jour et des captures d'écran.