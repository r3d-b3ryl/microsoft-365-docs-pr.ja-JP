---
title: レコード管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365 のレコード管理を使用すると、保持スケジュールをファイル計画に適用し、保持、レコード宣言、廃棄を管理することができます。
ms.openlocfilehash: 08b028bbd28c06684245321e09f8ef3252098956
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372490"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="bd133-103">Microsoft 365 のレコードの管理</span><span class="sxs-lookup"><span data-stu-id="bd133-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="bd133-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="bd133-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bd133-105">すべての種類の組織では、企業データ全体にわたって規制、法務およびビジネスに不可欠なレコードを管理するためにレコード管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bd133-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="bd133-106">Microsoft 365 のレコード管理は、組織が法的義務を管理できるようにし、規制の遵守を実証する機能を提供します。これにより、ビジネス上、保持する必要がなくなった、価値がなくなった、または不要になったアイテムを定期的に処分することができて効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="bd133-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="bd133-107">Microsoft 365 のレコード管理では、次の機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="bd133-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="bd133-108">**コンテンツをレコードとして分類する**。</span><span class="sxs-lookup"><span data-stu-id="bd133-108">**Label content as a record**.</span></span> <span data-ttu-id="bd133-109">コンテンツを[レコード](records.md)としてマークする保持ラベルを作成および構成します。ユーザーが適用したり、機密情報、キーワード、またはコンテンツ タイプを識別して[自動適用](apply-retention-labels-automatically.md)したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd133-109">Create and configure retention labels to mark content as a [record](records.md) that can then be applied by users or [auto-applied](apply-retention-labels-automatically.md) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="bd133-110">**ファイル計画を使用して、保持期間に関する要件を移行して管理します**。</span><span class="sxs-lookup"><span data-stu-id="bd133-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="bd133-111">[ファイル計画](file-plan-manager.md)を使用して、既存の保持プランを Microsoft 365 に持ち込んだり、新しいプランを構築して管理機能を強化したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd133-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="bd133-112">**保持ラベルを使用して、保持と削除の設定を構成します**。</span><span class="sxs-lookup"><span data-stu-id="bd133-112">**Configure retention and deletion settings with the retention label**.</span></span> <span data-ttu-id="bd133-113">最終更新日や作成日などのさまざまな要因に基づき、保持期間とアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="bd133-113">Define retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="bd133-114">[イベントベースの保持](event-driven-retention.md)を使って、**イベントが発生したときに、別の保持期間を開始する**。</span><span class="sxs-lookup"><span data-stu-id="bd133-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="bd133-115">[処理確認](disposition.md#disposition-reviews)、[レコードの削除](disposition.md#disposition-of-records)の証明を使用して**廃棄を確認および検証します**。</span><span class="sxs-lookup"><span data-stu-id="bd133-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="bd133-116">[[エクスポート] オプション](disposition.md#filter-and-export-the-views)を使用して、**廃棄されたすべてのアイテムに関する情報をエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="bd133-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="bd133-117">[適切なアクセス権を取得する](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ために、組織内のレコード管理機能に**特定のアクセス許可**を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd133-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="bd133-118">Microsoft 365 のレコード管理ソリューションを使用すると、組織の保持スケジュールと要件をファイル計画に反映させ、保持、レコード宣言、廃棄を管理して、コンテンツのライフサイクル全体をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd133-118">With the records-management solution in Microsoft 365, you can incorporate your organization's retention schedules and requirements into a file plan that manages retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd133-119">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="bd133-119">Additional resources</span></span>

<span data-ttu-id="bd133-120">記録管理については、[ウェビナーの録画](https://aka.ms/MIPC/Video-RecordsManagementWebinar) と[デッキをよく寄せられる質問](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) でご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd133-120">See the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) and [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) for records management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bd133-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="bd133-121">Next steps</span></span>

<span data-ttu-id="bd133-122">Microsoft 365 でのレコード管理を始める準備ができている場合は、「[レコードについての詳細](records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd133-122">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
