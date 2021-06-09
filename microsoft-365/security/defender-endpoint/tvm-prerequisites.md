---
title: 前提条件&アクセス許可 - 脅威と脆弱性の管理
description: アプリケーションの使用を開始脅威と脆弱性の管理、関連する構成とアクセス許可を持っている必要があります。
keywords: 脅威& 脆弱性の管理アクセス許可の前提条件、脅威と脆弱性の管理アクセス許可の前提条件、Microsoft Defender for Endpoint TVM アクセス許可の前提条件、脆弱性の管理
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
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843952"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="79965-104">前提条件&アクセス許可 - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="79965-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79965-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="79965-105">**Applies to:**</span></span>

- [<span data-ttu-id="79965-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="79965-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="79965-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="79965-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="79965-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79965-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="79965-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="79965-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79965-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="79965-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="79965-111">デバイスが次の条件を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79965-111">Ensure that your devices:</span></span>

- <span data-ttu-id="79965-112">Microsoft Defender for Endpoint にオンボードされている</span><span class="sxs-lookup"><span data-stu-id="79965-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="79965-113">サポート [されているオペレーティング システムとプラットフォームを実行する](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="79965-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="79965-114">ネットワークに次の必須更新プログラムをインストールして展開し、脆弱性評価の検出率を向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="79965-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="79965-115">リリース</span><span class="sxs-lookup"><span data-stu-id="79965-115">Release</span></span> | <span data-ttu-id="79965-116">セキュリティ更新プログラムの KB 番号とリンク</span><span class="sxs-lookup"><span data-stu-id="79965-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="79965-117">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="79965-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="79965-118">[KB4493441 および](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="79965-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="79965-119">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="79965-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="79965-120">[KB4493464](https://support.microsoft.com/help/4493464) および [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="79965-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="79965-121">Windows 10バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="79965-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="79965-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="79965-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="79965-123">Windows 10バージョン 1903</span><span class="sxs-lookup"><span data-stu-id="79965-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="79965-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="79965-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="79965-125">ユーザーが検出した[脅威Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[修復Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)を支援するために、脅威と脆弱性の管理。</span><span class="sxs-lookup"><span data-stu-id="79965-125">Are onboarded to [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="79965-126">Configuration Manager を使用している場合は、本体を最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="79965-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="79965-127">**注**: Intune 接続が有効になっている場合は、修復要求を作成するときに Intune セキュリティ タスクを作成するオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="79965-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="79965-128">接続が設定されていない場合、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="79965-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="79965-129">デバイス ページで表示できるセキュリティ推奨事項が 1 つ以上ある</span><span class="sxs-lookup"><span data-stu-id="79965-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="79965-130">タグ付けまたは共同管理としてマークされている</span><span class="sxs-lookup"><span data-stu-id="79965-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="79965-131">関連するアクセス許可オプション</span><span class="sxs-lookup"><span data-stu-id="79965-131">Relevant permission options</span></span>

1. <span data-ttu-id="79965-132">セキュリティ管理者またはグローバルMicrosoft Defender セキュリティ センターが割り当てられているアカウントを使用して、アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="79965-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="79965-133">ナビゲーション ウィンドウで、[ロール] を **設定 >します**。</span><span class="sxs-lookup"><span data-stu-id="79965-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="79965-134">詳細については、「役割ベースの [アクセス制御の役割の作成と管理」を参照してください。](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="79965-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="79965-135">データの表示</span><span class="sxs-lookup"><span data-stu-id="79965-135">View data</span></span>

- <span data-ttu-id="79965-136">**セキュリティ操作** - ポータルですべてのセキュリティ操作データを表示する</span><span class="sxs-lookup"><span data-stu-id="79965-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="79965-137">**脅威と脆弱性の管理**- ポータル脅威と脆弱性の管理データを表示する</span><span class="sxs-lookup"><span data-stu-id="79965-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="79965-138">アクティブな修復アクション</span><span class="sxs-lookup"><span data-stu-id="79965-138">Active remediation actions</span></span>

- <span data-ttu-id="79965-139">**セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理</span><span class="sxs-lookup"><span data-stu-id="79965-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="79965-140">**脅威と脆弱性の管理 - 例外処理**- 新しい例外を作成し、アクティブな例外を管理する</span><span class="sxs-lookup"><span data-stu-id="79965-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="79965-141">**脅威と脆弱性の管理 - 修復処理**- 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理</span><span class="sxs-lookup"><span data-stu-id="79965-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="79965-142">詳細については、「RBAC のアクセス許可 [オプション」を参照してください。](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="79965-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="79965-143">関連資料</span><span class="sxs-lookup"><span data-stu-id="79965-143">Related articles</span></span>

- [<span data-ttu-id="79965-144">脅威と脆弱性の管理概要</span><span class="sxs-lookup"><span data-stu-id="79965-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="79965-145">サポート対象オペレーティング システムとプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="79965-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="79965-146">デバイス値の割り当て</span><span class="sxs-lookup"><span data-stu-id="79965-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="79965-147">脅威と脆弱性の管理ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="79965-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

