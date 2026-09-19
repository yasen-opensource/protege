# Protégé Desktop (汉化与国际化项目 / Localization & Internationalization Project)

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

Last updated at 2026-09-19

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