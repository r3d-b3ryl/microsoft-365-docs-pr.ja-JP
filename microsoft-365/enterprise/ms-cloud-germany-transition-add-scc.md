---
title: Microsoft Cloud Deutschland からの移行中の電子情報開示エクスペリエンスに関する情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Deutschland からの移行に関する電子情報開示移行手順。'
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844252"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="d94a4-103">Microsoft Cloud Deutschland からの移行中の電子情報開示エクスペリエンスに関する情報</span><span class="sxs-lookup"><span data-stu-id="d94a4-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="d94a4-104">次のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行する際の電子情報開示エクスペリエンスに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d94a4-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="d94a4-105">フェーズ 4 までの電子情報開示の管理</span><span class="sxs-lookup"><span data-stu-id="d94a4-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="d94a4-106">フェーズ 4 まで、セキュリティとコンプライアンス センターは完全に利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d94a4-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="d94a4-107">すべてのコンテンツは引き続き Microsoft Cloud Germany に残り、Microsoft Cloud Germany Security and Compliance Center ( https://protection.office.de/) .</span><span class="sxs-lookup"><span data-stu-id="d94a4-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="d94a4-108">フェーズ 4 からフェーズ 9 の終了までの電子情報開示エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d94a4-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="d94a4-109">フェーズ 4 の初めからフェーズ 9 が完了するまで、電子情報開示の検索は失敗するか、移行された SharePoint Online、OneDrive for Business、および Exchange Online の場所に対して 0 の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="d94a4-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="d94a4-110">移行中、お客様は、コンテンツ検索を含むセキュリティ & コンプライアンス センターでケース、保留、[検索、およびエクスポートを](/microsoft-365/compliance/manage-legal-investigations)[作成し続けます](/microsoft-365/compliance/search-for-content)。</span><span class="sxs-lookup"><span data-stu-id="d94a4-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="d94a4-111">ただし、移行された SharePoint、OneDrive for Business、Exchange Online の場所に対して検索すると、0 の結果が返されるか、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d94a4-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="d94a4-112">移行中に検索で結果がゼロまたはエラーが返された場合は、次のアクションを実行してオンラインSharePointしてください。</span><span class="sxs-lookup"><span data-stu-id="d94a4-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="d94a4-113">「ファイルとフォルダーを SharePoint または OneDrive for Business OneDrive からダウンロードする」の手順に従って、SharePoint Online または OneDrive for Business サイトからサイトを直接[SharePointダウンロードします](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。</span><span class="sxs-lookup"><span data-stu-id="d94a4-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="d94a4-114">このメソッドでは、SharePointの管理者アクセス許可または読み取り専用のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d94a4-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="d94a4-115">[「OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)または SharePoint からファイルとフォルダーをダウンロードする」で説明したように、制限を超えた場合は、SharePoint ファイルと Teams ファイルをコンピューターと同期する[](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)のガイダンスに従って、OneDrive for Business 同期クライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d94a4-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="d94a4-116">詳細については[、「インプレース電子情報開示」をExchange Server。](/Exchange/policy-and-compliance/ediscovery/ediscovery)</span><span class="sxs-lookup"><span data-stu-id="d94a4-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="d94a4-117">フェーズ 9 以降の電子情報開示の管理</span><span class="sxs-lookup"><span data-stu-id="d94a4-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="d94a4-118">**適用対象:** 電子情報開示を使用しているすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d94a4-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="d94a4-119">フェーズ 9 では、新しいドイツのデータセンター領域に移行するための最後の手順が完了します。</span><span class="sxs-lookup"><span data-stu-id="d94a4-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="d94a4-120">このフェーズでは、残りのすべてのサービス コンポーネントが移行されます。</span><span class="sxs-lookup"><span data-stu-id="d94a4-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="d94a4-121">フェーズ 9 の後、Microsoft Cloud Germany (protection.office.de) のセキュリティとコンプライアンス センターの使用はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d94a4-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="d94a4-122">代わりに、新[しいセキュリティ センターまたは](https://security.microsoft.com/)[コンプライアンス センターを](https://compliance.microsoft.com/)使用してください。</span><span class="sxs-lookup"><span data-stu-id="d94a4-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="d94a4-123">すべてのデータが新しい管理ポータルに移行されました。</span><span class="sxs-lookup"><span data-stu-id="d94a4-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="d94a4-124">Step(s)</span><span class="sxs-lookup"><span data-stu-id="d94a4-124">Step(s)</span></span> | <span data-ttu-id="d94a4-125">説明</span><span class="sxs-lookup"><span data-stu-id="d94a4-125">Description</span></span> | <span data-ttu-id="d94a4-126">影響</span><span class="sxs-lookup"><span data-stu-id="d94a4-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="d94a4-127">すべての SharePoint、OneDrive for Business、およびExchange Onlineの場所は、セキュリティとコンプライアンス センター (SCC) と共に移行されています。</span><span class="sxs-lookup"><span data-stu-id="d94a4-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="d94a4-128">すべての電子情報開示アクティビティは、世界中のテナントから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94a4-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="d94a4-129">これで、検索は 100% 成功します。</span><span class="sxs-lookup"><span data-stu-id="d94a4-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="d94a4-130">エラーやエラーは、通常のサポート チャネルに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d94a4-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="d94a4-131">なし</span><span class="sxs-lookup"><span data-stu-id="d94a4-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="d94a4-132">電子情報開示の保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="d94a4-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="d94a4-133">**適用対象:**  移行前の手順の一部としてアイテム保持ポリシーを適用したすべての顧客</span><span class="sxs-lookup"><span data-stu-id="d94a4-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="d94a4-134">Step(s)</span><span class="sxs-lookup"><span data-stu-id="d94a4-134">Step(s)</span></span> | <span data-ttu-id="d94a4-135">説明</span><span class="sxs-lookup"><span data-stu-id="d94a4-135">Description</span></span> | <span data-ttu-id="d94a4-136">影響</span><span class="sxs-lookup"><span data-stu-id="d94a4-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="d94a4-137">移行前の手順で作成された組織全体の保持ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d94a4-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="d94a4-138">顧客は、移行前の作業中に作成された組織全体の保持ポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d94a4-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="d94a4-139">なし</span><span class="sxs-lookup"><span data-stu-id="d94a4-139">None</span></span> |
||||
