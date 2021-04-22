---
title: 権限&前提条件 - 脅威と脆弱性の管理
description: 脅威と脆弱性の管理の使用を開始する前に、関連する構成とアクセス許可を持っている必要があります。
keywords: 脅威&管理アクセス許可の前提条件、脅威と脆弱性管理のアクセス許可の前提条件、Microsoft Defender for Endpoint TVM アクセス許可の前提条件、脆弱性管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0df348e3a5564720468d95d7b23578f9dcad9294
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935187"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="520a8-104">権限&前提条件 - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="520a8-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="520a8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="520a8-105">**Applies to:**</span></span>

- [<span data-ttu-id="520a8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="520a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="520a8-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="520a8-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="520a8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="520a8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="520a8-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="520a8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="520a8-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="520a8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="520a8-111">デバイスが次の条件を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="520a8-111">Ensure that your devices:</span></span>

- <span data-ttu-id="520a8-112">Microsoft Defender for Endpoint にオンボードされている</span><span class="sxs-lookup"><span data-stu-id="520a8-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="520a8-113">サポート [されているオペレーティング システムとプラットフォームを実行する](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="520a8-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="520a8-114">ネットワークに次の必須更新プログラムをインストールして展開し、脆弱性評価の検出率を向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="520a8-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="520a8-115">Release</span><span class="sxs-lookup"><span data-stu-id="520a8-115">Release</span></span> | <span data-ttu-id="520a8-116">セキュリティ更新プログラムの KB 番号とリンク</span><span class="sxs-lookup"><span data-stu-id="520a8-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="520a8-117">Windows 10 Version 1709</span><span class="sxs-lookup"><span data-stu-id="520a8-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="520a8-118">[KB4493441 および](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="520a8-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="520a8-119">Windows 10 Version 1803</span><span class="sxs-lookup"><span data-stu-id="520a8-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="520a8-120">[KB4493464](https://support.microsoft.com/help/4493464) および [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="520a8-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="520a8-121">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="520a8-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="520a8-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="520a8-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="520a8-123">Windows 10 Version 1903</span><span class="sxs-lookup"><span data-stu-id="520a8-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="520a8-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="520a8-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="520a8-125">脅威と脆弱性管理によって検出された脅威を修復するために [、Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) および  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) にオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="520a8-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="520a8-126">Configuration Manager を使用している場合は、本体を最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="520a8-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="520a8-127">**注**: Intune 接続が有効になっている場合は、修復要求を作成するときに Intune セキュリティ タスクを作成するオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="520a8-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="520a8-128">接続が設定されていない場合、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="520a8-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="520a8-129">デバイス ページで表示できるセキュリティ推奨事項が 1 つ以上ある</span><span class="sxs-lookup"><span data-stu-id="520a8-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="520a8-130">タグ付けまたは共同管理としてマークされている</span><span class="sxs-lookup"><span data-stu-id="520a8-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="520a8-131">関連するアクセス許可オプション</span><span class="sxs-lookup"><span data-stu-id="520a8-131">Relevant permission options</span></span>

1. <span data-ttu-id="520a8-132">セキュリティ管理者またはグローバル管理者の役割が割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="520a8-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="520a8-133">ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。</span><span class="sxs-lookup"><span data-stu-id="520a8-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="520a8-134">詳細については、「役割ベースの [アクセス制御の役割の作成と管理」を参照してください。](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="520a8-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="520a8-135">データの表示</span><span class="sxs-lookup"><span data-stu-id="520a8-135">View data</span></span>

- <span data-ttu-id="520a8-136">**セキュリティ操作** - ポータルですべてのセキュリティ操作データを表示する</span><span class="sxs-lookup"><span data-stu-id="520a8-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="520a8-137">**脅威と脆弱性の管理** - ポータルで脅威と脆弱性の管理データを表示する</span><span class="sxs-lookup"><span data-stu-id="520a8-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="520a8-138">アクティブな修復アクション</span><span class="sxs-lookup"><span data-stu-id="520a8-138">Active remediation actions</span></span>

- <span data-ttu-id="520a8-139">**セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理</span><span class="sxs-lookup"><span data-stu-id="520a8-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="520a8-140">**脅威と脆弱性の管理 - 例外処理** - 新しい例外を作成し、アクティブな例外を管理する</span><span class="sxs-lookup"><span data-stu-id="520a8-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="520a8-141">**脅威と脆弱性の管理 - 修復処理** - 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理</span><span class="sxs-lookup"><span data-stu-id="520a8-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="520a8-142">詳細については、「RBAC のアクセス許可 [オプション」を参照してください。](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="520a8-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="520a8-143">関連記事</span><span class="sxs-lookup"><span data-stu-id="520a8-143">Related articles</span></span>

- [<span data-ttu-id="520a8-144">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="520a8-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="520a8-145">サポート対象オペレーティング システムとプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="520a8-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="520a8-146">デバイス値の割り当て</span><span class="sxs-lookup"><span data-stu-id="520a8-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="520a8-147">脅威と脆弱性の管理ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="520a8-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

