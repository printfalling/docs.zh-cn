### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="d5049-101">带有超时自变量的 Task.WaitAll 方法的行为更改</span><span class="sxs-lookup"><span data-stu-id="d5049-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d5049-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="d5049-102">Details</span></span>|<span data-ttu-id="d5049-103">Task.WaitAll 行为在 .NET 4.5 中变得更加一致。在 .NET Framework 4 中，这些方法的行为不一致。</span><span class="sxs-lookup"><span data-stu-id="d5049-103">Task.WaitAll behavior was made more consistent in .NET 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="d5049-104">当超时到期时，如果在调用此方法之前已完成或已取消一个或多个任务，则此方法会引发 <xref:System.AggregateException?displayProperty=name> 异常。</span><span class="sxs-lookup"><span data-stu-id="d5049-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=name> exception.</span></span> <span data-ttu-id="d5049-105">在超时到期时，如果在调用此方法之前尚未完成或取消任何任务，但在调用此方法之后，一个或多个任务进入了这些状态，则该方法返回 false。</span><span class="sxs-lookup"><span data-stu-id="d5049-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="d5049-106">在 .NET Framework 4.5 中，如果在超时时间间隔到期时仍有任务在运行，这些方法重载现在将返回 false；仅当取消某个输入任务（无论是在方法调用之前还是之后取消）且没有任务仍在运行时，它们才将引发 <xref:System.AggregateException?displayProperty=name> 异常。</span><span class="sxs-lookup"><span data-stu-id="d5049-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=name> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>|
|<span data-ttu-id="d5049-107">建议</span><span class="sxs-lookup"><span data-stu-id="d5049-107">Suggestion</span></span>|<span data-ttu-id="d5049-108">如果 <xref:System.AggregateException?displayProperty=name> 已捕获作为检测在调用 WaitAll 之前已取消的任务的方法，该代码应通过 IsCanceled 属性（例如：.Any(t =&gt; t.IsCanceled)）执行相同的检测操作，因为 .NET 4.6 仅当所有等待任务在超时前均已完成时才会引发。</span><span class="sxs-lookup"><span data-stu-id="d5049-108">If an <xref:System.AggregateException?displayProperty=name> was being caught as a means of detecting a task that was cancelled prior to the WaitAll call being invoked, that code should instead do the same detection via the IsCanceled property (for example: .Any(t =&gt; t.IsCanceled)) since .NET 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>|
|<span data-ttu-id="d5049-109">范围</span><span class="sxs-lookup"><span data-stu-id="d5049-109">Scope</span></span>|<span data-ttu-id="d5049-110">次要</span><span class="sxs-lookup"><span data-stu-id="d5049-110">Minor</span></span>|
|<span data-ttu-id="d5049-111">版本</span><span class="sxs-lookup"><span data-stu-id="d5049-111">Version</span></span>|<span data-ttu-id="d5049-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d5049-112">4.5</span></span>|
|<span data-ttu-id="d5049-113">类型</span><span class="sxs-lookup"><span data-stu-id="d5049-113">Type</span></span>|<span data-ttu-id="d5049-114">运行时</span><span class="sxs-lookup"><span data-stu-id="d5049-114">Runtime</span></span>|
|<span data-ttu-id="d5049-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="d5049-115">Affected APIs</span></span>|<ul><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|
