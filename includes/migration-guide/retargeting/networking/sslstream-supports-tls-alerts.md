### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="9e9b7-101">SslStream 支持 TLS 警报</span><span class="sxs-lookup"><span data-stu-id="9e9b7-101">SslStream supports TLS Alerts</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9e9b7-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="9e9b7-102">Details</span></span>|<span data-ttu-id="9e9b7-103">TLS 握手失败后，第一个 I/O 读取/写入操作将引发带有内部 <xref:System.ComponentModel.Win32Exception?displayProperty=name> 异常的 <xref:System.IO.IOException?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=name> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=name> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="9e9b7-104">使用此 [Schannel documentation](https://msdn.microsoft.com/library/windows/desktop/dd721886%28v=vs.85%29.aspx) 可从远程方将 <xref:System.ComponentModel.Win32Exception?displayProperty=name> 的 <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=name> 代码映射到 TLS 警报。有关详细信息，请参阅 [RFC 2246：第 7.2.2 节错误警报](https://tools.ietf.org/html/rfc2246#section-7.2.2)。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=name> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=name> can be mapped to the TLS Alert from the remote party using this [Schannel documentation](https://msdn.microsoft.com/library/windows/desktop/dd721886%28v=vs.85%29.aspx).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="9e9b7-105">.NET Framework 4.6.2 及更早版本中的行为是：如果另一方握手失败然后立即拒绝连接，则传输通道（通常为 TCP 连接）将在写入或读取时超时。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>|
|<span data-ttu-id="9e9b7-106">建议</span><span class="sxs-lookup"><span data-stu-id="9e9b7-106">Suggestion</span></span>|<span data-ttu-id="9e9b7-107">调用网络 I/O API（例如 <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>）的应用程序应处理 <xref:System.IO.IOException> 或 <xref:System.TimeoutException?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=name>.</span></span><br/><span data-ttu-id="9e9b7-108">从 .NET Framework 4.7 开始，TLS 警报功能将默认启用。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="9e9b7-109">在 .NET Framework 4.7 或更高系统上运行的面向 .NET Framework 4.0 到 4.6.2 版本的应用程序将禁用该功能以保留兼容性。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="9e9b7-110">以下配置 API 用于为在 .NET Framework 4.7 或更高版本上运行的 .NET Framework 4.6 和更高版本应用程序启用或禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span><ul><li><span data-ttu-id="9e9b7-111">以编程方式：</span><span class="sxs-lookup"><span data-stu-id="9e9b7-111">Programmatically:</span></span></li></ul><span data-ttu-id="9e9b7-112">必须是应用程序执行的第一件事，因为 ServicePointManager 将只初始化一次：</span><span class="sxs-lookup"><span data-stu-id="9e9b7-112">Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span><pre><code class="lang-csharp">AppContext.SetSwitch(&quot;TestSwitch.LocalAppContext.DisableCaching&quot;, true);&#13;&#10;AppContext.SetSwitch(&quot;Switch.System.Net.DontEnableTlsAlerts&quot;, true); // Set to &#39;false&#39; to enable the feature in .NET Framework 4.6 - 4.6.2.&#13;&#10;</code></pre><ul><li><span data-ttu-id="9e9b7-113">AppConfig：</span><span class="sxs-lookup"><span data-stu-id="9e9b7-113">AppConfig:</span></span></li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableTlsAlerts=true&quot;/&gt;&#13;&#10;&lt;!-- Set to &#39;false&#39; to enable the feature in .NET Framework 4.6 - 4.6.2. --&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><ul><li><span data-ttu-id="9e9b7-114">注册表项（计算机全局）：</span><span class="sxs-lookup"><span data-stu-id="9e9b7-114">Registry key (machine global):</span></span></li></ul><span data-ttu-id="9e9b7-115">将值设置为 <code>false</code> 以在 .NET Framework 4.6 - 4.6.2 中启用该功能。</span><span class="sxs-lookup"><span data-stu-id="9e9b7-115">Set the Value to <code>false</code> to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span><pre><code>Key = HKLM\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts&#13;&#10;Type = String&#13;&#10;Value = &quot;true&quot;&#13;&#10;</code></pre>|
|<span data-ttu-id="9e9b7-116">范围</span><span class="sxs-lookup"><span data-stu-id="9e9b7-116">Scope</span></span>|<span data-ttu-id="9e9b7-117">边缘</span><span class="sxs-lookup"><span data-stu-id="9e9b7-117">Edge</span></span>|
|<span data-ttu-id="9e9b7-118">版本</span><span class="sxs-lookup"><span data-stu-id="9e9b7-118">Version</span></span>|<span data-ttu-id="9e9b7-119">4.7</span><span class="sxs-lookup"><span data-stu-id="9e9b7-119">4.7</span></span>|
|<span data-ttu-id="9e9b7-120">类型</span><span class="sxs-lookup"><span data-stu-id="9e9b7-120">Type</span></span>|<span data-ttu-id="9e9b7-121">重定目标</span><span class="sxs-lookup"><span data-stu-id="9e9b7-121">Retargeting</span></span>|
|<span data-ttu-id="9e9b7-122">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="9e9b7-122">Affected APIs</span></span>|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.WebRequest?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.Http?displayProperty=nameWithType></li></ul>|
