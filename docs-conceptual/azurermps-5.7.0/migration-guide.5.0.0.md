# <a name="breaking-changes-for-microsoft-azure-powershell-500"></a><span data-ttu-id="9d8d6-101">Större ändringar för Microsoft Azure PowerShell 5.0.0</span><span class="sxs-lookup"><span data-stu-id="9d8d6-101">Breaking changes for Microsoft Azure PowerShell 5.0.0</span></span>

<span data-ttu-id="9d8d6-102">Det här dokumentet fungerar både som ett meddelande om större ändringar och som en migreringsguide för användare av Microsoft Azure PowerShell-cmdletar.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-102">This document serves as both a breaking change notification and migration guide for consumers of the Microsoft Azure PowerShell cmdlets.</span></span> <span data-ttu-id="9d8d6-103">I varje avsnitt beskrivs både orsaken till den större ändringen och det enklaste migreringssättet.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-103">Each section describes both the impetus for the breaking change and the migration path of least resistance.</span></span> <span data-ttu-id="9d8d6-104">Se den pull-begäran som är kopplad till varje ändring för en mer djupgående kontext.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-104">For in-depth context, please refer to the pull request associated with each change.</span></span>

## <a name="table-of-contents"></a><span data-ttu-id="9d8d6-105">Innehållsförteckning</span><span class="sxs-lookup"><span data-stu-id="9d8d6-105">Table of Contents</span></span>

