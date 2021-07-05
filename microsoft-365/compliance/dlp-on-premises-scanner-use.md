---
title: Microsoft 365 のデータ損失防止のオンプレミス スキャナー (プレビュー) を使用する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: オンプレミスのスキャナーで Microsoft 365 データ損失防止を使用して、保存されているデータをスキャンし、オンプレミスのファイル共有とオンプレミスの SharePoint フォルダーとドキュメント ライブラリに保護アクションを実装する方法について説明します。
ms.openlocfilehash: b2512c47b82ab3624d892d349611dd3f1e5aed3c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289177"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="4f4a7-103">Microsoft 365 のデータ損失防止のオンプレミス スキャナー (プレビュー) を使用する</span><span class="sxs-lookup"><span data-stu-id="4f4a7-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="4f4a7-104">DLP オンプレミス機能、および DLP ポリシーで表示される方法を把握するために、いくつかのシナリオをまとめてましたので、確認してください。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f4a7-105">これらの DLP オンプレミス シナリオは、DLP ポリシーの作成と調整に関する公式な手順ではありません。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="4f4a7-106">一般的な状況で DLP ポリシーを使用する必要がある場合は、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>
> - [<span data-ttu-id="4f4a7-107">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="4f4a7-107">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
> - [<span data-ttu-id="4f4a7-108">DLP の既定ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="4f4a7-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
> - [<span data-ttu-id="4f4a7-109">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4f4a7-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
> - [<span data-ttu-id="4f4a7-110">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="4f4a7-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="4f4a7-111">シナリオ: DLP ルールに一致するファイルを検出する</span><span class="sxs-lookup"><span data-stu-id="4f4a7-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="4f4a7-112">DLP オンプレミス スキャナーのデータが複数の領域に表示される</span><span class="sxs-lookup"><span data-stu-id="4f4a7-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="4f4a7-113">アクティビティ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="4f4a7-113">Activity explorer</span></span>

 <span data-ttu-id="4f4a7-114">オンプレミス用の Microsoft DLP は、DLP ルールの一致を検出し、「[アクティビティ エクスプローラー](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)」に報告します。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span>

#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="4f4a7-115">Microsoft 365 監査ログ</span><span class="sxs-lookup"><span data-stu-id="4f4a7-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="4f4a7-116">パブリック プレビュー中、DLP ルールの一致は監査ログ UI で利用できます。「[コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」か、「[Search-UnifiedAuditLogPowerShell](/powershell/module/exchange/search-unifiedauditlog)」からアクセスできます。 </span><span class="sxs-lookup"><span data-stu-id="4f4a7-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="4f4a7-117">AIP</span><span class="sxs-lookup"><span data-stu-id="4f4a7-117">AIP</span></span>

<span data-ttu-id="4f4a7-118">検出データは、以下の場所に保存されている csv 形式のローカル レポートで利用できます。 </span><span class="sxs-lookup"><span data-stu-id="4f4a7-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="4f4a7-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="4f4a7-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="4f4a7-120">次の列を調べてください。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-120">Look for the following columns:</span></span>

- <span data-ttu-id="4f4a7-121">DLP モード</span><span class="sxs-lookup"><span data-stu-id="4f4a7-121">DLP Mode</span></span>
- <span data-ttu-id="4f4a7-122">DLP の状態</span><span class="sxs-lookup"><span data-stu-id="4f4a7-122">DLP Status</span></span>
- <span data-ttu-id="4f4a7-123">DLP コメント</span><span class="sxs-lookup"><span data-stu-id="4f4a7-123">DLP Comment</span></span>
- <span data-ttu-id="4f4a7-124">DLP ルール名</span><span class="sxs-lookup"><span data-stu-id="4f4a7-124">DLP Rule Name</span></span>
- <span data-ttu-id="4f4a7-125">DLP アクション</span><span class="sxs-lookup"><span data-stu-id="4f4a7-125">DLP Actions</span></span>
- <span data-ttu-id="4f4a7-126">所有者</span><span class="sxs-lookup"><span data-stu-id="4f4a7-126">Owner</span></span>
- <span data-ttu-id="4f4a7-127">現在の NTFS アクセス許可 (SDDL)</span><span class="sxs-lookup"><span data-stu-id="4f4a7-127">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="4f4a7-128">適用済みの NTFS アクセス許可 (SDDL)</span><span class="sxs-lookup"><span data-stu-id="4f4a7-128">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="4f4a7-129">NTFS アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="4f4a7-129">NTFS permissions type</span></span>

### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="4f4a7-130">シナリオ: DLP ルールを適用する</span><span class="sxs-lookup"><span data-stu-id="4f4a7-130">Scenario: Enforce DLP rule</span></span>

<span data-ttu-id="4f4a7-131">スキャンしたファイルに DLP ルールを適用する場合、AIP のコンテンツ スキャン ジョブと DLP のポリシー レベルの両方で、適用を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-131">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>

#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="4f4a7-132">ポリシー アクションを適用するために DLP を構成する</span><span class="sxs-lookup"><span data-stu-id="4f4a7-132">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="4f4a7-133">[[データ損失防止](https://compliance.microsoft.com/datalossprevention?viewid=policies)] ページを開き、AIP で構成したオンプレミスの場所リポジトリを対象とする DLP ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-133">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span>
2. <span data-ttu-id="4f4a7-134">ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-134">Edit the policy.</span></span>
3. <span data-ttu-id="4f4a7-135">「**ポリシーをテストまたは有効にする**」のページで、**[はい] を選び、ポリシーを今すぐ有効にします**。</span><span class="sxs-lookup"><span data-stu-id="4f4a7-135">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f4a7-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f4a7-136">See also</span></span>

- [<span data-ttu-id="4f4a7-137">DLP オンプレミス スキャナーの前提条件 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4f4a7-137">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="4f4a7-138">DLP オンプレミス スキャナーの使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4f4a7-138">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="4f4a7-139">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="4f4a7-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="4f4a7-140">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="4f4a7-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4f4a7-141">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="4f4a7-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
