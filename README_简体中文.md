# <img src="https://static.cdnlogo.com/logos/f/26/firefox-preview.svg" width="32" height="32" style="vertical-align: middle;"> FlexFox（简体中文版）

<div>
 <a href='https://www.mozilla.org'><img src="https://img.shields.io/badge/Last%20tested%20Firefox-v140-orange?logo=firefox"></a>
 <a href='https://github.com/yuuqilin/FlexFox/commits/main/'><img src="https://img.shields.io/github/last-commit/yuuqilin/FlexFox/main"></a>
 <a href='https://github.com/yuuqilin/FlexFox/commits/Beta/'><img src="https://img.shields.io/github/last-commit/yuuqilin/FlexFox/Beta?label=last%20Nightly%20commit&color=purple"></a>
 <a href='https://github.com/yuuqilin/FlexFox/stargazers'><img src='https://img.shields.io/github/stars/yuuqilin/FlexFox?style=social'></a>
</div>

<br>

一款灵活可定制的 Firefox 主题，灵感来自 [VerticalFox](https://github.com/christorange/VerticalFox)、[EdgyArc-fr](https://github.com/artsyfriedchicken/EdgyArc-fr)、[Edge-Frfox](https://github.com/bmFtZQ/edge-frfox)、[ArcWTF](https://github.com/KiKaraage/ArcWTF)、[shimmer](https://github.com/nuclearcodecat/shimmer) 和 [firefox-csshacks](https://github.com/MrOtherGuy/firefox-csshacks)。FlexFox 提供多种功能选项以增强浏览体验。

![FlexFox Dark-Light Theme](./assets/FlexFox-light-dark.webp) 

## 🆕 更新内容

**v3.1.7**
- 修复了原生垂直选项卡展开时动画延迟的问题，现在文字标签的显示时机与选项卡宽度的变化同步。
- 优化了 PowerShell 安装脚本中的下载大小预估，使其更接近实际文件大小。

<details>

<summary>💬 <b>历史更新</b></summary>

**v3.1.6**
- 用户现在可以在 `content` 文档夹中创建 `uc-custom-content.css` 文档，用于定义网页内容的自定义样式。该文档会在 `userContent.css` 的最后被导入，因此能覆盖之前的样式。此外，它并不包含在 FlexFox 项目本体中，所以在更新 FlexFox 时不会被覆盖，内容会被完整保留。
- 重新调整了项目的文档结构，以简化通过 Git 克隆方式进行更新的流程。这一改动也为未来即将推出的安装与更新脚本做好了准备。

**v3.1.5**  
- 在启用新版侧边栏时减少了不必要的样式规则应用。 
- 修复了旧版侧边栏中，鼠标悬停在切换器菜单上时导致侧边栏折叠的问题。  
_注：这个 Bug 已经存在多年，由于影响较小且修复它会带来一些性能损耗，因此之前一直没有处理。现在 FlexFox 已经完全迁移到新版侧边栏，这次修复也为旧版划下一个完美的句号。_

**v3.1.4**  
- 微调了查找栏的显示位置。

**v3.1.3**  
- 修复了当查找栏位于右下角时，无法显示匹配结果数量的问题。

**v3.1.2**

- Findbar（查找栏）的默认位置从“上方中央偏左”更改为“右上角”。添加字符串类型的选项 `uc.flex.findbar-position`：
  - 设置为 `"top-center-left"` 或 `"0"` 时，Findbar 将显示在之前的默认位置（上方中央偏左）。
  - 设置为 `"top-right"` 或 `"1"` 时，将显示在新的默认位置（右上角）。
  - 设置为 `"bottom-right"` 或 `"2"` 时，将回到 Firefox 原本的默认位置（右下角）。
- 移除了 `--uc-findbar-top` 变量，Findbar 位置现在通过 `--uc-findbar-x-position` 和 `--uc-findbar-y-position` 两个变量进行控制，用户可以自由调整位置。
- 移除了侧边栏最小宽度的硬编码限制，最小宽度现在完全由用户自定义变量 `--uc-sidebar-width` 控制。

**v3.1.1**

- 将 Sidebery 折叠/展开的默认动画类型改为 `ease-in-out`，与 Firefox 原生垂直选项卡的效果一致（之前 Sidebery 使用的是 `linear`）。用户可以在 `uc-user-settings.css` 中通过设置 `--uc-autohide-transition-type` 变量自定义动画效果。
- 现在 Firefox 原生垂直选项卡的动画类型也可以通过 `--uc-autohide-transition-type` 变量进行修改。
- 修复了在未最大化窗口状态下启用新版侧边栏并开启 `uc.flex.fully-hide-sidebery` 选项时，窗口边缘出现多余空白并导致 Sidebery 高度显示异常的问题。

随着本次更新完成了对原生垂直选项卡与 `uc.flex.fully-hide-sidebery` 的兼容性处理，FlexFox v3.1.1 已实现与旧版水平选项卡模式完全一致的功能，用户可以无缝迁移使用。

**v3.1.0**
- 刷新了 `uc-variables.css` 的结构。常用且可自定义的变量现在集中放在文档开头，并配有清淅的说明。
- 重构了 FlexFox 对工具栏背景颜色的覆盖逻辑。此次更新应彻底修复在启用主题时背景图错位、透明度异常，以及窗口非激活状态下显示不正确的问题。
- 优化了垂直选项卡在展开和折叠时的动画流畅度。
- 调整了导航栏的位置，使其按钮更好地与垂直选项卡对齐。
- 切换 `uc.flex.allow-addons-to-change-toolbar-color` 时不再导致侧边栏上下晃动。

**v3.0.7**
- 修复在使用 Firefox 原生标签页（包括水平和垂直选项）时，当前激活标签页背景高亮显示异常的问题。  
- 修复在启用菜单栏并将书签栏设置为自动隐藏的情况下，主题背景图在导航栏与书签栏之间出现错位的问题。  
- 修复 Firefox 窗口处于非活动状态时，菜单栏的背景颜色未能正确变化的问题。

**3.0.6**
- 将多个引入的样式更新为最新版本。  
  - 为查找栏失去焦点后自动关闭添加了动画效果。  
  - 优化了在打开面板时导航栏保持显示的行为。  
- 为避免潜在错误和调试困难，修正了一处不符合标准的语法写法。

**v3.0.5**  
- 修复启用 `uc.flex.allow-addons-to-change-toolbar-color` 时，侧边栏彩带位置偏移的问题。

**v3.0.4**  
- 修复了一个打字错误。  
- 修复了在启用新版侧边栏的 `隐藏标签页和侧栏` 选项时，书签工具栏的水平偏移问题。

**v3.0.3**  
- 修复启用 `uc.flex.fully-hide-sidebery` 或处于全屏模式时，侧边栏彩带无法展开的问题，同时也修复了在相同条件下彩带与 Sidebery 动画不同步的问题。  
- 修复主题颜色问题，解决菜单栏背景色与下方导航工具栏不一致的情况。

**v3.0.2**  
- 修复了新版侧边栏放在右侧时展开与折叠的动画效果问题。  
- 现在原生垂直选项卡使用与 Sidebery 相同的展开/折叠速度。你可以使用 `uc.flex.sidebery-fast-hover-expand` 或 `uc.flex.sidebery-slow-hover-expand` 选项来加快或减慢速度，或者直接修改 `--uc-autohide-*` 和 `--uc-hover-*` 变量，设定你喜欢的动画速度。

**v3.0.1**
- 修复同时启用 `uc.flex.disable-bookmarks-autohide` 和新版侧边栏时，侧边栏彩带位置显示错误的问题。  
- 修复同时启用 `uc.flex.disable-sidebery-autohide` 和新版侧边栏时，侧边栏彩带宽度显示异常的问题。

**v3.0.0**
- 将 Firefox 原生垂直选项卡与 Sidebery 整合。  
  - 当 Sidebery 启用时，原生垂直选项卡会自动隐藏。新版侧边栏会折叠为 Sidebery 顶部的一条细长彩色条带。将鼠标悬停在彩带上可以显示侧边栏工具按钮。  
  - 当 Sidebery 被禁用（例如启用其他侧边栏工具或扩展）时，则会显示原生垂直选项卡。  
  - 使用 F1 键快速切换 Sidebery 时，由于 Sidebery 与原生垂直选项卡共享相同的宽度与布局，界面切换看起来非常流畅自然。  
  - 支持自动适配左右两侧的侧边栏布局，可根据 UI 位置灵活调整。  
- 添加数值选项 `uc.flex.max-visible-vertical-pinned-tabs`（可设范围：4–6）。此选项用于控制原生垂直选项卡面板中，每一列在垂直方向上最多可显示的钉选标签页数量。默认值为 4。若垂直排列的钉选标签页超过此值，将出现滚动条。

> [!IMPORTANT]
> 原生垂直选项卡支持自动折叠和鼠标悬停展开。可通过`展开侧边栏`按钮（Alt+Ctrl+Z）启用该功能。 
> <details>
> <summary>🖼️ <b>原生垂直选项卡自动折叠效果示例</b></summary>
> <p>原生垂直选项卡展开，<code>uc.flex.show-pin-tabs-separator-in-expanded-state</code> 为 false</p>
> <img src="./assets/vertical-tabs-expanded.webp" alt="vertical-tabs-expanded" width="50%" />
> <p>原生垂直选项卡折叠，<code>uc.flex.show-pin-tabs-separator-in-expanded-state</code> 为 false</p>
> <img src="./assets/vertical-tabs-collapsed.webp" alt="vertical-tabs-collapsed" width="50%" />
> </details>  

> [!TIP]
> **用户现在可以在 `components` 文档夹中创建 `uc-user-settings.css` 文档，以自定义 FlexFox 的样式。该文档会在 FlexFox 之后加载，并覆盖其样式，因此即使将来更新，用户的自定义修改也会保留。**  
> **详细步骤请参见：[User-Customizable Styles (`uc-user-settings.css`)](https://github.com/yuuqilin/FlexFox?tab=readme-ov-file#-user-customizable-styles-uc-user-settingscss)**

**v2.1.2**  
- 修复了在启用原生垂直选项卡并将 `uc.flex.disable-bookmarks-autohide` 设为 true 时，书签栏出现偏移的问题。  
- 修复了全屏模式下地址栏过渡动画延迟的问题。  

**v2.1.1**  
- 修复了 Firefox v137 中原生垂直选项卡背景变成透明的问题。  
- 添加 `uc.flex.disable-native-vertical-tabs-autohide` 选项，设为 true 时可关闭自动折叠原生垂直选项卡的功能。 

**v2.1.0**  
- 原生垂直选项卡支持自动折叠和鼠标悬停展开。可通过`展开侧边栏`按钮（Alt+Ctrl+Z）启用该功能。  
- 添加选项 `uc.flex.show-pin-tabs-separator-in-expanded-state`，可在使用原生垂直选项卡时，为固定标签页面板显示分隔线。  
- 修复启用原生垂直选项卡时无法应用主题，以及自动隐藏书签栏时主题背景图损坏的问题。  
- **现在用户可以在 `components` 文档夹中创建 `uc-user-settings.css`，用于自定义 FlexFox 的样式。该文档在 FlexFox 之后加载，因此即使 FlexFox 更新，也不会影响用户的自定义修改。**  
- 原生垂直选项卡与 Sidebery 尚未整合，当前只能二选一使用。  

侧边栏工具按钮的设计借鉴了 @Godiesc 的 [firefox-gx](https://github.com/Godiesc/firefox-gx)。感谢 @Godiesc 提供了这样出色的实现。  

**v2.0.3**  
- 添加了 `sidebar-positionend` 属性，以兼容 Firefox v138+，并对新版侧边栏的宽度做了轻微调整。  

**v2.0.2**  
- 更新 `@media` 规则以兼容 Firefox v137+。  

**v2.0.1**  
- 窗口未最大化时，在顶部添加了1px的边框。  
- 清理样式，移除了不必要的规则和注释。  

**v2.0.0**:  
- 核心功能完全重写，速度比旧版提升28倍。  
   - 启动后首次打开右键菜单的时间为13ms，与Firefox原生主题完全一致。  
   - 在205个标签页的情况下，打开“列出所有标签页”菜单的时间为26ms，也与原生主题无差异。  
   - 换句话说，经过重写后，v2.0.0对Firefox的性能几乎完全没有影响。  
- 修复了Nightly (v135)的地址栏和原生垂直标签页的显示问题。 

<details>
<summary>🖼️ <b>新功能的展示效果</b></summary>
<p>启用深色主题和<code>uc.flex.disable-sidebery-autohide</code>的新FlexFox：</p>
<img src="./assets/disable-sidebery-autohide.webp" alt="disable-sidebery-autohide" width="98%" />
<p>与<code>uc.flex.fully-hide-toolbox</code>结合使用的效果：</p>
<img src="./assets/disable-sidebery-autohide-with-fully-hide-toolbox.webp" alt="disable-sidebery-autohide-with-fully-hide-toolbox" width="98%" />
</details>

**v1.1.1**:
- 修正了应用主题时查找栏背景颜色显示异常的问题。

**v1.1.0**:
- 修复启用主题背景图时，悬停展开书签工具栏时背景图断裂的问题。
- 调整了缩放级别文本的亮度。
- 修正了 Nightly (v135) 版本中窗口控制按钮位置的问题，解决了 `tabsintitlebar` 被弃用后与 `customtitlebar` 的兼容性问题。
- 添加选项 `uc.flex.disable-sidebery-autohide`，可停用 Sidebery 自动折叠。

> [!IMPORTANT]  
> 在导入 v1.1.0 版的 `sidebery-styles.json` 之前，请先清除旧版样式。打开 Sidebery 设置（齿轮图标）> `Styles editor` > 将 `Sidebar` 和 `Group page` 两个页面下的样式全部清除后，再导入新版样式。  
> 导入 `sidebery-settings.json` 时可能会导致面板数据丢失，请务必先使用快照功能备份面板数据。

**v1.0.4**:
- 当网页缩放比例不是默认值时，固定显示缩放比例图标。
- 当网页已加书签时，固定显示书签星标图标。  
   <img src="./assets/urlbar-star-light.webp" alt="urlbar-star-light" width="380" />  
   <img src="./assets/urlbar-star-dark.webp" alt="urlbar-star-dar" width="380" />

**v1.0.3**:
- 优化了开启 `uc.flex.allow-addons-to-change-toolbar-color` 选项时的性能，相较于v1.0.2速度提升了1.4倍。

**v1.0.2**:
- 改善地址栏切换器和图标的显示效果。
- 添加选项 `uc.flex.allow-addons-to-change-toolbar-color`，允许主题和扩展修改工具栏背景图片和颜色。  
   <img src="./assets/allow-addons-to-change-toolbar-color.webp" alt="allow-addons-to-change-toolbar-color" width="98%" />

**v1.0.1**:  
- 修复了URL栏追踪保护图标无法隐藏的问题。
- 添加了`uc-pdf.js.css`。
- 添加了LICENSE文档。

**v1.0.0**:
- 性能大幅提升，相比之前的版本运行速度提高了 **100 倍**。打开右键菜单的延迟仅增加 **16ms**，与默认界面几乎无异。

> [!IMPORTANT]
> 如果您在 Firefox v133 之前的版本使用过 FlexFox，更新前请重置设置：在 `about:config` 中搜索 `uc.flex.` 并删除所有相关条目。

</details>

## ✨ 功能亮点

### 🌟 极简设计

> *最大化你的网页视野。*

- 工具栏和侧边栏可独立折叠或隐藏。  
  > *你可以自由选择隐藏侧边栏或导航栏，甚至两者都隐藏，根据自己的使用习惯灵活组合界面。*

- 隐藏所有界面时，仅显示网页内容。  
  > *无需进入全屏，就能获得近乎全屏的阅读体验；也能创建像便签一样的极简窗口，贴在桌面上阅读或对比多个网页。*

### 🌟 稳定不跳动

> *界面切换平稳，页面位置不乱动。*

- 展开折叠的界面元素时不会推动网页内容。  
  > *工具栏和侧边栏会悬浮显示，而不是挤压页面，从而避免页面发生跳动。*

- 展开后的标签页保持原位。  
  > *垂直选项卡展开时，会在原位横向伸展，垂直位置不变，鼠标无需重新定位目标标签页。*

### 🌟 自适应布局

> *根据你的使用习惯自动调整。*

- Sidebery启用时会自动隐藏原生标签页栏。  
  > *避免界面重复，保持界面整洁有序。*

- 兼容多种Firefox界面设置。  
  > *无论你是否显示标题栏、菜单栏、书签栏，或者将侧边栏放在左边或右边，FlexFox都能保持正常排版，适配各种使用习惯。*

### 🌟 高度灵活

> *完全掌控外观与功能。*

- 在 `about:config` 中可快速开启或关闭各项功能。  
  > *不喜欢的功能可以关掉，保留你需要的部分，其余恢复为Firefox原始样式。*

- 支持通过用户样式深度自定义。  
  > *FlexFox支持加载用户的自定义样式，并优先于自身设置，这样即使更新版本，你的自定义配置也不会丢失。*

## 💿 部署指南

### 🚀 方法一：自动安装与更新

<details>
<summary><h4>💻 PowerShell 脚本《点击展开》👇</h4></summary>

- **在线部署** – 在 PowerShell 中输入以下命令：
  ```powershell
   Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass; iex ((New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/yuuqilin/FlexFox/refs/heads/main/deploy-userchrome.ps1') -replace '(?s)<#.*?#>', '')
  ```
  **静默部署（在线）**：
  ```powershell
   $env:FLEXFOX_INSTALL_MODE = 'silent'; Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass; iex ((New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/yuuqilin/FlexFox/refs/heads/main/deploy-userchrome.ps1') -replace '(?s)<#.*?#>', '')
  ```

- **本地部署** – 下载 [`deploy-userchrome.ps1`](https://github.com/yuuqilin/FlexFox/raw/refs/heads/main/deploy-userchrome.ps1) 脚本并运行：
  ```powershell
   Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass; .\deploy-userchrome.ps1
  ```
  **静默部署（本地）**：
  ```powershell
   $env:FLEXFOX_INSTALL_MODE = 'silent'; Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass; .\deploy-userchrome.ps1
  ```

- **计划任务或 Win+R 执行静默部署**：
  ```powershell
   powershell -ExecutionPolicy Bypass -Command "$env:FLEXFOX_INSTALL_MODE = 'silent'; .\deploy-userchrome.ps1"
  ```

</details>

<details>
<summary><h4>🔃 Git Pull《点击展开》👇</h4></summary>

- 根据你的使用环境，选择使用 `scripts` 文档夹中的任一 `git-pull-chrome-only` 脚本。这些脚本会：
  - 自动将 Firefox 配置文档夹设为 Git 工作目录
  - 添加 FlexFox 为远程仓库
  - 只下载并更新 `chrome` 文档夹（不包含其他内容）

- 或者手动为 Firefox 配置文档夹添加远程仓库：

  **首次设置（初始化 chrome 文档夹）：**
  ```bash
  git init
  git remote add origin https://github.com/yuuqilin/FlexFox.git
  git sparse-checkout init --no-cone
  git sparse-checkout set /chrome
  git fetch origin
  git checkout -b main origin/main
  ```

  **手动更新：**
  ```bash
  git fetch origin
  git checkout main
  git merge origin/main --allow-unrelated-histories
  ```

</details>

---

### 👷 方法二：手动安装

> [!IMPORTANT]
> 1. 安装 [Sidebery](https://addons.mozilla.org/firefox/addon/sidebery/)（可选，但推荐）。
> 2. 下载对应版本的 FlexFox：
>    - [FlexFox](https://github.com/yuuqilin/FlexFox/archive/refs/heads/main.zip)：标准版 Firefox 使用
>    - [FlexFox Beta](https://github.com/yuuqilin/FlexFox/archive/refs/heads/Beta.zip)：Firefox Beta / Nightly 使用
>    - [FlexFox ESR](https://github.com/yuuqilin/FlexFox/archive/refs/heads/ESR.zip)：Firefox ESR 使用
> 3. 打开 `about:support`，找到 **配置文档夹**，点击 **打开文档夹**。
> 4. 将 `chrome` 文档夹和 `scripts` 文档夹中的 `user.js` 文档复制到配置文档夹中。
> 5. *(可选)* 使用文本编辑器打开 `user.js`，删除注释 `//` 以启用额外功能。
>    - 确保以下设置保持为 `true`：
>      - `toolkit.legacyUserProfileCustomizations.stylesheets`
>      - `svg.context-properties.content.enabled`
> 6. 重启 Firefox，然后删除 `user.js` 文档，使 `about:config` 中的修改能正常保存。
> 7. 配置 Sidebery：
>    - 点击侧边栏齿轮图标打开设置
>    - 进入 `帮助` > `导入插件数据`，导入下载包中的 `sidebery-settings.json` 和 `sidebery-styles.json`
>    - *注意*：如果设置没有生效，请重新导入一次
> 8. *(可选)* 在 `about:config` 中搜索 `uc.flex.`，根据需要启用或关闭功能。

## ⚙️ 配置选项

### 📜 用户可自定义样式（`uc-user-settings.css`）

> [!TIP]
> 你可以在不修改核心文档的情况下，自行覆盖默认的样式变量和规则。
> 
> 操作步骤如下：
> 
> 1. 在 `components` 文档夹中创建一个名为 `uc-user-settings.css` 的新文档。
> 2. 将你想修改的变量或规则（例如来自 `uc-variables.css`）复制出来。
> 3. 粘贴到 `uc-user-settings.css` 中，并按需修改。
> 
> 该文档会在所有内建样式之后加载，因此优先级更高。即使 FlexFox 将来更新，你的自定义设置也不会受到影响。  

> 💡 如果你要复制的是某个选择器（例如 `:root` 或 `:root:has(...)`）中的变量，请务必连同整个选择器区块一并复制，才能保证覆盖生效。

### 🧩 可配置的首选项（`about:config`）

| 配置选项                                   | 说明                                           |
|--------------------------------------------|------------------------------------------------|
| `uc.flex.add-ui-text-stroke`               | 给界面文本添加粗体边框。                       |
| `uc.flex.add-bookmarks-left-margin`        | 通过添加边距，使书签与工具栏图标对齐。         |
| `uc.flex.fully-hide-sidebery`              | 完全隐藏 Sidebery。                            |
| `uc.flex.fully-hide-toolbox`               | 隐藏所有顶部工具栏（标签、导航、书签）。       |
| `uc.flex.increase-sidebery-expanded-width` | 增加 Sidebery 展开时的宽度。                   |
| `uc.flex.allow-addons-to-change-toolbar-color` | 允许主题和扩展修改工具栏的背景图片和颜色。 |
| `uc.flex.disable-bookmarks-autohide`       | 禁用书签栏自动隐藏。                           |
| `uc.flex.disable-tabs-toolbar-autohide`    | 禁用 Sidebery 非激活时的原生标签栏自动隐藏。   |
| `uc.flex.disable-findbar-autohide`         | 禁用查找栏失去焦点时自动隐藏。                 |
| `uc.flex.disable-native-vertical-tabs-autohide` | 禁用原生垂直选项卡的自动折叠功能。          |
| `uc.flex.disable-sidebery-autohide`        | 停用 Sidebery 自动折叠。                       |
| `uc.flex.remove-bookmarks-folder-icons`    | 移除书签文档夹中的图标。                       |
| `uc.flex.remove-bookmarks-labels`          | 移除书签文本标签。                             |
| `uc.flex.switch-to-alternate-condensed-panel` | 切换到另一个简洁的扩展面板。                |
| `uc.flex.revert-to-original-window-controls` | 恢复原始窗口按钮（最小化、最大化、关闭）。   |
| `uc.flex.sidebery-fast-hover-expand`       | 加快 Sidebery 悬停展开/折叠的速度。            |
| `uc.flex.sidebery-slow-hover-expand`       | 放慢 Sidebery 悬停展开/折叠的速度。            |
| `uc.flex.show-pin-tabs-separator-in-expanded-state` | 在垂直选项卡的固定和普通标签页之间显示分隔线。 |
| `uc.flex.max-visible-vertical-pinned-tabs` | 设置原生垂直选项卡中每列钉选标签页的最大数量（数值，4～6）。    |
| `uc.flex.findbar-position` | 设置查找栏的位置。（字符串，`"top-center-left"` 或 `"0"` = 上方中央偏左，`"top-right"` 或 `"1"` = 右上角，`"bottom-right"` 或 `"2"` = 右下角） |

## 🐞 已知问题

- 对于 Floorp 用户：请在 Floorp 界面选项中切换到 `Firefox Proton UI`，以减少兼容性问题。
- 仅在 Windows 上测试：可能需要为其他操作系统进行调整。

<details>
  <summary><h2 style="display: inline;">📄 许可证</h2></summary>
  <p>本项目主要基于 MIT 许可证进行授权。<br>
  不过，部分源代码（见下文）整合了原本采用 Mozilla Public License 2.0（MPL-2.0）授权的代码。</p>

  <p>具体来说，<code>uc-sidebar.css</code> 中的部分整合代码来自以下项目：</p>

  <ul>
    <li><strong>项目</strong>：firefox-gx</li>
    <li><strong>作者</strong>：@Godiesc</li>
    <li><strong>代码库</strong>：<a href="https://github.com/Godiesc/firefox-gx">https://github.com/Godiesc/firefox-gx</a></li>
    <li><strong>许可证</strong>：MPL-2.0</li>
  </ul>

  <p>这些代码区块保留了原始的 MPL-2.0 许可声明，并符合其授权条款。<br>
  有关 MPL-2.0 的完整内容，请参见 <code>LICENSES/MPL-2.0.txt</code>。</p>
</details>
