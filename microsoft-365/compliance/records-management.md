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
ms.openlocfilehash: 48705ac6d0c271ca2646de7c058a340ee3f736ae
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818957"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="771f7-103">Microsoft 365 のレコードの管理</span><span class="sxs-lookup"><span data-stu-id="771f7-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="771f7-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="771f7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="771f7-105">すべての種類の組織では、企業データ全体にわたって規制、法務およびビジネスに不可欠なレコードを管理するためにレコード管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="771f7-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="771f7-106">Microsoft 365 のレコード管理は、組織が法的義務を管理できるようにし、規制の遵守を実証する機能を提供します。これにより、ビジネス上、保持する必要がなくなった、価値がなくなった、または不要になったアイテムを定期的に処分することができて効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="771f7-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="771f7-107">Microsoft 365 のレコード管理では、次の機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="771f7-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="771f7-108">**コンテンツをレコードとして分類する**。</span><span class="sxs-lookup"><span data-stu-id="771f7-108">**Label content as a record**.</span></span> <span data-ttu-id="771f7-109">コンテンツを[レコード](records.md)としてマークする保持ラベルを作成および発行します。エンドユーザーが適用したり、機密情報、キーワード、またはコンテンツ タイプを識別して[自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="771f7-109">Create and publish retention labels that mark content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="771f7-110">**ファイル計画を使用して、保持期間に関する要件を移行して管理します**。</span><span class="sxs-lookup"><span data-stu-id="771f7-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="771f7-111">[ファイル計画](file-plan-manager.md)を使用して、既存の保持プランを Microsoft 365 に持ち込んだり、新しいプランを構築して管理機能を強化したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="771f7-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="771f7-112">**レコード ラベル内で保持と削除のポリシーを確立します**。</span><span class="sxs-lookup"><span data-stu-id="771f7-112">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="771f7-113">最終更新日や作成日などのさまざまな要因に基づき、[保持](create-retention-policies.md#retaining-content-for-a-specific-period-of-time)および[廃棄](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age)の期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="771f7-113">Define [retention](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="771f7-114">[イベント ベースの保持](event-driven-retention.md)を使用して**イベント ベースの保持をトリガーします**。</span><span class="sxs-lookup"><span data-stu-id="771f7-114">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="771f7-115">[処理確認](disposition.md#disposition-reviews)、[レコードの削除](disposition.md#disposition-of-records)の証明を使用して**廃棄を確認および検証します**。</span><span class="sxs-lookup"><span data-stu-id="771f7-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="771f7-116">[[エクスポート] オプション](disposition.md#filter-and-export-the-views)を使用して、**廃棄されたすべてのアイテムに関する情報をエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="771f7-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="771f7-117">[適切なアクセス権を取得する](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ために、組織内のレコード管理機能に**特定のアクセス許可**を設定します。</span><span class="sxs-lookup"><span data-stu-id="771f7-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="771f7-118">Microsoft 365 のレコード管理ソリューションを使用すると、組織の保持スケジュールをファイル計画に反映させ、保持、レコード宣言、廃棄を管理して、コンテンツのライフサイクル全体をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="771f7-118">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="771f7-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="771f7-119">Next steps</span></span>

<span data-ttu-id="771f7-120">Microsoft 365 でのレコード管理を始める準備ができている場合は、「[レコードについての詳細](records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="771f7-120">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
