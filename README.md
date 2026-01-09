# -
这些自定义事件用于自定义主页和自定义帮助，详情可以在 PCL 的内置帮助中搜索 XAML。
这些自定义事件用于自定义主页和自定义帮助，详情可以在 PCL 的内置帮助中搜索 `XAML`。

## 触发多个自定义事件

[](#触发多个自定义事件)

使用以下格式可以在一个控件中触发多个自定义事件，它们会从上往下依次执行。

注意：这里的参数名是 `Type` 和 `Data`，而非 `EventType` 和 `EventData`。
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>修改变量并刷新<span class="pl-pds">"</span></span>&gt;
    &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventService</span>.Events&gt;
        &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventCollection</span>&gt;
            &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEvent</span> <span class="pl-e">Type</span>=<span class="pl-s"><span class="pl-pds">"</span>修改变量<span class="pl-pds">"</span></span> <span class="pl-e">Data</span>=<span class="pl-s"><span class="pl-pds">"</span>storage|test_value|-<span class="pl-pds">"</span></span> /&gt;
            &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEvent</span> <span class="pl-e">Type</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新页面<span class="pl-pds">"</span></span> <span class="pl-e">Data</span>=<span class="pl-s"><span class="pl-pds">"</span>-<span class="pl-pds">"</span></span> /&gt;
            &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEvent</span> <span class="pl-e">Type</span>=<span class="pl-s"><span class="pl-pds">"</span>弹出提示<span class="pl-pds">"</span></span> <span class="pl-e">Data</span>=<span class="pl-s"><span class="pl-pds">"</span>已修改变量并刷新！|Green<span class="pl-pds">"</span></span> /&gt;
        &lt;/<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventCollection</span>&gt;
    &lt;/<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventService</span>.Events&gt;
&lt;/<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span>&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;修改变量并刷新&quot;&gt;
    &lt;local:CustomEventService.Events&gt;
        &lt;local:CustomEventCollection&gt;
            &lt;local:CustomEvent Type=&quot;修改变量&quot; Data=&quot;storage|test_value|-&quot; /&gt;
            &lt;local:CustomEvent Type=&quot;刷新页面&quot; Data=&quot;-&quot; /&gt;
            &lt;local:CustomEvent Type=&quot;弹出提示&quot; Data=&quot;已修改变量并刷新！|Green&quot; /&gt;
        &lt;/local:CustomEventCollection&gt;
    &lt;/local:CustomEventService.Events&gt;
&lt;/local:MyButton&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 支持自定义事件的控件列表

[](#支持自定义事件的控件列表)

  

| 类名 | 触发时机 |
| --- | --- |
| `MyButton` | 点击时 |
| `MyCard` | 若 `CanSwap="True"` 则在为展开/折叠时，否则为直接点击时 |
| `MyCheckBox` | 勾选/取消勾选时 |
| `MyComboBox` | 选中的项改变时 |
| `MyExtraButton` | 点击时 |
| `MyExtraTextButton` | 点击时 |
| `MyHint` | 点击时 |
| `MyIconButton` | 点击时 |
| `MyIconTextButton` | 点击时 |
| `MyListItem` | 点击时 |
| `MyMenuItem` | 点击时 |
| `MyRadioBox` | 勾选/取消勾选时 |
| `MyRadioButton` | 勾选/取消勾选时 |
| `MySearchBox` | 按下回车时 |
| `MyTextBox` | 按下回车时 |
| `MyTextButton` | 点击时 |

## 事件列表

[](#事件列表)

## 打开网页

[](#打开网页)

在浏览器中打开指定的网页。

**参数 1：** 要打开的网页的网址。支持 `http://`、`https://`、`minecraft://`、`minecraft-preview://` 协议。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>打开 Minecraft Wiki<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>打开网页<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>https://zh.minecraft.wiki/<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;打开 Minecraft Wiki&quot; EventType=&quot;打开网页&quot; EventData=&quot;https://zh.minecraft.wiki/&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
## 执行命令 / 打开文件

[](#执行命令--打开文件)

以特定的参数和路径启动进程。

**参数 1：** 要启动的进程的路径。

**参数 2 (可选)：** 进程的参数。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>打开记事本<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>执行命令<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>notepad.exe<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;打开记事本&quot; EventType=&quot;执行命令&quot; EventData=&quot;notepad.exe&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
  <div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>定位游戏启动脚本<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>执行命令<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>explorer.exe|/select,LatestLaunch.bat<span class="pl-pds">"</span></span>
    <span class="pl-e">ToolTip</span>=<span class="pl-s"><span class="pl-pds">"</span>PCL 会将上一次启动 MC 的脚本保存在 PCL 文件夹内，且名为 LatestLaunch.bat。<span class="pl-c1">&amp;#xA;</span>点击按钮会打开文件管理器，并且借助参数要求它选中这个文件。<span class="pl-pds">"</span></span>  /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;定位游戏启动脚本&quot; EventType=&quot;执行命令&quot; EventData=&quot;explorer.exe|/select,LatestLaunch.bat&quot;
    ToolTip=&quot;PCL 会将上一次启动 MC 的脚本保存在 PCL 文件夹内，且名为 LatestLaunch.bat。&amp;#xA;点击按钮会打开文件管理器，并且借助参数要求它选中这个文件。&quot;  /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
  <div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>打开 PCL 文件夹下的 run.exe<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>执行命令<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>run.exe|-arg {varible:SomeCustomSetup}<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;打开 PCL 文件夹下的 run.exe&quot; EventType=&quot;执行命令&quot; EventData=&quot;run.exe|-arg {varible:SomeCustomSetup}&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 打开帮助

[](#打开帮助)

打开指定路径或网址中的帮助条目。

**参数 1：** 要打开的帮助条目 JSON 文件的路径或网址。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>打开自定义帮助页面<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>打开帮助<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>个性化/XAML 格式.json<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;打开自定义帮助页面&quot; EventType=&quot;打开帮助&quot; EventData=&quot;个性化/XAML 格式.json&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 启动游戏

[](#启动游戏)

启动指定版本名的 Minecraft，并且可以指定自动进入某个服务器。

**参数 1：** 要启动的 Minecraft 版本名，或填写 `\current` 以直接启动当前版本。

**参数 2 (可选)：** 在启动 Minecraft 后，自动加入该地址下的服务器。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>启动 Minecraft 1.12.2<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>启动游戏<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>1.12.2<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;启动 Minecraft 1.12.2&quot; EventType=&quot;启动游戏&quot; EventData=&quot;1.12.2&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
  <div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>启动 1.20.1 并进入 Hypixel<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>启动游戏<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>1.20.1|mc.hypixel.net<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;启动 1.20.1 并进入 Hypixel&quot; EventType=&quot;启动游戏&quot; EventData=&quot;1.20.1|mc.hypixel.net&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
  <div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>启动 {name} 并进入 Hypixel<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>启动游戏<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>\current|mc.hypixel.net<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;启动 {name} 并进入 Hypixel&quot; EventType=&quot;启动游戏&quot; EventData=&quot;\current|mc.hypixel.net&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 复制文本

[](#复制文本)

将 `EventData` 中的内容复制到剪贴板。

**参数：** 要复制的文本。内容可以包含 `|`。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>复制苦力怕召唤命令<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>复制文本<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>/summon creeper ~ ~ ~<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;复制苦力怕召唤命令&quot; EventType=&quot;复制文本&quot; EventData=&quot;/summon creeper ~ ~ ~&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 刷新页面

[](#刷新页面)

刷新当前所在页面，等同于立即按下 F5。可以以此刷新页面中的替换标记。

**参数 1 (可选)：** 若为空则会在刷新后显示 “已刷新！” 提示，若不为空则静默执行。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新页面<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;刷新&quot; EventType=&quot;刷新页面&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 刷新主页

[](#刷新主页)

刷新启动页面右侧的自定义主页内容。可以以此刷新页面中的替换标记。

**参数 1 (可选)：** 若为空则会在刷新后显示 “已刷新！” 提示，若不为空则静默执行。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新主页<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;刷新&quot; EventType=&quot;刷新主页&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 刷新帮助

[](#刷新帮助)

重新解压、重新加载帮助库，等同于在帮助主页面按下 F5。

**参数 1 (可选)：** 若为空则会在刷新后显示 “已刷新！” 提示，若不为空则静默执行。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新帮助<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;刷新&quot; EventType=&quot;刷新帮助&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 今日人品 / 内存优化 / 清理垃圾

[](#今日人品--内存优化--清理垃圾)

等同于按下 `更多 → 百宝箱` 中的对应按钮。

无参数。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>看看今日人品<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>今日人品<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;看看今日人品&quot; EventType=&quot;今日人品&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 弹出窗口

[](#弹出窗口)

弹出一个窗口。

**参数 1：** 弹窗的标题。

**参数 2：** 弹窗的内容。

**参数 3 (可选)：** 弹窗的确定按钮的文本。默认为 `确定`。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>显示一个弹窗<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>弹出窗口<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>这是标题|标题与内容以竖线间隔。\n你也可以直接在其中换行。<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;显示一个弹窗&quot; EventType=&quot;弹出窗口&quot; EventData=&quot;这是标题|标题与内容以竖线间隔。\n你也可以直接在其中换行。&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 弹出提示

[](#弹出提示)

在左下角弹出一个提示条。

**参数 1：** 提示条的内容。

**参数 2 (可选)：** 提示条的颜色，为 `Blue`、`Green` 或 `Red`。默认为 `Blue`。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>显示 PCL 所处文件夹<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>弹出提示<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>PCL 位于：{path}|Green<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;显示 PCL 所处文件夹&quot; EventType=&quot;弹出提示&quot; EventData=&quot;PCL 位于：{path}|Green&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 切换页面

[](#切换页面)

强行让 PCL 切换到指定的页面。

**参数 1：** 主页面。要查看其列表，请在 [FormMain.xaml.vb](https://github.com/Meloong-Git/PCL/blob/main/Plain%20Craft%20Launcher%202/FormMain.xaml.vb) 中搜索 `Enum PageType`。

**参数 2 (可选)：** 子页面。默认为第一个子页面 (Default)。要查看其列表，请在 [FormMain.xaml.vb](https://github.com/Meloong-Git/PCL/blob/main/Plain%20Craft%20Launcher%202/FormMain.xaml.vb) 中搜索 `Enum PageSubType`。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>切换到个性化设置<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>切换页面<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>Setup|SetupUI<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;切换到个性化设置&quot; EventType=&quot;切换页面&quot; EventData=&quot;Setup|SetupUI&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 导入整合包 / 安装整合包

[](#导入整合包--安装整合包)

等同于按下 `版本选择 → 导入整合包` 按钮。

无参数。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>导入整合包！<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>导入整合包<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;导入整合包！&quot; EventType=&quot;导入整合包&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 下载文件

[](#下载文件)

从指定网址下载文件。

**参数 1：** 要下载文件的来源网址。只接受 `http://` 与 `https://` 协议。

**参数 2 (可选)：** 下载到本地的文件名。若不填写此参数，则会从网址中自动分析文件名。

**参数 3 (可选)：** 下载的目标文件夹路径。若不填写此参数，则会弹窗要求选择下载到哪个文件夹。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>下载百度的 Logo<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>下载文件<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>https://www.baidu.com/img/flexible/logo/pc/result.png|百度 Logo.png<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;下载百度的 Logo&quot; EventType=&quot;下载文件&quot; EventData=&quot;https://www.baidu.com/img/flexible/logo/pc/result.png|百度 Logo.png&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 修改设置 / 写入设置

[](#修改设置--写入设置)

修改 PCL 的指定设置项并应用。

**参数 1：** 设置名。

**参数 2：** 设置值。要确定设置值，你可以先在 PCL 内自行修改这项设置，然后再使用 [setup 替换标记](https://github.com/Meloong-Git/PCL/wiki/%E6%9B%BF%E6%8D%A2%E6%A0%87%E8%AE%B0#%E9%AB%98%E7%BA%A7) 查看。

**参数 3 (可选)：** 若为空则会在刷新后显示 “已写入设置！” 提示，若不为空则静默执行。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>将窗口改为半透明<span class="pl-pds">"</span></span> <span class="pl-e">Tooltip</span>=<span class="pl-s"><span class="pl-pds">"</span>当前设置值为：{setup:UiLauncherTransparent}<span class="pl-pds">"</span></span>
    <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>修改设置<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>UiLauncherTransparent|400<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;将窗口改为半透明&quot; Tooltip=&quot;当前设置值为：{setup:UiLauncherTransparent}&quot;
    EventType=&quot;修改设置&quot; EventData=&quot;UiLauncherTransparent|400&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 修改变量 / 写入变量

[](#修改变量--写入变量)

写入一个自定义变量，以便后续在 [varible 替换标记](https://github.com/Meloong-Git/PCL/wiki/%E6%9B%BF%E6%8D%A2%E6%A0%87%E8%AE%B0#%E9%AB%98%E7%BA%A7) 中使用。

该自定义变量将存储于注册表的 `HKEY_CURRENT_USER\Software\PCL` 路径中。

**参数 1：** 变量名。

**参数 2：** 变量值。

**参数 3 (可选)：** 若为空则会在刷新后显示 “已写入变量！” 提示，若不为空则静默执行。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>将变量 storage 改为 test_value<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>修改变量<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>storage|test_value<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;将变量 storage 改为 test_value&quot; EventType=&quot;修改变量&quot; EventData=&quot;storage|test_value&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
  <div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>修改变量并刷新<span class="pl-pds">"</span></span> <span class="pl-e">Tooltip</span>=<span class="pl-s"><span class="pl-pds">"</span>当前变量为：{varible:storage}<span class="pl-pds">"</span></span>&gt;
    &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventService</span>.Events&gt;
        &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventCollection</span>&gt;
            &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEvent</span> <span class="pl-e">Type</span>=<span class="pl-s"><span class="pl-pds">"</span>修改变量<span class="pl-pds">"</span></span> <span class="pl-e">Data</span>=<span class="pl-s"><span class="pl-pds">"</span>storage|test_value|-<span class="pl-pds">"</span></span> /&gt;
            &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEvent</span> <span class="pl-e">Type</span>=<span class="pl-s"><span class="pl-pds">"</span>刷新页面<span class="pl-pds">"</span></span> <span class="pl-e">Data</span>=<span class="pl-s"><span class="pl-pds">"</span>-<span class="pl-pds">"</span></span> /&gt;
            &lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEvent</span> <span class="pl-e">Type</span>=<span class="pl-s"><span class="pl-pds">"</span>弹出提示<span class="pl-pds">"</span></span> <span class="pl-e">Data</span>=<span class="pl-s"><span class="pl-pds">"</span>已修改变量并刷新！|Green<span class="pl-pds">"</span></span> /&gt;
        &lt;/<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventCollection</span>&gt;
    &lt;/<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">CustomEventService</span>.Events&gt;
&lt;/<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span>&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;修改变量并刷新&quot; Tooltip=&quot;当前变量为：{varible:storage}&quot;&gt;
    &lt;local:CustomEventService.Events&gt;
        &lt;local:CustomEventCollection&gt;
            &lt;local:CustomEvent Type=&quot;修改变量&quot; Data=&quot;storage|test_value|-&quot; /&gt;
            &lt;local:CustomEvent Type=&quot;刷新页面&quot; Data=&quot;-&quot; /&gt;
            &lt;local:CustomEvent Type=&quot;弹出提示&quot; Data=&quot;已修改变量并刷新！|Green&quot; /&gt;
        &lt;/local:CustomEventCollection&gt;
    &lt;/local:CustomEventService.Events&gt;
&lt;/local:MyButton&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>

## 加入房间

[](#加入房间)

加入联机房间。

**参数 1 (可选)：** 切换到联机页面，将该参数作为邀请码，自动加入指定的联机房间。若为空，则会弹窗要求输入邀请码。

**示例**
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto"><pre>&lt;<span class="pl-ent">local</span><span class="pl-ent">:</span><span class="pl-ent">MyButton</span> <span class="pl-e">Text</span>=<span class="pl-s"><span class="pl-pds">"</span>加入！<span class="pl-pds">"</span></span> <span class="pl-e">EventType</span>=<span class="pl-s"><span class="pl-pds">"</span>加入房间<span class="pl-pds">"</span></span> <span class="pl-e">EventData</span>=<span class="pl-s"><span class="pl-pds">"</span>PFE0F-X59JM-VVM0M<span class="pl-pds">"</span></span> /&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0" data-copy-feedback="Copied!" data-tooltip-direction="w" value="&lt;local:MyButton Text=&quot;加入！&quot; EventType=&quot;加入房间&quot; EventData=&quot;PFE0F-X59JM-VVM0M&quot; /&gt;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
