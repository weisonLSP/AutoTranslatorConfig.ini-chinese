[服务]
Endpoint : GoogleTranslate ; 使用的端点。请参见 translators section 获取有效值。
FallbackEndpoint : ; 如果特定翻译失败，自动回退到的端点。
[常规]
Language : en ; 要翻译成的语言
FromLanguage : ja ; 游戏原始语言。“auto” 也被支持，但通常不推荐使用
[文件]
Directory : Translation{Lang}\Text ; 搜索缓存翻译文件的目录。可以使用占位符：{GameExeName}, {Lang}
OutputFile : Translation{Lang}\Text_AutoGeneratedTranslations.txt ; 插入生成翻译的文件。可以使用占位符：{GameExeName}, {Lang}
SubstitutionFile : Translation{Lang}\Text_Substitutions.txt ; 包含在翻译前应用替换的文件。可以使用占位符：{GameExeName}, {Lang}
PreprocessorsFile : Translation{Lang}\Text_Preprocessors.txt ; 包含在发送文本给翻译器之前应用的预处理程序的文件。可以使用占位符：{GameExeName}, {Lang}
PostprocessorsFile : Translation{Lang}\Text_Postprocessors.txt ; 包含在接收文本后应用的后处理程序的文件。可以使用占位符：{GameExeName}, {Lang}
[文本框架]
EnableUGUI : True ; 启用或禁用 UGUI 翻译
EnableNGUI : True ; 启用或禁用 NGUI 翻译
EnableTextMeshPro : True ; 启用或禁用 TextMeshPro 翻译
EnableTextMesh : False ; 启用或禁用 TextMesh 翻译
EnableIMGUI : False ; 启用或禁用 IMGUI 翻译
[行为]
MaxCharactersPerTranslation : 200 ; 每个文本要翻译的最大字符数。最大2500。
IgnoreWhitespaceInDialogue : True ; 是否忽略对话键中的空白，包括换行。
IgnoreWhitespaceInNGUI : True ; 是否忽略 NGUI 中的空白，包括换行。
MinDialogueChars : 20 ; 被视为对话所需文本长度
ForceSplitTextAfterCharacters : 0 ; 一旦翻译后的文本超过此字符数，将其拆分成多行。
CopyToClipboard : False ; 是否将钩取到的文本复制到剪贴板
MaxClipboardCopyCharacters : 450 ; 每次钩取到剪贴板的最大字符数
…
[行为]（续）
ClipboardDebounceTime : 1.25 ; 钩取文本到剪贴板所需的秒数。最小值为0.1。
EnableUIResizing : True ; 插件是否应在翻译时提供“最佳尝试”来调整 UI 组件大小。
EnableBatching : True ; 是否启用对支持的端点进行翻译批处理。
UseStaticTranslations : True ; 是否使用包含的静态翻译缓存中的翻译。
OverrideFont : ; 更新文本组件时使用的字体覆盖。注意：仅适用于 UGUI。
OverrideFontTextMeshPro : ; 考虑使用 FallbackFontTextMeshPro 替代。更新文本组件时使用的字体覆盖。仅适用于 TextMeshPro。
FallbackFontTextMeshPro : ; 为 TextMeshPro 添加后备字体，以防特定字符不被支持。这比 OverrideFontTextMeshPro 更推荐。
ResizeUILineSpacingScale : ; 在 UI 调整大小期间默认行间距应缩放的十进制值，例如：0.80。注意：仅适用于 UGUI。
ForceUIResizing : True ; 指示无论 UI 组件是否被翻译，都应将 UI 调整行为应用于所有 UI 组件。
IgnoreTextStartingWith=\u180e; ; 指示插件应忽略以某些字符开头的字符串。这是一个用分号分隔的列表。
TextGetterCompatibilityMode : False; 指示是否启用“文本获取器兼容模式”。只有在游戏需要时才应启用。
[日志]
GameLogTextPaths= ; 指示游戏作为“日志组件”使用的特定路径，该路径不断附加或预先添加文本。设置此项需要专业知识。这是一个用分号分隔的列表。
[罗马字后处理]
RomajiPostProcessing=ReplaceMacronWithCircumflex;RemoveApostrophes;ReplaceHtmlEntities;
指示在“翻译”的罗马字文本上执行何种类型的后处理。在某些游戏中，这可能很重要，因为所使用的字体无法正确支持各种变音符号。这是一个用分号分隔的列表。可能值包括：
“RemoveAllDiacritics”
“ReplaceMacronWithCircumflex”
“RemoveApostrophes”
“ReplaceHtmlEntities”
[翻译后处理]
TranslationPostProcessing=ReplaceMacronWithCircumflex;ReplaceHtmlEntities;
指示对翻译文本（非罗马字）执行何种类型的后处理。可能值包括：
“RemoveAllDiacritics”
“ReplaceMacronWithCircumflex”
“RemoveApostrophes”
“ReplaceWideCharacters”
“ReplaceHtmlEntities”
[正则表达式后处理]
**RegexPostProcessing=None ;指示对正则表达式捕获组执行何种类型的后处理。可能值包括：
“RemoveAllDiacritics”
“ReplaceMacronWithCircumflex”
…
[缓存]
*CacheRegexLookups=False ;指示是否将正则查找结果输出到指定输出文件 CacheWhitespaceDifferences=False ; 指示是否将空白差异输出到指定输出文件。
CacheRegexPatternResults=False ; 指示是否将正则拆分翻译的完整结果输出到指定输出文件。
GenerateStaticSubstitutionTranslations=False ; 指示插件在使用替换时是否生成没有变量的翻译。
GeneratePartialTranslations=False ; 指示插件在文本“滚动中”支持文本翻译时是否生成部分翻译。
EnableTranslationScoping=False ; 指示插件是否应解析 ‘TARC’ 指令并根据这些指令范围翻译。
EnableSilentMode=False ; 指示插件在与翻译相关的成功消息上不打印任何内容。
BlacklistedIMGUIPlugins= ; 如果 IMGUI 窗口程序集/类/方法名称包含列表中的任何字符串（不区分大小写），则该 UI 将不会被翻译。这是一个用分号分隔的列表。
OutputUntranslatableText=False ; 指示如果文本被插件视为不可翻译，是否应将其输出到指定输出文件。
IgnoreVirtualTextSetterCallingRules=False; 指示在尝试设置文本组件的文本时，虚拟方法调用规则应被忽略。在某些情况下，这可能有助于设置顽固组件的文本。
MaxTextParserRecursion=1 ; 指示当文本被解析以便可以在不同部分进行翻译时允许多少级递归。这可以与高级场景中的拆分正则表达式一起使用。默认值为一，基本上意味着禁用递归。
[HTML 实体预处理]
HtmlEntityPreprocessing=True ; 在发送前，将对 HTML 实体进行预处理和解码。一些翻译器在接收到 HTML 实体时会失败。
[富文本处理]
HandleRichText=True ; 启用自动处理带标记的富文本（带格式的文本）。
PersistRichTextMode=Final ; 表示解析后的富文本应该如何持久化。“Fragment”表示逐块存储文本，“Final”表示存储整个已翻译字符串（不支持替换！）。
[助手]
EnableTranslationHelper=False ; 是否启用与翻译相关的帮助日志消息。这在基于重定向资源进行翻译时可能有用。
[MonoMod 钩子]
ForceMonoModHooks=False ; 表明插件必须使用 MonoMod 钩子，而不是 Harmony 钩子。
InitializeHarmonyDetourBridge=False; 表明插件应初始化 Harmony 拦截桥，以使 Harmony 钩子能够在不存在 System.Reflection.Emit 的环境中工作（通常由插件管理器处理，因此请勿在使用插件管理器时使用）。
[资源重定向器]
PreferredStoragePath=Translation{Lang}\RedirectedResources; ；指示有关 Auto Translator 的重定向资源首选存储路径，可以使用占位符：{GameExeName}, {Lang}
**EnableTextAssetRedirector=False ；指示 TextAssets 是否应被重定向。
…
[HTTP 设置]
**UserAgent= ; 覆盖 API 所需用户代理所使用的用户代理。
**DisableCertificateValidation=False; 表明是否禁用 .NET API 的证书验证。
[翻译聚合器]
**Width=400 ; 翻译聚合窗口的总宽度。
**Height=100 ; 每个翻译器的宽度。
**EnabledTranslators= ; 已启用在翻译聚合窗口中的端点 ID 列表，用分号分隔。
[Google 设置]
**ServiceUrl= ; 可选，用于将 Google API 请求导向不同 URL，可用于绕过 GFWoC。
[合法 Google 设置]
**GoogleAPIKey= ; 可选，如果配置了 GoogleTranslateLegitimate，则需要此项。
[Bing 设置]
-**OcpApimSubscriptionKey= ; 可选，如果配置了 BingTranslateLegitimate，则需要此项。

