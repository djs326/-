# -
这些自定义事件用于自定义主页和自定义帮助，详情可以在 PCL 的内置帮助中搜索 XAML。
自定义事件
龙腾猫跃 编辑此页 2025年10月31日 · 22 次修订
这些自定义事件用于自定义主页和自定义帮助，详情可以在 PCL 的内置帮助中搜索 XAML。



触发多个自定义事件
使用以下格式可以在一个控件中触发多个自定义事件，它们会从上往下依次执行。

注意：这里的参数名是 Type 和 Data，而非 EventType 和 EventData。

<local:MyButton Text="修改变量并刷新">
    <local:CustomEventService.Events>
        <local:CustomEventCollection>
            <local:CustomEvent Type="修改变量" Data="storage|test_value|-" />
            <local:CustomEvent Type="刷新页面" Data="-" />
            <local:CustomEvent Type="弹出提示" Data="已修改变量并刷新！|Green" />
        </local:CustomEventCollection>
    </local:CustomEventService.Events>
</local:MyButton>


支持自定义事件的控件列表

类名	触发时机
MyButton	点击时
MyCard	若 CanSwap="True" 则在为展开/折叠时，否则为直接点击时
MyCheckBox	勾选/取消勾选时
MyComboBox	选中的项改变时
MyExtraButton	点击时
MyExtraTextButton	点击时
MyHint	点击时
MyIconButton	点击时
MyIconTextButton	点击时
MyListItem	点击时
MyMenuItem	点击时
MyRadioBox	勾选/取消勾选时
MyRadioButton	勾选/取消勾选时
MySearchBox	按下回车时
MyTextBox	按下回车时
MyTextButton	点击时


事件列表

打开网页
在浏览器中打开指定的网页。

参数 1： 要打开的网页的网址。支持 http://、https://、minecraft://、minecraft-preview:// 协议。


示例

<local:MyButton Text="打开 Minecraft Wiki" EventType="打开网页" EventData="https://zh.minecraft.wiki/" />


执行命令 / 打开文件
以特定的参数和路径启动进程。

参数 1： 要启动的进程的路径。

参数 2 (可选)： 进程的参数。


示例

<local:MyButton Text="打开记事本" EventType="执行命令" EventData="notepad.exe" />
<local:MyButton Text="定位游戏启动脚本" EventType="执行命令" EventData="explorer.exe|/select,LatestLaunch.bat"
    ToolTip="PCL 会将上一次启动 MC 的脚本保存在 PCL 文件夹内，且名为 LatestLaunch.bat。&#xA;点击按钮会打开文件管理器，并且借助参数要求它选中这个文件。"  />
<local:MyButton Text="打开 PCL 文件夹下的 run.exe" EventType="执行命令" EventData="run.exe|-arg {varible:SomeCustomSetup}" />


打开帮助
打开指定路径或网址中的帮助条目。

参数 1： 要打开的帮助条目 JSON 文件的路径或网址。

若要打开 PCL 自带的帮助库，输入其在 帮助库 中的相对路径，例如 个性化/XAML 格式.json。

示例

<local:MyButton Text="打开自定义帮助页面" EventType="打开帮助" EventData="个性化/XAML 格式.json" />


启动游戏
启动指定版本名的 Minecraft，并且可以指定自动进入某个服务器。

参数 1： 要启动的 Minecraft 版本名，或填写 \current 以直接启动当前版本。

若为 \current：直接启动当前版本。

否则：启动 当前 Minecraft 文件夹\versions\本参数\ 中的版本。若参数指定的文件夹不存在，则会弹出错误信息。

参数 2 (可选)： 在启动 Minecraft 后，自动加入该地址下的服务器。


示例

<local:MyButton Text="启动 Minecraft 1.12.2" EventType="启动游戏" EventData="1.12.2" />
<local:MyButton Text="启动 1.20.1 并进入 Hypixel" EventType="启动游戏" EventData="1.20.1|mc.hypixel.net" />
<local:MyButton Text="启动 {name} 并进入 Hypixel" EventType="启动游戏" EventData="\current|mc.hypixel.net" />


复制文本
将 EventData 中的内容复制到剪贴板。

参数： 要复制的文本。内容可以包含 |。


示例

<local:MyButton Text="复制苦力怕召唤命令" EventType="复制文本" EventData="/summon creeper ~ ~ ~" />


刷新页面
刷新当前所在页面，等同于立即按下 F5。可以以此刷新页面中的替换标记。

参数 1 (可选)： 若为空则会在刷新后显示 “已刷新！” 提示，若不为空则静默执行。


示例

<local:MyButton Text="刷新" EventType="刷新页面" />


刷新主页
刷新启动页面右侧的自定义主页内容。可以以此刷新页面中的替换标记。

参数 1 (可选)： 若为空则会在刷新后显示 “已刷新！” 提示，若不为空则静默执行。


示例