- [<span data-ttu-id="9d8d6-106">Större ändringar i ApiManagement-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-106">Breaking changes to ApiManagement cmdlets</span></span>](#breaking-changes-to-apimanagement-cmdlets)
- [<span data-ttu-id="9d8d6-107">Större ändringar i Batch-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-107">Breaking changes to Batch cmdlets</span></span>](#breaking-changes-to-batch-cmdlets)
- [<span data-ttu-id="9d8d6-108">Större ändringar i Compute-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-108">Breaking changes to Compute cmdlets</span></span>](#breaking-changes-to-compute-cmdlets)
- [<span data-ttu-id="9d8d6-109">Större ändringar i EventHub-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-109">Breaking changes to EventHub cmdlets</span></span>](#breaking-changes-to-eventhub-cmdlets)
- [<span data-ttu-id="9d8d6-110">Större ändringar i Insights-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-110">Breaking changes to Insights cmdlets</span></span>](#breaking-changes-to-insights-cmdlets)
- [<span data-ttu-id="9d8d6-111">Större ändringar i Network-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-111">Breaking changes to Network cmdlets</span></span>](#breaking-changes-to-network-cmdlets)
- [<span data-ttu-id="9d8d6-112">Större ändringar i Resources-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-112">Breaking changes to Resources cmdlets</span></span>](#breaking-changes-to-resources-cmdlets)
- [<span data-ttu-id="9d8d6-113">Större ändringar i ServiceBus-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-113">Breaking Changes to ServiceBus Cmdlets</span></span>](#breaking-changes-to-servicebus-cmdlets)

## <a name="breaking-changes-to-apimanagement-cmdlets"></a><span data-ttu-id="9d8d6-114">Större ändringar i ApiManagement-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-114">Breaking changes to ApiManagement cmdlets</span></span>

### <a name="new-azurermapimanagementbackendproxy"></a><span data-ttu-id="9d8d6-115">**New-AzureRmApiManagementBackendProxy**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-115">**New-AzureRmApiManagementBackendProxy**</span></span>
- <span data-ttu-id="9d8d6-116">Parametrarna ”UserName” och ”Password” ersätts av PSCredential</span><span class="sxs-lookup"><span data-stu-id="9d8d6-116">Parameters "UserName" and "Password" are being replaced in favor of a PSCredential</span></span>

```powershell
# Old
New-AzureRmApiManagementBackendProxy [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
New-AzureRmApiManagementBackendProxy [other required parameters] -Credential $PSCredentialVariable
```

### <a name="new-azurermapimanagementuser"></a><span data-ttu-id="9d8d6-117">**New-AzureRmApiManagementUser**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-117">**New-AzureRmApiManagementUser**</span></span>
- <span data-ttu-id="9d8d6-118">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-118">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapimanagementuser"></a><span data-ttu-id="9d8d6-119">**Set-AzureRmApiManagementUser**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-119">**Set-AzureRmApiManagementUser**</span></span>
- <span data-ttu-id="9d8d6-120">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-120">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Set-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-batch-cmdlets"></a><span data-ttu-id="9d8d6-121">Större ändringar i Batch-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-121">Breaking changes to Batch cmdlets</span></span>

### <a name="new-azurebatchcertificate"></a><span data-ttu-id="9d8d6-122">**New-AzureBatchCertificate**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-122">**New-AzureBatchCertificate**</span></span>
- <span data-ttu-id="9d8d6-123">Parametern `Password` ersätts av en säker sträng</span><span class="sxs-lookup"><span data-stu-id="9d8d6-123">Parameter `Password` being replaced in favor of a Secure string</span></span>

```powershell
# Old
New-AzureBatchCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureBatchCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchcomputenodeuser"></a><span data-ttu-id="9d8d6-124">**New-AzureBatchComputeNodeUser**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-124">**New-AzureBatchComputeNodeUser**</span></span>
- <span data-ttu-id="9d8d6-125">Parametern `Password` ersätts av en säker sträng</span><span class="sxs-lookup"><span data-stu-id="9d8d6-125">Parameter `Password` being replaced in favor of a Secure string</span></span>

```powershell
# Old
New-AzureBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
New-AzureBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermbatchcomputenodeuser"></a><span data-ttu-id="9d8d6-126">**Set-AzureRmBatchComputeNodeUser**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-126">**Set-AzureRmBatchComputeNodeUser**</span></span>
- <span data-ttu-id="9d8d6-127">Parametern `Password` ersätts av en säker sträng</span><span class="sxs-lookup"><span data-stu-id="9d8d6-127">Parameter `Password` being replaced in favor of a Secure string</span></span>

```powershell
# Old
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchtask"></a><span data-ttu-id="9d8d6-128">**New-AzureBatchTask**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-128">**New-AzureBatchTask**</span></span>
 - <span data-ttu-id="9d8d6-129">Växeln `RunElevated` har tagits bort och ersatts med `UserIdentity`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-129">Removed the `RunElevated` switch and replaced it with `UserIdentity`.</span></span>

```powershell
# Old
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -RunElevated $TRUE

# New
$autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
$userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -UserIdentity $userIdentity
```

<span data-ttu-id="9d8d6-130">Detta påverkar även egenskapen `RunElevated` på `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask` och `PSJobReleaseTask`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-130">This additionally impacts the `RunElevated` property on `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask`, and `PSJobReleaseTask`.</span></span>

### <a name="psmultiinstancesettings"></a><span data-ttu-id="9d8d6-131">**PSMultiInstanceSettings**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-131">**PSMultiInstanceSettings**</span></span>

- <span data-ttu-id="9d8d6-132">`PSMultiInstanceSettings`-konstruktorn tar inte längre en obligatorisk `numberOfInstances`-parameter. Den tar i stället en nödvändig `coordinationCommandLine`-parameter.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-132">`PSMultiInstanceSettings` constructor no longer takes a required `numberOfInstances` parameter, instead it takes a required `coordinationCommandLine` parameter.</span></span>

```powershell
# Old
$settings = New-Object Microsoft.Azure.Commands.Batch.Models.PSMultiInstanceSettings -ArgumentList @(2)
$settings.CoordinationCommandLine = "cmd /c echo hello"
New-AzureBatchTask [other parameters] -MultiInstanceSettings $settings

# New
$settings = New-Object Microsoft.Azure.Commands.Batch.Models.PSMultiInstanceSettings -ArgumentList @("cmd /c echo hello", 2)
New-AzureBatchTask [other parameters] -MultiInstanceSettings $settings
```

### <a name="get-azurebatchtask"></a><span data-ttu-id="9d8d6-133">**Get-AzureBatchTask**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-133">**Get-AzureBatchTask**</span></span>
 - <span data-ttu-id="9d8d6-134">Egenskapen `RunElevated` har tagits bort på `PSCloudTask`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-134">Removed the `RunElevated` property on `PSCloudTask`.</span></span> <span data-ttu-id="9d8d6-135">Egenskapen `UserIdentity` har lagts till för att ersätta `RunElevated`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-135">The `UserIdentity` property has been added to replace `RunElevated`.</span></span>

```powershell
# Old
$task = Get-AzureBatchTask [parameters]
$task.RunElevated

# New
$task = Get-AzureBatchTask [parameters]
$task.UserIdentity.AutoUser.ElevationLevel
```

<span data-ttu-id="9d8d6-136">Detta påverkar även egenskapen `RunElevated` på `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask` och `PSJobReleaseTask`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-136">This additionally impacts the `RunElevated` property on `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask`, and `PSJobReleaseTask`.</span></span>

### <a name="multiple-types"></a><span data-ttu-id="9d8d6-137">**Flera typer**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-137">**Multiple types**</span></span>

- <span data-ttu-id="9d8d6-138">Egenskapen `SchedulingError` på `PSExitConditions` har bytt namn till `PreProcessingError`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-138">Renamed the `SchedulingError` property on `PSExitConditions` to `PreProcessingError`.</span></span>

```powershell
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.PreProcessingError
```

### <a name="multiple-types"></a><span data-ttu-id="9d8d6-139">**Flera typer**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-139">**Multiple types**</span></span>

- <span data-ttu-id="9d8d6-140">Egenskapen `SchedulingError` på `PSJobPreparationTaskExecutionInformation` har bytt namn till `PSJobReleaseTaskExecutionInformation`, `PSStartTaskInformation`, `PSSubtaskInformation` och `PSTaskExecutionInformation` till `FailureInformation`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-140">Renamed the `SchedulingError` property on `PSJobPreparationTaskExecutionInformation`, `PSJobReleaseTaskExecutionInformation`, `PSStartTaskInformation`, `PSSubtaskInformation`, and `PSTaskExecutionInformation` to `FailureInformation`.</span></span>
  - <span data-ttu-id="9d8d6-141">`FailureInformation` returneras när ett fel uppstår i uppgiften.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-141">`FailureInformation` is returned any time there is a task failure.</span></span> <span data-ttu-id="9d8d6-142">Det här omfattar alla tidigare fall av schemaläggningsfel, slutkoder för aktiviteter utan nollor och fel vid uppladdning av filer från den nya funktionen för utdatafiler.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-142">This includes all previous scheduling error cases, as well as nonzero task exit codes, and file upload failures from the new output files feature.</span></span>
  - <span data-ttu-id="9d8d6-143">Det här är strukturerat på samma sätt som tidigare, så du behöver inte göra några ändringar i koden när du använder den här typen.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-143">This is structured the same as before, so no code change is needed when using this type.</span></span>

```powershell
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.FailureInformation
```

<span data-ttu-id="9d8d6-144">Det här påverkar dessutom: Get-AzureBatchPool, Get-AzureBatchSubtask och Get-AzureBatchJobPreparationAndReleaseTaskStatus</span><span class="sxs-lookup"><span data-stu-id="9d8d6-144">This additionally impacts: Get-AzureBatchPool, Get-AzureBatchSubtask, and Get-AzureBatchJobPreparationAndReleaseTaskStatus</span></span>

### <a name="new-azurebatchpool"></a><span data-ttu-id="9d8d6-145">**New-AzureBatchPool**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-145">**New-AzureBatchPool**</span></span>
 - <span data-ttu-id="9d8d6-146">`TargetDedicated` har tagits bort och ersatts med `TargetDedicatedComputeNodes` och `TargetLowPriorityComputeNodes`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-146">Removed `TargetDedicated` and replaced it with `TargetDedicatedComputeNodes` and `TargetLowPriorityComputeNodes`.</span></span>
 - <span data-ttu-id="9d8d6-147">`TargetDedicatedComputeNodes` har ett alias `TargetDedicated`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-147">`TargetDedicatedComputeNodes` has an alias `TargetDedicated`.</span></span>

```powershell
# Old
New-AzureBatchPool [other parameters] [-TargetDedicated <Int32>]

# New
New-AzureBatchPool [other parameters] [-TargetDedicatedComputeNodes <Int32>] [-TargetLowPriorityComputeNodes <Int32>]
```

<span data-ttu-id="9d8d6-148">Det här påverkar dessutom: Start-AzureBatchPoolResize</span><span class="sxs-lookup"><span data-stu-id="9d8d6-148">This also impacts: Start-AzureBatchPoolResize</span></span>

### <a name="get-azurebatchpool"></a><span data-ttu-id="9d8d6-149">**Get-AzureBatchPool**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-149">**Get-AzureBatchPool**</span></span>
 - <span data-ttu-id="9d8d6-150">Egenskaperna `TargetDedicated` och `CurrentDedicated` på `PSCloudPool` har bytt namn till `TargetDedicatedComputeNodes` och `CurrentDedicatedComputeNodes`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-150">Renamed the `TargetDedicated` and `CurrentDedicated` properties on `PSCloudPool` to `TargetDedicatedComputeNodes` and `CurrentDedicatedComputeNodes`.</span></span>

```powershell
# Old
$pool = Get-AzureBatchPool [parameters]
$pool.TargetDedicated
$pool.CurrentDedicated

# New
$pool = Get-AzureBatchPool [parameters]
$pool.TargetDedicatedComputeNodes
$pool.CurrentDedicatedComputeNodes
```

### <a name="type-pscloudpool"></a><span data-ttu-id="9d8d6-151">**PSCloudPool-typ**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-151">**Type PSCloudPool**</span></span>

- <span data-ttu-id="9d8d6-152">`ResizeError` har bytt namn till `ResizeErrors` på `PSCloudPool` och det är nu en samling.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-152">Renamed `ResizeError` to `ResizeErrors` on `PSCloudPool`, and it is now a collection.</span></span>

```powershell
# Old
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeError

# New
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeErrors[0]
```

### <a name="new-azurebatchjob"></a><span data-ttu-id="9d8d6-153">**New-AzureBatchJob**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-153">**New-AzureBatchJob**</span></span>
- <span data-ttu-id="9d8d6-154">Egenskapen `TargetDedicated` på `PSPoolSpecification` har bytt namn till `TargetDedicatedComputeNodes`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-154">Renamed the `TargetDedicated` property on `PSPoolSpecification` to `TargetDedicatedComputeNodes`.</span></span>

```powershell
# Old
$poolInfo = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
$poolInfo.AutoPoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification.TargetDedicated = 5
New-AzureBatchJob [other parameters] -PoolInformation $poolInfo

# New
$poolInfo = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
$poolInfo.AutoPoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification.TargetDedicatedComputeNodes = 5
New-AzureBatchJob [other parameters] -PoolInformation $poolInfo
```

### <a name="get-azurebatchnodefile"></a><span data-ttu-id="9d8d6-155">**Get-AzureBatchNodeFile**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-155">**Get-AzureBatchNodeFile**</span></span>
 - <span data-ttu-id="9d8d6-156">`Name` har tagits bort och ersatts med `Path`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-156">Removed `Name` and replaced it with `Path`.</span></span>
 - <span data-ttu-id="9d8d6-157">`Path` har ett alias `Name`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-157">`Path` has an alias `Name`.</span></span>

```powershell
# Old
Get-AzureBatchNodeFile [other parameters] [[-Name] <String>]

# New
Get-AzureBatchNodeFile [other parameters] [[-Path] <String>]
```

<span data-ttu-id="9d8d6-158">Det här påverkar dessutom: Get-AzureBatchNodeFileContent, Remove-AzureBatchNodeFile</span><span class="sxs-lookup"><span data-stu-id="9d8d6-158">This also impacts: Get-AzureBatchNodeFileContent, Remove-AzureBatchNodeFile</span></span>

### <a name="type-psnodefile"></a><span data-ttu-id="9d8d6-159">Typen **PSNodeFile**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-159">Type **PSNodeFile**</span></span>

 - <span data-ttu-id="9d8d6-160">Egenskapen `Name` på `PSNodeFile` har bytt namn till `Path`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-160">Renamed the `Name` property on `PSNodeFile` to `Path`.</span></span>

```powershell
# Old
$file = Get-AzureBatchNodeFile [parameters]
$file.Name

# New
$file = Get-AzureBatchNodeFile [parameters]
$file.Path
```

### <a name="get-azurebatchsubtask"></a><span data-ttu-id="9d8d6-161">**Get-AzureBatchSubtask**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-161">**Get-AzureBatchSubtask**</span></span>
- <span data-ttu-id="9d8d6-162">Egenskaperna `PreviousState` och `State` för `PSSubtaskInformation` är inte längre är av typen `TaskState`.De är istället av typen `SubtaskState`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-162">The `PreviousState` and `State` properties of `PSSubtaskInformation` are no longer of type `TaskState`, instead they are of type `SubtaskState`.</span></span>
  - <span data-ttu-id="9d8d6-163">Till skillnad från `TaskState` har inte `SubtaskState` något `Active`-värde eftersom det inte är möjligt för underuppgifter att vara i tillståndet `Active`.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-163">Unlike `TaskState`, `SubtaskState` has no `Active` value, since it is not possible for subtasks to be in an `Active` state.</span></span>

```powershell
# Old
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.TaskState.Running) { }

# New
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.SubtaskState.Running) { }
```

## <a name="breaking-changes-to-compute-cmdlets"></a><span data-ttu-id="9d8d6-164">Större ändringar i Compute-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-164">Breaking changes to Compute cmdlets</span></span>

### <a name="set-azurermvmaccessextension"></a><span data-ttu-id="9d8d6-165">**Set-AzureRmVMAccessExtension**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-165">**Set-AzureRmVMAccessExtension**</span></span>
- <span data-ttu-id="9d8d6-166">Parametrarna ”UserName” och ”Password” ersätts av PSCredential</span><span class="sxs-lookup"><span data-stu-id="9d8d6-166">Parameters "UserName" and "Password" are being replaced in favor of a PSCredential</span></span>

```powershell
# Old
Set-AzureRmVMAccessExtension [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
Set-AzureRmVMAccessExtension [other required parameters] -Credential $PSCredential
```

## <a name="breaking-changes-to-eventhub-cmdlets"></a><span data-ttu-id="9d8d6-167">Större ändringar i EventHub-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-167">Breaking changes to EventHub cmdlets</span></span>

### <a name="new-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-168">**New-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-168">**New-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-169">Cmdleten ”New-AzureRmEventHubNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-169">The 'New-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-170">Använd cmdleten ”New-AzureRmEventHubAuthorizationRule”</span><span class="sxs-lookup"><span data-stu-id="9d8d6-170">Please use the 'New-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="get-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-171">**Get-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-171">**Get-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-172">Cmdleten ”Get-AzureRmEventHubNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-172">The 'Get-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-173">Använd cmdleten ”Get-AzureRmEventHubAuthorizationRule”</span><span class="sxs-lookup"><span data-stu-id="9d8d6-173">Please use the 'Get-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="set-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-174">**Set-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-174">**Set-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-175">Cmdleten ”Set-AzureRmEventHubNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-175">The 'Set-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-176">Använd cmdleten ”Set-AzureRmEventHubAuthorizationRule”</span><span class="sxs-lookup"><span data-stu-id="9d8d6-176">Please use the 'Set-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="remove-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-177">**Remove-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-177">**Remove-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-178">Cmdleten ”Remove-AzureRmEventHubNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-178">The 'Remove-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-179">Använd cmdleten ”Remove-AzureRmEventHubAuthorizationRule”</span><span class="sxs-lookup"><span data-stu-id="9d8d6-179">Please use the 'Remove-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="new-azurermeventhubnamespacekey"></a><span data-ttu-id="9d8d6-180">**New-AzureRmEventHubNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-180">**New-AzureRmEventHubNamespaceKey**</span></span>
- <span data-ttu-id="9d8d6-181">Cmdleten ”New-AzureRmEventHubNamespaceKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-181">The 'New-AzureRmEventHubNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-182">Använd cmdleten ”New-AzureRmEventHubKey”</span><span class="sxs-lookup"><span data-stu-id="9d8d6-182">Please use the 'New-AzureRmEventHubKey' cmdlet</span></span>
    
### <a name="get-azurermeventhubnamespacekey"></a><span data-ttu-id="9d8d6-183">**Get-AzureRmEventHubNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-183">**Get-AzureRmEventHubNamespaceKey**</span></span>
- <span data-ttu-id="9d8d6-184">Cmdleten ”Get-AzureRmEventHubNamespaceKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-184">The 'Get-AzureRmEventHubNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-185">Använd cmdleten ”Get-AzureRmEventHubKey”</span><span class="sxs-lookup"><span data-stu-id="9d8d6-185">Please use the 'Get-AzureRmEventHubKey' cmdlet</span></span>
    
### <a name="new-azurermeventhubnamespace"></a><span data-ttu-id="9d8d6-186">**New-AzureRmEventHubNamespace**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-186">**New-AzureRmEventHubNamespace**</span></span>
- <span data-ttu-id="9d8d6-187">Egenskaperna ”Status” och ”Enabled” kommer att tas bort från NamespceAttributes.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-187">The property 'Status' and 'Enabled' from the NamespceAttributes will be removed.</span></span> 

```powershell
# Old
# The $namespace has Status and Enabled property  
$namespace = New-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property    
$namespace = Get-AzureRmEventHubNamespace <parameters>
```
    
### <a name="get-azurermeventhubnamespace"></a><span data-ttu-id="9d8d6-188">**Get-AzureRmEventHubNamespace**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-188">**Get-AzureRmEventHubNamespace**</span></span>
- <span data-ttu-id="9d8d6-189">Egenskaperna ”Status” och ”Enabled” kommer att tas bort från NamespceAttributes.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-189">The property 'Status' and 'Enabled' from the NamespceAttributes will be removed.</span></span> 

```powershell
# Old
# The $namespace has Status and Enabled property 
$namespace = Get-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property    
$namespace = Get-AzureRmEventHubNamespace <parameters>
```
    
### <a name="set-azurermeventhubnamespace"></a><span data-ttu-id="9d8d6-190">**Set-AzureRmEventHubNamespace**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-190">**Set-AzureRmEventHubNamespace**</span></span>
- <span data-ttu-id="9d8d6-191">Egenskaperna ”Status” och ”Enabled” kommer att tas bort från NamespceAttributes.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-191">The property 'Status' and 'Enabled' from the NamespceAttributes will be removed.</span></span> 

```powershell
# Old
# The $namespace has Status and Enabled property 
$namespace = Set-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property    
$namespace = Set-AzureRmEventHubNamespace <parameters>
``` 
  
### <a name="new-azurermeventhubconsumergroup"></a><span data-ttu-id="9d8d6-192">**New-AzureRmEventHubConsumerGroup**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-192">**New-AzureRmEventHubConsumerGroup**</span></span>
- <span data-ttu-id="9d8d6-193">Egenskapen ”EventHubPath” kommer att tas bort från ConsumerGroupAttributes.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-193">The property 'EventHubPath' from the ConsumerGroupAttributes will be removed.</span></span>

```powershell
# Old
# The $consumergroup has EventHubPath property 
$consumergroup = New-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property    
$consumergroup = New-AzureRmEventHubConsumerGroup <parameters>
```
    
### <a name="set-azurermeventhubconsumergroup"></a><span data-ttu-id="9d8d6-194">**Set-AzureRmEventHubConsumerGroup**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-194">**Set-AzureRmEventHubConsumerGroup**</span></span>
- <span data-ttu-id="9d8d6-195">Egenskapen ”EventHubPath” kommer att tas bort från ConsumerGroupAttributes.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-195">The property 'EventHubPath' from the ConsumerGroupAttributes will be removed.</span></span>

```powershell
# Old
# The $consumergroup has EventHubPath property 
$consumergroup = Set-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property    
$consumergroup = Set-AzureRmEventHubConsumerGroup <parameters>
```
    
### <a name="get-azurermeventhubconsumergroup"></a><span data-ttu-id="9d8d6-196">**Get-AzureRmEventHubConsumerGroup**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-196">**Get-AzureRmEventHubConsumerGroup**</span></span>
- <span data-ttu-id="9d8d6-197">Egenskapen ”EventHubPath” kommer att tas bort från ConsumerGroupAttributes.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-197">The property 'EventHubPath' from the ConsumerGroupAttributes will be removed.</span></span>

```powershell
# Old
# The $consumergroup has EventHubPath property 
$consumergroup = Get-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property    
$consumergroup = Get-AzureRmEventHubConsumerGroup <parameters>
```

## <a name="breaking-changes-to-insights-cmdlets"></a><span data-ttu-id="9d8d6-198">Större ändringar i Insights-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-198">Breaking changes to Insights cmdlets</span></span>

### <a name="add-azurermlogalertrule"></a><span data-ttu-id="9d8d6-199">**Add-AzureRMLogAlertRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-199">**Add-AzureRMLogAlertRule**</span></span>
- <span data-ttu-id="9d8d6-200">Cmdleten **Add-AzureRMLogAlertRule** har gjorts inaktuell</span><span class="sxs-lookup"><span data-stu-id="9d8d6-200">The **Add-AzureRMLogAlertRule** cmdlet has been deprecated</span></span>
- <span data-ttu-id="9d8d6-201">Efter den 1 oktober kommer den här cmdleten inte längre att ha någon effekt eftersom den här funktionen kommer att övergå till aktivitetsloggaviseringar.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-201">After October 1st using this cmdlet will no longer have any effect as this functionality is being transitioned to Activity Log Alerts.</span></span> <span data-ttu-id="9d8d6-202">Mer information finns i https://aka.ms/migratemealerts.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-202">Please see https://aka.ms/migratemealerts for more information.</span></span>

### <a name="get-azurermusage"></a><span data-ttu-id="9d8d6-203">**Get-AzureRMUsage**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-203">**Get-AzureRMUsage**</span></span>
- <span data-ttu-id="9d8d6-204">Cmdleten **Get-AzureRMUsage** har gjorts inaktuell</span><span class="sxs-lookup"><span data-stu-id="9d8d6-204">The **Get-AzureRMUsage** cmdlet has been deprecated</span></span>

### <a name="get-azurermalerthistory--get-azurermautoscalehistory--get-azurermlogs"></a><span data-ttu-id="9d8d6-205">**Get-AzureRmAlertHistory** / **Get-AzureRmAutoscaleHistory** / **Get-AzureRmLogs**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-205">**Get-AzureRmAlertHistory** / **Get-AzureRmAutoscaleHistory** / **Get-AzureRmLogs**</span></span>
- <span data-ttu-id="9d8d6-206">Ändring i utdata: Fältet EventChannels från EventData-objektet (som returneras av de här cmdletarna) kommer att bli inaktuellt eftersom det nu returnerar ett konstant värde (Admin, Åtgärd.)</span><span class="sxs-lookup"><span data-stu-id="9d8d6-206">Output change: The field EventChannels from the EventData object (returned by these cmdlets) is being deprecated since it now returns a constant value (Admin,Operation.)</span></span>

### <a name="get-azurermalertrule"></a><span data-ttu-id="9d8d6-207">**Get-AzureRmAlertRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-207">**Get-AzureRmAlertRule**</span></span>
- <span data-ttu-id="9d8d6-208">Ändring i utdata: Utdata från den här cmdleten jämnas ut. Det innebär att egenskapsfältet kommer att tas bort för att förbättra användarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-208">Output change: The output of this cmdlet will be flattened, i.e. elimination of the properties field, to improve the user experience.</span></span>

```powershell
# Old
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -Foreground Red "Error updating alert rule"
    Write-Host $rules[0].Id
    Write-Host $rules[0].Properties.IsEnabled
    Write-Host $rules[0].Properties.Condition
}

# New
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -Foreground red "Error updating alert rule"
    Write-Host $rules[0].Id

    # Properties will remain for a while
    Write-Host $rules[0].Properties.IsEnabled
      
    # But the properties will be at the top level too. Later Properties will be removed
    Write-Host $rules[0].IsEnabled
    Write-Host $rules[0].Condition
}
```

### <a name="get-azurermautoscalesetting"></a><span data-ttu-id="9d8d6-209">**Get-AzureRmAutoscaleSetting**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-209">**Get-AzureRmAutoscaleSetting**</span></span>
- <span data-ttu-id="9d8d6-210">Ändring i utdata: Fältet AutoscaleSettingResourceName kommer att bli inaktuellt eftersom det alltid är samma som fältet Name.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-210">Output change: The AutoscaleSettingResourceName field will be deprecated since it always equals the Name field.</span></span>

```powershell
# Old
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
if ($s1.AutoscaleSettingResourceName -ne $s1.Name)
{
    Write-Host "There is something wrong with the name"
}

# New
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
    
# there won't be a AutoscaleSettingResourceName
Write-Host $s1.Name    
```

### <a name="remove-azurermalertrule--remove-azurermlogprofile"></a><span data-ttu-id="9d8d6-211">**Remove-AzureRmAlertRule** / **Remove-AzureRmLogProfile**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-211">**Remove-AzureRmAlertRule** / **Remove-AzureRmLogProfile**</span></span>
- <span data-ttu-id="9d8d6-212">Ändring i utdata: Typen av utdata kommer att ändras så att ett enda objekt som innehåller ID för begäran och statuskod returneras.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-212">Output change: The type of the output will change to return a single object containing the request Id and the status code.</span></span>

```powershell
# Old
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name $ruleName
if ($s1 -ne $null)
{
    $r = $s1[0].RequestId
    $s = $s1[0].StatusCode
}

# New
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name $ruleName
$r = $s1.RequestId
$s = $s1.StatusCode
```

## <a name="breaking-changes-to-network-cmdlets"></a><span data-ttu-id="9d8d6-213">Större ändringar i Network-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-213">Breaking changes to Network cmdlets</span></span>

### <a name="add-azurermapplicationgatewaysslcertificate"></a><span data-ttu-id="9d8d6-214">**Add-AzureRmApplicationGatewaySslCertificate**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-214">**Add-AzureRmApplicationGatewaySslCertificate**</span></span>
- <span data-ttu-id="9d8d6-215">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-215">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermapplicationgatewaysslcertificate"></a><span data-ttu-id="9d8d6-216">**New-AzureRmApplicationGatewaySslCertificate**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-216">**New-AzureRmApplicationGatewaySslCertificate**</span></span>
- <span data-ttu-id="9d8d6-217">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-217">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapplicationgatewaysslcertificate"></a><span data-ttu-id="9d8d6-218">**Set-AzureRmApplicationGatewaySslCertificate**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-218">**Set-AzureRmApplicationGatewaySslCertificate**</span></span>
- <span data-ttu-id="9d8d6-219">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-219">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-resources-cmdlets"></a><span data-ttu-id="9d8d6-220">Större ändringar i Resources-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-220">Breaking changes to Resources cmdlets</span></span>

### <a name="new-azurermadappcredential"></a><span data-ttu-id="9d8d6-221">**New-AzureRmADAppCredential**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-221">**New-AzureRmADAppCredential**</span></span>
- <span data-ttu-id="9d8d6-222">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-222">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADAppCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADAppCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadapplication"></a><span data-ttu-id="9d8d6-223">**New-AzureRmADApplication**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-223">**New-AzureRmADApplication**</span></span>
- <span data-ttu-id="9d8d6-224">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-224">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADApplication [other required parameters] -Password "plain-text string"

# New
New-AzureRmADApplication [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadserviceprincipal"></a><span data-ttu-id="9d8d6-225">**New-AzureRmADServicePrincipal**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-225">**New-AzureRmADServicePrincipal**</span></span>
- <span data-ttu-id="9d8d6-226">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-226">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADServicePrincipal [other required parameters] -Password "plain-text string"

# New
New-AzureRmADServicePrincipal [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadspcredential"></a><span data-ttu-id="9d8d6-227">**New-AzureRmADSpCredential**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-227">**New-AzureRmADSpCredential**</span></span>
- <span data-ttu-id="9d8d6-228">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-228">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADSpCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADSpCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermaduser"></a><span data-ttu-id="9d8d6-229">**New-AzureRmADUser**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-229">**New-AzureRmADUser**</span></span>
- <span data-ttu-id="9d8d6-230">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-230">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermaduser"></a><span data-ttu-id="9d8d6-231">**Set-AzureRmADUser**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-231">**Set-AzureRmADUser**</span></span>
- <span data-ttu-id="9d8d6-232">Parametern ”Password” ersätts av SecureString</span><span class="sxs-lookup"><span data-stu-id="9d8d6-232">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Set-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-servicebus-cmdlets"></a><span data-ttu-id="9d8d6-233">Större ändringar i ServiceBus-cmdletar</span><span class="sxs-lookup"><span data-stu-id="9d8d6-233">Breaking changes to ServiceBus cmdlets</span></span>

### <a name="get-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="9d8d6-234">**Get-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-234">**Get-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-235">Cmdleten ”Get-AzureRmServiceBusTopicAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-235">The 'Get-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-236">Använd cmdleten ”Get-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-236">Please use the 'Get-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>    

### <a name="get-azurermservicebustopickey"></a><span data-ttu-id="9d8d6-237">**Get-AzureRmServiceBusTopicKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-237">**Get-AzureRmServiceBusTopicKey**</span></span>
- <span data-ttu-id="9d8d6-238">Cmdleten ”Get-AzureRmServiceBusTopicKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-238">The 'Get-AzureRmServiceBusTopicKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-239">Använd cmdleten ”Get-AzureRmServiceBusKey”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-239">Please use the 'Get-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="new-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="9d8d6-240">**New-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-240">**New-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-241">Cmdleten ”New-AzureRmServiceBusTopicAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-241">The 'New-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-242">Använd cmdleten ”New-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-242">Please use the 'New-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="new-azurermservicebustopickey"></a><span data-ttu-id="9d8d6-243">**New-AzureRmServiceBusTopicKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-243">**New-AzureRmServiceBusTopicKey**</span></span>
- <span data-ttu-id="9d8d6-244">Cmdleten ”New-AzureRmServiceBusTopicKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-244">The 'New-AzureRmServiceBusTopicKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-245">Använd cmdleten ”New-AzureRmServiceBusKey”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-245">Please use the 'New-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="remove-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="9d8d6-246">**Remove-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-246">**Remove-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-247">Cmdleten ”Remove-AzureRmServiceBusTopicAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-247">The 'Remove-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-248">Använd cmdleten ”Remove-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-248">Please use the 'Remove-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="set-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="9d8d6-249">**Set-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-249">**Set-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-250">Cmdleten ”Set-AzureRmServiceBusTopicAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-250">The 'Set-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-251">Använd cmdleten ”Set-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-251">Please use the 'Set-AzureRmServiceBusAuthorizationRule'cmdlet.</span></span>

### <a name="new-azurermservicebusnamespacekey"></a><span data-ttu-id="9d8d6-252">**New-AzureRmServiceBusNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-252">**New-AzureRmServiceBusNamespaceKey**</span></span>
- <span data-ttu-id="9d8d6-253">Cmdleten ”New-AzureRmServiceBusNamespaceKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-253">The 'New-AzureRmServiceBusNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-254">Använd cmdleten ”New-AzureRmServiceBusKey”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-254">Please use the 'New-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="get-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="9d8d6-255">**Get-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-255">**Get-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-256">Cmdleten ”Get-AzureRmServiceBusQueueAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-256">The 'Get-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-257">Använd cmdleten ”Get-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-257">Please use the 'Get-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="get-azurermservicebusqueuekey"></a><span data-ttu-id="9d8d6-258">**Get-AzureRmServiceBusQueueKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-258">**Get-AzureRmServiceBusQueueKey**</span></span>
- <span data-ttu-id="9d8d6-259">Cmdleten ”Get-AzureRmServiceBusQueueKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-259">The 'Get-AzureRmServiceBusQueueKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-260">Använd cmdleten ”Get-AzureRmServiceBusKey”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-260">Please use the 'Get-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="new-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="9d8d6-261">**New-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-261">**New-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-262">Cmdleten ”New-AzureRmServiceBusQueueAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-262">The 'New-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-263">Använd cmdleten ”New-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-263">Please use the 'New-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="new-azurermservicebusqueuekey"></a><span data-ttu-id="9d8d6-264">**New-AzureRmServiceBusQueueKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-264">**New-AzureRmServiceBusQueueKey**</span></span>
- <span data-ttu-id="9d8d6-265">Cmdleten ”New-AzureRmServiceBusQueueKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-265">The 'New-AzureRmServiceBusQueueKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-266">Använd cmdleten ”New-AzureRmServiceBusKey”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-266">Please use the 'New-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="remove-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="9d8d6-267">**Remove-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-267">**Remove-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-268">Cmdleten ”Remove-AzureRmServiceBusQueueAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-268">The 'Remove-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-269">Använd cmdleten ”GRemove-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-269">Please use the 'GRemove-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="set-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="9d8d6-270">**Set-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-270">**Set-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-271">Cmdleten ”Set-AzureRmServiceBusQueueAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-271">The 'Set-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-272">Använd cmdleten ”Set-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-272">Please use the 'Set-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="get-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-273">**Get-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-273">**Get-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-274">Cmdleten ”Get-AzureRmServiceBusNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-274">The 'Get-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-275">Använd cmdleten ”Get-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-275">Please use the 'Get-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="get-azurermservicebusnamespacekey"></a><span data-ttu-id="9d8d6-276">**Get-AzureRmServiceBusNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-276">**Get-AzureRmServiceBusNamespaceKey**</span></span>
- <span data-ttu-id="9d8d6-277">Cmdleten ”Get-AzureRmServiceBusNamespaceKey” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-277">The 'Get-AzureRmServiceBusNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-278">Använd cmdleten ”Get-AzureRmServiceBusKey”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-278">Please use the 'Get-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="new-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-279">**New-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-279">**New-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-280">Cmdleten ”New-AzureRmServiceBusNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-280">The 'New-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-281">Använd cmdleten ”New-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-281">Please use the 'New-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="remove-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-282">**Remove-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-282">**Remove-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-283">Cmdleten ”Remove-AzureRmServiceBusNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-283">The 'Remove-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-284">Använd cmdleten ”Remove-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-284">Please use the 'Remove-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="set-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="9d8d6-285">**Set-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-285">**Set-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="9d8d6-286">Cmdleten ”Set-AzureRmServiceBusNamespaceAuthorizationRule” har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-286">The 'Set-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="9d8d6-287">Använd cmdleten ”Set-AzureRmServiceBusAuthorizationRule”.</span><span class="sxs-lookup"><span data-stu-id="9d8d6-287">Please use the 'Set-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="type-namespaceattributes"></a><span data-ttu-id="9d8d6-288">**Typen NamespaceAttributes**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-288">**Type NamespaceAttributes**</span></span>
- <span data-ttu-id="9d8d6-289">Följande egenskaper har tagits bort</span><span class="sxs-lookup"><span data-stu-id="9d8d6-289">The following properties have been removed</span></span>
    - <span data-ttu-id="9d8d6-290">Enabled</span><span class="sxs-lookup"><span data-stu-id="9d8d6-290">Enabled</span></span>
    - <span data-ttu-id="9d8d6-291">Status</span><span class="sxs-lookup"><span data-stu-id="9d8d6-291">Status</span></span>
   
```powershell
# Old
# The $namespace has Status and Enabled property 
$namespace = Get-AzureRmServiceBusNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Enabled and Status properties    
$namespace = Get-AzureRmServiceBusNamespace <parameters>
```

### <a name="type-queueattribute"></a><span data-ttu-id="9d8d6-292">**Typen QueueAttribute**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-292">**Type QueueAttribute**</span></span>
- <span data-ttu-id="9d8d6-293">Följande egenskaper har angetts som föråldrade:</span><span class="sxs-lookup"><span data-stu-id="9d8d6-293">The following properties are marked as obsolete:</span></span>
    - <span data-ttu-id="9d8d6-294">EnableBatchedOperations</span><span class="sxs-lookup"><span data-stu-id="9d8d6-294">EnableBatchedOperations</span></span>
    - <span data-ttu-id="9d8d6-295">EntityAvailabilityStatus</span><span class="sxs-lookup"><span data-stu-id="9d8d6-295">EntityAvailabilityStatus</span></span>
    - <span data-ttu-id="9d8d6-296">IsAnonymousAccessible</span><span class="sxs-lookup"><span data-stu-id="9d8d6-296">IsAnonymousAccessible</span></span>
    - <span data-ttu-id="9d8d6-297">SupportOrdering</span><span class="sxs-lookup"><span data-stu-id="9d8d6-297">SupportOrdering</span></span>

```powershell
# Old
# The $queue has EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties
$queue = Get-AzureRmServiceBusQueue <parameters>
$queue.EntityAvailabilityStatus
$queue.EnableBatchedOperations
$queue.IsAnonymousAccessible
$queue.SupportOrdering  

# New
# The call remains the same, but the returned values Queue object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties    
$queue = Get-AzureRmServiceBusQueue <parameters>
```
   
### <a name="type-topicattribute"></a><span data-ttu-id="9d8d6-298">**Typen TopicAttribute**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-298">**Type TopicAttribute**</span></span>
- <span data-ttu-id="9d8d6-299">Följande egenskaper har angetts som föråldrade:</span><span class="sxs-lookup"><span data-stu-id="9d8d6-299">The following properties are marked as obsolete:</span></span>
    - <span data-ttu-id="9d8d6-300">Plats</span><span class="sxs-lookup"><span data-stu-id="9d8d6-300">Location</span></span>
    - <span data-ttu-id="9d8d6-301">IsExpress</span><span class="sxs-lookup"><span data-stu-id="9d8d6-301">IsExpress</span></span>
    - <span data-ttu-id="9d8d6-302">IsAnonymousAccessible</span><span class="sxs-lookup"><span data-stu-id="9d8d6-302">IsAnonymousAccessible</span></span>
    - <span data-ttu-id="9d8d6-303">FilteringMessagesBeforePublishing</span><span class="sxs-lookup"><span data-stu-id="9d8d6-303">FilteringMessagesBeforePublishing</span></span>
    - <span data-ttu-id="9d8d6-304">EnableSubscriptionPartitioning</span><span class="sxs-lookup"><span data-stu-id="9d8d6-304">EnableSubscriptionPartitioning</span></span>
    - <span data-ttu-id="9d8d6-305">EntityAvailabilityStatus</span><span class="sxs-lookup"><span data-stu-id="9d8d6-305">EntityAvailabilityStatus</span></span>

```powershell
# Old
# The $topic has EntityAvailabilityStatus, EnableSubscriptionPartitioning, IsAnonymousAccessible, IsExpress, Location and FilteringMessagesBeforePublishing properties
$topic = Get-AzureRmServiceBusTopic <parameters>
$topic.EntityAvailabilityStatus
$topic.EnableSubscriptionPartitioning
$topic.IsAnonymousAccessible
$topic.IsExpress
$topic.FilteringMessagesBeforePublishing
$topic.Location

# New
# The call remains the same, but the returned values Topic object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties    
$topic = Get-AzureRmServiceBusTopic <parameters>
```
   
### <a name="type-subscriptionattribute"></a><span data-ttu-id="9d8d6-306">**Typen SubscriptionAttribute**</span><span class="sxs-lookup"><span data-stu-id="9d8d6-306">**Type SubscriptionAttribute**</span></span>
- <span data-ttu-id="9d8d6-307">Följande egenskaper har angetts som föråldrade</span><span class="sxs-lookup"><span data-stu-id="9d8d6-307">The following properties are marked as obsolete</span></span>
    - <span data-ttu-id="9d8d6-308">DeadLetteringOnFilterEvaluationExceptions</span><span class="sxs-lookup"><span data-stu-id="9d8d6-308">DeadLetteringOnFilterEvaluationExceptions</span></span>
    - <span data-ttu-id="9d8d6-309">EntityAvailabilityStatus</span><span class="sxs-lookup"><span data-stu-id="9d8d6-309">EntityAvailabilityStatus</span></span>
    - <span data-ttu-id="9d8d6-310">IsReadOnly</span><span class="sxs-lookup"><span data-stu-id="9d8d6-310">IsReadOnly</span></span>
    - <span data-ttu-id="9d8d6-311">Plats</span><span class="sxs-lookup"><span data-stu-id="9d8d6-311">Location</span></span>
   
```powershell
# Old
# The $subscription has EntityAvailabilityStatus, EnableSubscriptionPartitioning, IsAnonymousAccessible, IsExpress, Location and FilteringMessagesBeforePublishing properties
$subscription = Get-AzureRmServiceBussubscription <parameters>
$subscription.EntityAvailabilityStatus
$subscription.EnableSubscriptionPartitioning
$subscription.IsAnonymousAccessible
$subscription.IsExpress
$subscription.FilteringMessagesBeforePublishing
$subscription.Location

# New
# The call remains the same, but the returned values Topic object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties    
$subscription = Get-AzureRmServiceBussubscription <parameters>
```