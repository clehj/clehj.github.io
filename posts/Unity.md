---
title: 某梦想音游的逆向分析及心得总结
date: 2025-04-25
tags: [逆向分析, 游戏修改]
pinned: false
head:
  - - meta
    - name: description
      content: 本文介绍了某梦想音游的逆向分析过程，以及如何通过修改游戏判定逻辑来提升游戏体验。
  - - meta
    - name: keywords
      content: 逆向分析, 游戏修改, 音游, 判定逻辑
---

本文分享了作者对某梦想音游进行逆向分析的过程，以及通过修改游戏判定逻辑来提升游戏体验的心得。通过调整普通Note和滑条Note的判定，作者成功使游戏手感更接近另一款音游（Phigros），并提供了一些修改建议。

---

### 一、背景
作为一个音游玩家，作者希望调整某梦想音游的判定，使其手感更接近另一款游戏（Phigros），以提升游戏体验并满足联机AP的虚荣心。作者强调，过度修改会丧失游戏乐趣，因此不建议大改。

### 二、逆向分析过程

#### 1. 游戏包分析
- **游戏类型**：Unity游戏，使用il2cpp方式。
- **文件结构**：发现`libil2cpp.so`未加密，`global-metadata.dat`文件可用于进一步分析。

#### 2. 使用工具
- **il2cppdumper**：用于dump游戏的C#代码。
- **IDA Pro**：用于分析汇编代码。
- **AndroidKiller**：用于重新打包APK。

#### 3. 判定函数分析
- **搜索关键词**：通过搜索`Perfect`等关键词，找到`Note`的判定信息。
- **函数返回值**：判定函数返回`NoteResultType`类型，通过搜索相关函数，找到返回`Perfect`的函数。
- **修改判定逻辑**：
  - **普通Note**：将`MOV R1, #X`修改为`MOV R1, #4`，使普通Note直接判定为`Perfect`。
  - **滑条Note（SlideNote）**：分析`SlideNoteManager`的判定函数，避免提前判定导致的体验问题，将关键的`MOV R1, #X`修改为`MOV R1, #4`。