<local:MyButton Text="刷新" EventType="刷新主页" />


刷新帮助
重新解压、重新加载帮助库，等同于在帮助主页面按下 F5。

参数 1 (可选)： 若为空则会在刷新后显示 “已刷新！” 提示，若不为空则静默执行。


示例

<local:MyButton Text="刷新" EventType="刷新帮助" />


今日人品 / 内存优化 / 清理垃圾
等同于按下 更多 → 百宝箱 中的对应按钮。

无参数。


示例

<local:MyButton Text="看看今日人品" EventType="今日人品" />


弹出窗口
弹出一个窗口。

参数 1： 弹窗的标题。

参数 2： 弹窗的内容。

参数 3 (可选)： 弹窗的确定按钮的文本。默认为 确定。


示例

<local:MyButton Text="显示一个弹窗" EventType="弹出窗口" EventData="这是标题|标题与内容以竖线间隔。\n你也可以直接在其中换行。" />


弹出提示
在左下角弹出一个提示条。

参数 1： 提示条的内容。

参数 2 (可选)： 提示条的颜色，为 Blue、Green 或 Red。默认为 Blue。


示例

<local:MyButton Text="显示 PCL 所处文件夹" EventType="弹出提示" EventData="PCL 位于：{path}|Green" />


切换页面
强行让 PCL 切换到指定的页面。

Warning

由于这会以非常规方式强行切换页面，切换到部分页面会导致 PCL 出错！

参数 1： 主页面。要查看其列表，请在 FormMain.xaml.vb 中搜索 Enum PageType。

参数 2 (可选)： 子页面。默认为第一个子页面 (Default)。要查看其列表，请在 FormMain.xaml.vb 中搜索 Enum PageSubType。


示例

<local:MyButton Text="切换到个性化设置" EventType="切换页面" EventData="Setup|SetupUI" />


导入整合包 / 安装整合包
等同于按下 版本选择 → 导入整合包 按钮。

无参数。


示例

<local:MyButton Text="导入整合包！" EventType="导入整合包" />


下载文件
从指定网址下载文件。

参数 1： 要下载文件的来源网址。只接受 http:// 与 https:// 协议。

参数 2 (可选)： 下载到本地的文件名。若不填写此参数，则会从网址中自动分析文件名。

参数 3 (可选)： 下载的目标文件夹路径。若不填写此参数，则会弹窗要求选择下载到哪个文件夹。


示例

<local:MyButton Text="下载百度的 Logo" EventType="下载文件" EventData="https://www.baidu.com/img/flexible/logo/pc/result.png|百度 Logo.png" />


修改设置 / 写入设置
修改 PCL 的指定设置项并应用。

参数 1： 设置名。

你可以在 ModSetup.vb 的开头查看其列表
若上述文件对应行有 Encoded:=True，则该项设置已加密，不允许使用本事件修改
若上述文件对应行有 Source:=SetupSource.Version，则该项设置是版本独立设置，本事件会修改当前选中版本的对应设置
参数 2： 设置值。要确定设置值，你可以先在 PCL 内自行修改这项设置，然后再使用 setup 替换标记 查看。

参数 3 (可选)： 若为空则会在刷新后显示 “已写入设置！” 提示，若不为空则静默执行。


示例

<local:MyButton Text="将窗口改为半透明" Tooltip="当前设置值为：{setup:UiLauncherTransparent}"
    EventType="修改设置" EventData="UiLauncherTransparent|400" />


修改变量 / 写入变量
写入一个自定义变量，以便后续在 varible 替换标记 中使用。

该自定义变量将存储于注册表的 HKEY_CURRENT_USER\Software\PCL 路径中。

参数 1： 变量名。

参数 2： 变量值。

参数 3 (可选)： 若为空则会在刷新后显示 “已写入变量！” 提示，若不为空则静默执行。


示例

<local:MyButton Text="将变量 storage 改为 test_value" EventType="修改变量" EventData="storage|test_value" />
<local:MyButton Text="修改变量并刷新" Tooltip="当前变量为：{varible:storage}">
    <local:CustomEventService.Events>
        <local:CustomEventCollection>
            <local:CustomEvent Type="修改变量" Data="storage|test_value|-" />
            <local:CustomEvent Type="刷新页面" Data="-" />
            <local:CustomEvent Type="弹出提示" Data="已修改变量并刷新！|Green" />
        </local:CustomEventCollection>
    </local:CustomEventService.Events>
</local:MyButton>


加入房间
Note

该事件在 PCL 2.11.1 或更高的版本可用（ {pcl_version_code} >= 374 ）

加入联机房间。

参数 1 (可选)： 切换到联机页面，将该参数作为邀请码，自动加入指定的联机房间。若为空，则会弹窗要求输入邀请码。


示例

<local:MyButton Text="加入！" EventType="加入房间" EventData="PFE0F-X59JM-VVM0M" />
