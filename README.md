<!-- ffxiv-tc-port 繁體中文說明開始 -->
# nmd(台服 fork)

C/C++ 單一標頭檔函式庫集合（上游 [Nomade040/nmd](https://github.com/Nomade040/nmd)，上游帳號現在改名為 gh-nomad）。Dalamud 本體的原生載入器 `Dalamud.Boot` 引用其中的 `nmd_assembly.h`（C89 的 x86 組譯／反組譯器）。

## 台服 fork 的目的

- 讓 Dalamud 本體的子模組網址指向本 org，建置不依賴上游 repo 是否還在、有沒有被改寫。

## 與上游的差異

- 移除上游的 GitHub Actions 工作流程（CodeQL、Coverity 掃描、assembly 建置／測試），避免在本 org 觸發。原始碼與上游相同。
- Dalamud 本體釘的是上游原本的版本，不含上面那顆移除 CI 的 commit。

## 誰在用它

- [Dalamud](https://github.com/ffxiv-tc-port/Dalamud)：子模組 `lib/Nomade040-nmd`，`Dalamud.Boot` 引用 `nmd_assembly.h`。

---

以下為上游原始 README，內容未經修改：

<!-- ffxiv-tc-port 繁體中文說明結束 -->
![Build nmd_assembly.h](https://github.com/Nomade040/nmd/workflows/Build%20nmd_assembly.h/badge.svg) ![Test nmd_assembly.h](https://github.com/Nomade040/nmd/workflows/Test%20nmd_assembly.h/badge.svg) [![Discord](https://img.shields.io/badge/chat-on%20Discord-green.svg)](https://discord.gg/VF4rVxA)
<a href="https://scan.coverity.com/projects/nomade040-nmd"><img alt="Coverity Scan Build Status" src="https://scan.coverity.com/projects/21763/badge.svg"/></a>

# nmd
set of single-header libraries for C/C++

# Notable
- C89 x86 assembler and disassembler: [nmd_assembly.h](nmd_assembly.h)
- C89 2D graphics library: [nmd_graphics.h](nmd_graphics.h)

# General information
 - **Each library's documentation is at the start of the file.**
 - **The end user should use the single-header libraries in the root directory.** The code in the folders(e.g. `/assembly`, `/graphics`) is for development only.

# Showcase(listed in no particular order)
 - [RTTI Finder Dumper](https://github.com/theluc4s/RTTI-Finder-Dumper)
 - [CVEAC-2020](https://github.com/thesecretclub/CVEAC-2020)

# Code guidelines
 - Ensure C89 compatibility.
 - Every identifier uses snake case.
 - Enums and macros are uppercase, every other identifier is lowercase.
 - Non-internal identifiers start with the `NMD_` prefix. e.g. `nmd_x86_decode()`.
 - Internal identifiers start with the `_NMD_` prefix. e.g. `_nmd_append_string()`.

Repository inspired by [nothings/stb](https://github.com/nothings/stb).
