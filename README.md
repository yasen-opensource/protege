# Protégé Desktop (汉化与国际化项目 / Localization & Internationalization Project)

> 📋 [参与 2 分钟用户调研](https://github.com/yasen-opensource/protege/discussions/X) · 你的反馈决定翻译优先级

> **🇨🇳 欢迎全球社区的有志之士共同参与！** 
> 请参阅我们的详细贡献指南：[👉 国际化与汉化贡献指南 (Localization Contribution Guide)](docs/localization_contribution_guide.md/#中文版本) 以了解如何通过 Pull Request 贡献你的本地化语言包。
> 
> **🇬🇧 Welcome passionate contributors from the global community!** 
> Please refer to our detailed contribution guide: [👉 Localization Contribution Guide](docs/localization_contribution_guide.md/#english-version) to learn how to contribute your localization language pack via Pull Request.
> 
> **🇫🇷 Bienvenue aux contributeurs passionnés de la communauté mondiale !** 
> Veuillez consulter notre guide de contribution détaillé : [👉 Guide de Contribution à la Localisation](docs/localization_contribution_guide.md/#version-française) pour savoir comment contribuer à votre pack de langue via une Pull Request.

---

## 🇨🇳 中文汉化计划 (Chinese Localization)

本项目分支正致力于开展 **Protégé Desktop 的全面国际化与中文汉化** 工作，方便全球华语开发者和本体工程学习者使用。

### 📌 汉化路线图
1. **核心模块划分**：
   - `Protégé-common`：集中维护多语言字典（如 `Messages_zh_CN.properties`, `Messages_fr_FR.properties` 等）。
   - 各功能插件模块：通过底层公共类与类加载器统一加载。
2. **实施方案**：
   - 采用标准 Java 国际化 (`ResourceBundle` / `.properties`) 属性文件与动态 Locale 选择机制。
   - 确保在 Maven 编译打包及 Swing 运行时中完美支持多国语言字符。

---

## 🇬🇧 English Localization & Internationalization Plan

This project branch is dedicated to expanding **Protégé Desktop with comprehensive internationalization and localization (i18n)** support, making it easier for global developers and ontology engineers to use in their native languages.

### 📌 Localization Roadmap
1. **Core Module Architecture**:
   - `Protégé-common`: Centrally manages multi-language properties files (e.g., `Messages_zh_CN.properties`, `Messages_fr_FR.properties`).
   - Feature plugins load resources dynamically via shared underlying loaders.
2. **Implementation**:
   - Uses standard Java Internationalization (`ResourceBundle` / `.properties`) with dynamic Locale selection.

---

## 🇫🇷 Plan de Localisation et d'Internationalisation (Français)

Cette branche du projet se consacre à l'expansion de **Protégé Desktop avec un support complet d'internationalisation et de localisation (i18n)**, facilitant son utilisation par les développeurs et ingénieurs ontologiques du monde entier dans leur langue maternelle.

### 📌 Feuille de Route de Localisation
1. **Architecture du Module Central**:
   - `Protégé-common`: Gère de manière centralisée les dictionnaires multilingues.
2. **Mise en Œuvre**:
   - Utilise l'internationalisation standard de Java (`ResourceBundle`) avec sélection dynamique de la Locale.

---

## ⚖️ 与其他 Protégé 汉化版本的区别 (Comparison with Other Chinese Versions)

如果你在搜索引擎或下载站找到了其他"Protégé 汉化版"，选择前请先看下表：

| 维度 | 本仓库 (yasen-opensource/protege) | NLPIR 汉化版 (2018) | 下载站"5.5 汉化绿色包" |
|---|---|---|---|
| **基线版本** | 跟随 Protégé 最新发布【当前基线，如 5.6.9】 | Protégé 5.0 beta（2018 年），已落后多个大版本 | 来源混杂，多数未标注基线 |
| **实现方式** | 标准 `ResourceBundle` 属性文件，走官方 i18n 框架，**不改变任何程序逻辑** | 修改版安装包 | 多为重新打包的安装包/绿色版，打包过程不透明 |
| **维护状态** | 活跃维护，跟随上游版本更新 | 已停止更新（最后发布于 2018 年） | 无人维护，版本固定 |
| **安全性** | 源码公开、可审计；所有翻译文件可逐行 diff 核对 | 完整安装包需自行校验来源 | ⚠️ 无法验证打包者是否改动了二进制或捆绑了额外程序，**不建议在生产/科研环境使用** |
| **兼容性** | 可与其他官方插件共存，升级 Protégé 不丢翻译 | 仅兼容当时的 5.0 beta | 换机/升级后通常失效 |
| **社区归属** | 开放贡献（见 [贡献指南](docs/localization_contribution_guide.md)），目标是进入官方上游 | 团队项目，不接受外部贡献 | 无社区 |

### 💡 一句话选择建议

- 想要**持续更新、可审计、能回馈上游**的中文体验 → 用本仓库的翻译资源包；
- 只是临时尝鲜、且环境隔离 → 旧版汉化包也不是不能用，但请知悉它停留在 2018 年的代码基线上；
- 从下载站拿到来路不明的"汉化绿色版" → 谨慎对待，本体文件通常承载科研/生产数据，不值得为省一步安装冒供应链风险。

> 🔍 **如何自己验证一个汉化包是否可信？**
> 1. 翻译资源应当是 `.properties` 文本文件，而不是替换掉的 `.jar` / `.class` / `.exe`；
> 2. 对照本仓库同名文件，用 `diff` 即可看出改了什么；
> 3. 安装包的数字签名/哈希应与官方发布一致，不一致即说明被重新打包过。

---

Last updated at 2026-09-25

---

Below is the original README:

# Protégé Desktop

[Protégé](https://Protégé.stanford.edu) is a free, open-source ontology editor that supports the latest [OWL 2.0 standard](http://www.w3.org/TR/owl2-overview/). Protégé has a pluggable architecture, and many [plugins](https://Protégéwiki.stanford.edu/wiki/Protégé_Plugin_Library) for different functionalities are available.

To read more about **Protégé's features**, please visit the Protégé [home page](https://Protégé.stanford.edu).

The latest version of Protégé can be [downloaded](https://Protégé.stanford.edu/software.php#desktop-Protégé) from the Protégé website, or from [github](https://github.com/Protégéproject/Protégé-distribution/releases).

If you would like to contribute to the Protégé Project please see our [contributing guide](https://github.com/Protégéproject/Protégé/blob/master/CONTRIBUTING.md)

The [Developer Documentation](https://github.com/Protégéproject/Protégé/wiki/Developer-Documentation) may be found on the wiki.

**Looking for support?** Please ask questions on the [Protégé-user](https://Protégé.stanford.edu/support.php) or [Protégé-dev](https://Protégé.stanford.edu/support.php) mailing lists. If you found a bug or would like to request a feature, you may also use [this issue tracker](https://github.com/Protégéproject/Protégé/issues).

Protégé is released under the [BSD 2-clause license](https://raw.githubusercontent.com/Protégéproject/Protégé/master/license.txt).

Instructions for [building from source](https://github.com/Protégéproject/Protégé/wiki/Building-from-Source) are available on the the wiki.