[百度设置]
-**BaiduAppId= ; 可选，如果配置了 BaiduTranslate，则需要此项。
-**BaiduAppSecret= ; 可选，如果配置了 BaiduTranslate，则需要此项。

[Yandex 设置]
-**YandexAPIKey= ; 可选，如果配置了 YandexTranslate，则需要此项。

[Watson 设置]
-**Url= ; 可选，如果配置了 WatsonTranslate，则需要此项。
-**Key= ; 可选，如果配置了 WatsonTranslate，则需要此项。

[DeepL 设置]
-**MinDelay=2 ；可选，用于限制 DeepL 的请求速度。
-**MaxDelay=7 ；可选，用于限制 DeepL 的请求速度。

[合法 DeepL 设置]
-**ApiKey= ；可选，如果配置了 DeepLLegitimate 则必需。
-**Free=False ；可选，如配置 DeepLLegitimate 则必需。

[自定义设置]
-**Url= ；可选，当 CustomTranslated 配置时必需。

[LecPowerTranslator15 设置]
-**InstallationPath= ；可选，当 LecPowerTranslator15 配置时必需。

[LingoCloud 设置]
-**LingoCloudToken= ；可选，当 LingoCloudTranslate 配置时必需。

[调试设置]
-**EnableConsole=False ؛ 启用控制台。如果其他插件（管理器）处理此功能，请勿启用。
-**EnableLog=False ؛ 启用额外日志记录以供调试目的。

[迁移设置]
-**Enable=True ؛ 用于启用该配置文件的自动迁移
-**Tag=4.15.0 ؛ 表示最后一次执行该插件所依据版本标签。不编辑
