---
title: 1 つの修復アクティビティの暴露デバイスを一覧表示する
description: 指定した修復タスクの公開されているデバイスに関する情報を返します。
keywords: apis、修復、修復 API、取得、修復タスク、公開されているデバイスの修復
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 92b5a93e86a20f36469d2b5cb606a8ddc2e97077
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241714"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="88428-104">1 つの修復アクティビティの暴露デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="88428-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88428-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="88428-105">**Applies to:**</span></span>

- [<span data-ttu-id="88428-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="88428-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88428-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88428-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="88428-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="88428-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="88428-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="88428-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="88428-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="88428-110">API Description</span></span>

<span data-ttu-id="88428-111">指定した修復タスクの公開されているデバイスに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="88428-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="88428-112">[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="88428-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="88428-113">修復タスクに関連付けられている公開されているデバイスの一覧 (ID)</span><span class="sxs-lookup"><span data-stu-id="88428-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="88428-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="88428-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="88428-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="88428-115">Permissions</span></span>

<span data-ttu-id="88428-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="88428-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="88428-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="88428-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="88428-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="88428-118">Permission type</span></span> | <span data-ttu-id="88428-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="88428-119">Permission</span></span> | <span data-ttu-id="88428-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="88428-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="88428-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="88428-121">Application</span></span> | <span data-ttu-id="88428-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="88428-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="88428-123">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="88428-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="88428-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="88428-124">Delegated (work or school account)</span></span> | <span data-ttu-id="88428-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="88428-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="88428-126">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="88428-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="88428-127">プロパティの詳細</span><span class="sxs-lookup"><span data-stu-id="88428-127">Properties details</span></span>

<span data-ttu-id="88428-128">プロパティ (id)</span><span class="sxs-lookup"><span data-stu-id="88428-128">Property (id)</span></span> | <span data-ttu-id="88428-129">データ型</span><span class="sxs-lookup"><span data-stu-id="88428-129">Data type</span></span> | <span data-ttu-id="88428-130">説明</span><span class="sxs-lookup"><span data-stu-id="88428-130">Description</span></span> | <span data-ttu-id="88428-131">例</span><span class="sxs-lookup"><span data-stu-id="88428-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="88428-132">id</span><span class="sxs-lookup"><span data-stu-id="88428-132">id</span></span> | <span data-ttu-id="88428-133">String</span><span class="sxs-lookup"><span data-stu-id="88428-133">String</span></span> | <span data-ttu-id="88428-134">デバイス ID</span><span class="sxs-lookup"><span data-stu-id="88428-134">Device ID</span></span> | <span data-ttu-id="88428-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="88428-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="88428-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="88428-136">computerDnsName</span></span> | <span data-ttu-id="88428-137">String</span><span class="sxs-lookup"><span data-stu-id="88428-137">String</span></span> | <span data-ttu-id="88428-138">デバイス名</span><span class="sxs-lookup"><span data-stu-id="88428-138">Device name</span></span> | <span data-ttu-id="88428-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="88428-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="88428-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="88428-140">osPlatform</span></span> | <span data-ttu-id="88428-141">String</span><span class="sxs-lookup"><span data-stu-id="88428-141">String</span></span> | <span data-ttu-id="88428-142">デバイス オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="88428-142">Device operating system</span></span> | <span data-ttu-id="88428-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="88428-143">WindowsServer2012R2</span></span>
<span data-ttu-id="88428-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="88428-144">rbacGroupName</span></span> | <span data-ttu-id="88428-145">String</span><span class="sxs-lookup"><span data-stu-id="88428-145">String</span></span> | <span data-ttu-id="88428-146">このデバイスが関連付けられているデバイス グループの名前</span><span class="sxs-lookup"><span data-stu-id="88428-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="88428-147">Servers</span><span class="sxs-lookup"><span data-stu-id="88428-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="88428-148">例</span><span class="sxs-lookup"><span data-stu-id="88428-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="88428-149">要求の例</span><span class="sxs-lookup"><span data-stu-id="88428-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="88428-150">応答の例</span><span class="sxs-lookup"><span data-stu-id="88428-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="88428-151">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="88428-151">See also</span></span>

- [<span data-ttu-id="88428-152">修復方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="88428-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="88428-153">ID による 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="88428-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="88428-154">すべての修復作業を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="88428-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="88428-155">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="88428-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="88428-156">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="88428-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
