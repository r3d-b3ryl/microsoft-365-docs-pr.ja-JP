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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772163"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="6d303-104">1 つの修復アクティビティの暴露デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="6d303-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d303-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6d303-105">**Applies to:**</span></span>

- [<span data-ttu-id="6d303-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6d303-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6d303-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d303-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6d303-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="6d303-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d303-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="6d303-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6d303-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="6d303-110">API Description</span></span>

<span data-ttu-id="6d303-111">指定した修復タスクの公開されているデバイスに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6d303-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="6d303-112">[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="6d303-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="6d303-113">修復タスクに関連付けられている公開されているデバイスの一覧 (ID)</span><span class="sxs-lookup"><span data-stu-id="6d303-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="6d303-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="6d303-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="6d303-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6d303-115">Permissions</span></span>

<span data-ttu-id="6d303-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6d303-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6d303-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6d303-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="6d303-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="6d303-118">Permission type</span></span> | <span data-ttu-id="6d303-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6d303-119">Permission</span></span> | <span data-ttu-id="6d303-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="6d303-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6d303-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6d303-121">Application</span></span> | <span data-ttu-id="6d303-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="6d303-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="6d303-123">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="6d303-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6d303-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="6d303-124">Delegated (work or school account)</span></span> | <span data-ttu-id="6d303-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="6d303-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="6d303-126">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="6d303-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="6d303-127">プロパティの詳細</span><span class="sxs-lookup"><span data-stu-id="6d303-127">Properties details</span></span>

<span data-ttu-id="6d303-128">プロパティ (id)</span><span class="sxs-lookup"><span data-stu-id="6d303-128">Property (id)</span></span> | <span data-ttu-id="6d303-129">データ型</span><span class="sxs-lookup"><span data-stu-id="6d303-129">Data type</span></span> | <span data-ttu-id="6d303-130">説明</span><span class="sxs-lookup"><span data-stu-id="6d303-130">Description</span></span> | <span data-ttu-id="6d303-131">例</span><span class="sxs-lookup"><span data-stu-id="6d303-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="6d303-132">id</span><span class="sxs-lookup"><span data-stu-id="6d303-132">id</span></span> | <span data-ttu-id="6d303-133">String</span><span class="sxs-lookup"><span data-stu-id="6d303-133">String</span></span> | <span data-ttu-id="6d303-134">デバイス ID</span><span class="sxs-lookup"><span data-stu-id="6d303-134">Device ID</span></span> | <span data-ttu-id="6d303-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="6d303-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="6d303-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="6d303-136">computerDnsName</span></span> | <span data-ttu-id="6d303-137">String</span><span class="sxs-lookup"><span data-stu-id="6d303-137">String</span></span> | <span data-ttu-id="6d303-138">デバイス名</span><span class="sxs-lookup"><span data-stu-id="6d303-138">Device name</span></span> | <span data-ttu-id="6d303-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="6d303-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="6d303-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="6d303-140">osPlatform</span></span> | <span data-ttu-id="6d303-141">String</span><span class="sxs-lookup"><span data-stu-id="6d303-141">String</span></span> | <span data-ttu-id="6d303-142">デバイス オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6d303-142">Device operating system</span></span> | <span data-ttu-id="6d303-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="6d303-143">WindowsServer2012R2</span></span>
<span data-ttu-id="6d303-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6d303-144">rbacGroupName</span></span> | <span data-ttu-id="6d303-145">String</span><span class="sxs-lookup"><span data-stu-id="6d303-145">String</span></span> | <span data-ttu-id="6d303-146">このデバイスが関連付けられているデバイス グループの名前</span><span class="sxs-lookup"><span data-stu-id="6d303-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="6d303-147">Servers</span><span class="sxs-lookup"><span data-stu-id="6d303-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="6d303-148">例</span><span class="sxs-lookup"><span data-stu-id="6d303-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="6d303-149">要求の例</span><span class="sxs-lookup"><span data-stu-id="6d303-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="6d303-150">応答の例</span><span class="sxs-lookup"><span data-stu-id="6d303-150">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6d303-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d303-151">See also</span></span>

- [<span data-ttu-id="6d303-152">修復方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="6d303-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="6d303-153">ID による 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="6d303-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="6d303-154">すべての修復作業を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="6d303-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="6d303-155">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="6d303-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="6d303-156">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="6d303-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
