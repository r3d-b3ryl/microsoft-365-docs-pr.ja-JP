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
description: Microsoft 365 のレコード管理を使用すると、組織の特定の保持スケジュールをファイル計画に適用し、コンテンツの完全なライフサイクルをサポートするために、保持、レコード宣言、廃棄を管理することができます。
ms.openlocfilehash: e4454ba5940d9a67d9f160d90d0a9db14563bcf7
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949250"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="b4b5b-103">Microsoft 365 のレコードの管理</span><span class="sxs-lookup"><span data-stu-id="b4b5b-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="b4b5b-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="b4b5b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b4b5b-105">すべての種類の組織では、企業データ全体にわたって規制、法務およびビジネスに不可欠なレコードを管理するためにレコード管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="b4b5b-106">Microsoft 365 のレコード管理は、組織が法的義務を管理できるようにし、規制の遵守を実証する機能を提供します。これにより、ビジネス上、保持する必要がなくなった、価値がなくなった、または不要になったアイテムを定期的に処分することができて効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="b4b5b-107">レコード管理ソリューションは、次の要素をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="b4b5b-108">**コンテンツをレコードとして分類する**。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-108">**Label content as a record**.</span></span> <span data-ttu-id="b4b5b-109">コンテンツを[レコード](records.md)として宣言する保持ラベルを作成および発行します。エンドユーザーが適用したり、機密情報、キーワード、またはコンテンツ タイプを識別して[自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-109">Create and publish retention labels that declare content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="b4b5b-110">**ファイル計画を使用して保持計画を移行および管理**し、[ファイル計画マネージャー](file-plan-manager.md)を使用して既存の保持計画を取り込むか、ファイル記述子と階層を展開して新しい計画を構築します。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="b4b5b-111">**保持と削除のポリシーを規定します**。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-111">**Establish retention and deletion policies**.</span></span> <span data-ttu-id="b4b5b-112">最終更新日や作成日などのさまざまな要因に基づき、[保持](retention-policies.md#retaining-content-for-a-specific-period-of-time)および[廃棄](retention-policies.md#deleting-content-thats-older-than-a-specific-age)の期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-112">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="b4b5b-113">[イベント ベースの保持](event-driven-retention.md)を使用して**イベント ベースの保持をトリガーします**。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="b4b5b-114">[処理確認](disposition.md#disposition-reviews)、[レコードの削除](disposition.md#disposition-of-records)の証明を使用して**廃棄を確認および検証します**。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-114">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="b4b5b-115">[[エクスポート] オプション](disposition.md#filter-and-export-the-views)を使用して、**廃棄されたすべてのアイテムに関する情報をエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-115">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="b4b5b-116">[適切なアクセス権を取得する](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ために、組織内のレコード管理機能に**特定のアクセス許可**を設定します。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b4b5b-117">Microsoft 365 のレコード管理ソリューションを使用すると、組織の保持スケジュールをファイル計画に反映させ、保持、レコード宣言、廃棄を管理して、コンテンツのライフサイクル全体をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4b5b-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>
