---
title: Advanced eDiscovery で保管担当者を操作する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Advanced eDiscovery で保管担当者管理ツールを使用して、法的なケースのデータを管理する方法について説明します。
ms.openlocfilehash: 159ee0b0365ec7c2419fd9abe1426ad9c5efed4a
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024687"
---
# <a name="work-with-custodians-and-non-custodial-data-sources-in-advanced-ediscovery"></a><span data-ttu-id="919cc-103">Advanced eDiscovery で保管担当者および非 custodial データソースを操作する</span><span class="sxs-lookup"><span data-stu-id="919cc-103">Work with custodians and non-custodial data sources in Advanced eDiscovery</span></span>

<span data-ttu-id="919cc-104">組織が法的調査に応答した場合、関連するデータを保管担当者する組織内のユーザーに基づいて、潜在的な関連性のあるコンテンツを特定し、保持し、収集することに関するワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="919cc-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="919cc-105">電子情報開示では、これらの個人は*data 保管担当者*(または*保管担当者*) と呼ばれ、"ドキュメントまたは電子ファイルの管理制御を持つ人" として定義されています。</span><span class="sxs-lookup"><span data-stu-id="919cc-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="919cc-106">たとえば、電子メールメッセージの保管担当者は、関連するメッセージが含まれるメールボックスの所有者である場合があります。</span><span class="sxs-lookup"><span data-stu-id="919cc-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>

<span data-ttu-id="919cc-107">また、保管担当者に関連付けられていないが、そのケースに関連するコンテンツがメールボックスやサイトにある場合があります。</span><span class="sxs-lookup"><span data-stu-id="919cc-107">Additionally, there may be content located in mailboxes and sites that aren't associated with a custodian but that's relevant to the case.</span></span> <span data-ttu-id="919cc-108">ケース保管担当者に管理者制御がなく、関連データが含まれている可能性があるコンテンツの場所を区別するために、これらは*非 wi-fi ダイヤルデータソース*として知られています。</span><span class="sxs-lookup"><span data-stu-id="919cc-108">To differentiate content locations where case custodians don't have administrative control but may contain relevant data, these are known as *non-custodial data sources*.</span></span>

<span data-ttu-id="919cc-109">高度な電子情報開示ケースでは、法務部門が組織内の個人を保管担当者として追加し、Exchange メールボックス、OneDrive アカウント、SharePoint、Teams サイトなどの、custodial データソースを自動的に識別して保持することができます。</span><span class="sxs-lookup"><span data-stu-id="919cc-109">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="919cc-110">また、非 wi-fi ダイヤルデータソースを識別して保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="919cc-110">They can also identify and preserve non-custodial data sources.</span></span> <span data-ttu-id="919cc-111">高度な電子情報開示の組み込みの保管担当者およびデータソース管理ツールを使用することにより、組織は不用意 (または故意) による削除から電子的に保存された情報を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="919cc-111">By using the built-in custodian and data source management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="919cc-112">これにより、訴訟ホールドプロセスを手動で実行するための時間がかかり、エラーが発生しやすいプロセスを排除することができます。</span><span class="sxs-lookup"><span data-stu-id="919cc-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span>

<span data-ttu-id="919cc-113">保管担当者の使用の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919cc-113">For more information about working with custodians, see the following:</span></span>

- [<span data-ttu-id="919cc-114">ケースにカストディアンを追加する</span><span class="sxs-lookup"><span data-stu-id="919cc-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="919cc-115">ケースへの一括追加保管担当者</span><span class="sxs-lookup"><span data-stu-id="919cc-115">Bulk-add custodians to a case</span></span>](bulk-add-custodians.md)

- [<span data-ttu-id="919cc-116">ケースで保管担当者を管理する</span><span class="sxs-lookup"><span data-stu-id="919cc-116">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="919cc-117">カストディアンのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="919cc-117">View custodian activity</span></span>](view-custodian-activity.md)

- [<span data-ttu-id="919cc-118">ケースに非 custodial データソースを追加する</span><span class="sxs-lookup"><span data-stu-id="919cc-118">Add non-custodial data sources to a case</span></span>](non-custodial-data-sources.md)
