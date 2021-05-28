---
title: Microsoft 365 の Microsoft 情報ガバナンス
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: コンプライアンスや規制の要件を満たすようにデータを管理するには、Microsoft 情報ガバナンス機能を実装します。
ms.openlocfilehash: a62b1a20aa07c8b5d147fd24e3867c4d4c50174e
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683537"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a><span data-ttu-id="d86cb-103">Microsoft 365 の Microsoft 情報ガバナンス</span><span class="sxs-lookup"><span data-stu-id="d86cb-103">Microsoft Information Governance in Microsoft 365</span></span>

><span data-ttu-id="d86cb-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="d86cb-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="d86cb-105">Microsoft 情報ガバナンス (MIG と略されることもあります) 機能を使用して、コンプライアンスや規制の要件を満たすようにデータを管理します。</span><span class="sxs-lookup"><span data-stu-id="d86cb-105">Use Microsoft Information Governance (sometimes abbreviated to MIG) capabilities to govern your data for compliance or regulatory requirements.</span></span>

![データを管理する - 情報ガバナンスとレコード管理](../media/information-governance-records-management.png)

<span data-ttu-id="d86cb-107">データをセキュリティで保護するには、</span><span class="sxs-lookup"><span data-stu-id="d86cb-107">Looking to protect your data?</span></span> <span data-ttu-id="d86cb-108">「[Microsoft 365 の Microsoft Information Protection](information-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86cb-108">See [Microsoft Information Protection in Microsoft 365](information-protection.md).</span></span>

<span data-ttu-id="d86cb-p102">データのプライバシー規則を遵守できるよう、安全なアクセス、脅威からの保護、情報の保護、データ ガバナンスなど、Microsoft 365 全体の機能を計画および実装するためのエンド ツー エンドのプロセスがわかるワークフローを設計しました。詳細については、「[Microsoft 365を使用したデータプライバシー規制の情報保護の展開 ](../solutions/information-protection-deploy.md) 」(aka.ms/m365dataprivacy) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86cb-p102">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including secure access, threat protection, information protection, and data governance. For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 

## <a name="information-governance"></a><span data-ttu-id="d86cb-111">情報ガバナンス</span><span class="sxs-lookup"><span data-stu-id="d86cb-111">Information governance</span></span>

<span data-ttu-id="d86cb-112">以下のように、必要なものを保持し、不要なものを削除します。</span><span class="sxs-lookup"><span data-stu-id="d86cb-112">To keep what you need and delete what you don't:</span></span>
 
|<span data-ttu-id="d86cb-113">機能</span><span class="sxs-lookup"><span data-stu-id="d86cb-113">Capability</span></span>|<span data-ttu-id="d86cb-114">解決される問題</span><span class="sxs-lookup"><span data-stu-id="d86cb-114">What problems does it solve?</span></span>|<span data-ttu-id="d86cb-115">作業の開始</span><span class="sxs-lookup"><span data-stu-id="d86cb-115">Get started</span></span>|
|:------|:------------|:--------------------|:-----------------------------|
|[<span data-ttu-id="d86cb-116">アイテム保持ポリシーと保持ラベル</span><span class="sxs-lookup"><span data-stu-id="d86cb-116">Retention policies and retention labels</span></span>](retention.md)| <span data-ttu-id="d86cb-117">メール、ドキュメント、インスタント メッセージなどのポリシー管理および削除ワークフローを使用して、コンテンツを保持または削除する</span><span class="sxs-lookup"><span data-stu-id="d86cb-117">Retain or delete content with policy management and a deletion workflow for email, documents, instant messages, and more</span></span> <br /><br /><span data-ttu-id="d86cb-118">シナリオ例: [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="d86cb-118">Example scenario: [Apply a retention label to content automatically](apply-retention-labels-automatically.md)</span></span> | [<span data-ttu-id="d86cb-119">アイテム保持ポリシーおよび保持ラベルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="d86cb-119">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)|
|[<span data-ttu-id="d86cb-120">サービスをインポートする</span><span class="sxs-lookup"><span data-stu-id="d86cb-120">Import service</span></span>](importing-pst-files-to-office-365.md)| <span data-ttu-id="d86cb-121">Exchange Online メールボックスに PST ファイルを一括インポートして、コンプライアンスや規制要件に対応してメールメッセージを保持し検索する</span><span class="sxs-lookup"><span data-stu-id="d86cb-121">Bulk-import PST files to Exchange Online mailboxes to retain and search email messages for compliance or regulatory requirements</span></span> | [<span data-ttu-id="d86cb-122">ネットワーク アップロードを使用して、組織の PST ファイルを Microsoft 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="d86cb-122">Use network upload to import your organization's PST files to Microsoft 365</span></span>](use-network-upload-to-import-pst-files.md)|
|[<span data-ttu-id="d86cb-123">サードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="d86cb-123">Archive third-party data</span></span>](archiving-third-party-data.md)| <span data-ttu-id="d86cb-124">ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームからサードパーティのデータをインポートし、アーカイブして、コンプライアンス ソリューションを適用する</span><span class="sxs-lookup"><span data-stu-id="d86cb-124">Import, archive, and apply compliance solutions to third-party data from social media platforms, instant messaging platforms, and document collaboration platforms</span></span>| [<span data-ttu-id="d86cb-125">サードパーティのコネクタ</span><span class="sxs-lookup"><span data-stu-id="d86cb-125">Third-party connectors</span></span>](archiving-third-party-data.md#third-party-data-connectors)|
|[<span data-ttu-id="d86cb-126">非アクティブなメールボックス</span><span class="sxs-lookup"><span data-stu-id="d86cb-126">Inactive mailboxes</span></span>](inactive-mailboxes-in-office-365.md)| <span data-ttu-id="d86cb-127">従業員が組織を離れた後にメールボックスのコンテンツを保持する</span><span class="sxs-lookup"><span data-stu-id="d86cb-127">Retain mailbox content after employees leave the organization</span></span> | [<span data-ttu-id="d86cb-128">非アクティブなメールボックスを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="d86cb-128">Create and manage inactive mailboxes</span></span>](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a><span data-ttu-id="d86cb-129">レコード管理</span><span class="sxs-lookup"><span data-stu-id="d86cb-129">Records management</span></span>

<span data-ttu-id="d86cb-130">以下のように、法的、ビジネス、または規制上の義務のために価値の高いコンテンツを管理します。</span><span class="sxs-lookup"><span data-stu-id="d86cb-130">To manage high-value content for legal, business, or regulatory obligations:</span></span>

|<span data-ttu-id="d86cb-131">機能</span><span class="sxs-lookup"><span data-stu-id="d86cb-131">Capability</span></span>|<span data-ttu-id="d86cb-132">解決される問題</span><span class="sxs-lookup"><span data-stu-id="d86cb-132">What problems does it solve?</span></span>|<span data-ttu-id="d86cb-133">作業の開始</span><span class="sxs-lookup"><span data-stu-id="d86cb-133">Get started</span></span>|
|:------|:------------|---------------------|:----------------------------|
|[<span data-ttu-id="d86cb-134">レコード管理</span><span class="sxs-lookup"><span data-stu-id="d86cb-134">Records management</span></span>](records-management.md)| <span data-ttu-id="d86cb-135">レコード宣言、保持、処理により、コンテンツのライフサイクル全体をサポートする、保持スケジュールと要件をファイル計画に組み込んだメールとドキュメント用の単一ソリューション。</span><span class="sxs-lookup"><span data-stu-id="d86cb-135">A single solution for email and documents that incorporates retention schedules and requirements into a file plan that supports the full lifecycle of your content with records declaration, retention, and disposition</span></span> <br /><br /><span data-ttu-id="d86cb-136">シナリオ例: [ レコードの処理](disposition.md#disposition-of-records)</span><span class="sxs-lookup"><span data-stu-id="d86cb-136">Example scenario: [Disposition of records](disposition.md#disposition-of-records)</span></span>|[<span data-ttu-id="d86cb-137">レコード管理の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="d86cb-137">Get started with records management</span></span>](get-started-with-records-management.md) |

## <a name="licensing-requirements"></a><span data-ttu-id="d86cb-138">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="d86cb-138">Licensing requirements</span></span>

<span data-ttu-id="d86cb-139">Microsoft 情報ガバナンスのライセンス要件は、このページにリストされている各機能のライセンス要件を設定するのではなく、使用するシナリオと機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d86cb-139">License requirements for Microsoft Information Governance depend on the scenarios and features you use, rather than set licensing requirements for each capability listed on this page.</span></span> <span data-ttu-id="d86cb-140">ライセンス要件とオプションを理解するには、Microsoft 365 ライセンス ドキュメントの「[情報ガバナンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)」 と 「[レコード管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management)」セクションを参照し、関連する PDF または Excel をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="d86cb-140">To understand your licensing requirements and options, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) and [Records Management](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) sections from the Microsoft 365 licensing documentation, and download the related PDF or Excel.</span></span>