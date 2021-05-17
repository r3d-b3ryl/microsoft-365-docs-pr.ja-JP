---
title: 管理者と一緒に作業Advanced eDiscovery
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
description: カストディアン管理ツールを使用して、Advanced eDiscoveryケースのデータを管理する方法について説明します。
ms.openlocfilehash: 22297edbf73f561ad46e5fae521abeb371fdc88d
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528133"
---
# <a name="work-with-custodians-and-non-custodial-data-sources-in-advanced-ediscovery"></a><span data-ttu-id="41ac5-103">管理担当者と管理されていないデータ ソースを管理Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="41ac5-103">Work with custodians and non-custodial data sources in Advanced eDiscovery</span></span>

<span data-ttu-id="41ac5-104">組織が法的調査に応答すると、関連する可能性のあるコンテンツの特定、保存、および収集に関するワークフローは、関連するデータの保管担当者である組織内のユーザーに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="41ac5-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="41ac5-105">電子情報開示では、これらの個人はデータ保管担当者 *(または* カストディアン *)* と呼ばされ、「ドキュメントまたは電子ファイルの管理制御を持つ人物」と定義されます。</span><span class="sxs-lookup"><span data-stu-id="41ac5-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="41ac5-106">たとえば、電子メールメッセージのカストディアンは、関連メッセージを含むメールボックスの所有者でもあります。</span><span class="sxs-lookup"><span data-stu-id="41ac5-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>

<span data-ttu-id="41ac5-107">さらに、メールボックスやサイト内に、保管担当者に関連付けされていないが、ケースに関連するコンテンツがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="41ac5-107">Additionally, there may be content located in mailboxes and sites that aren't associated with a custodian but that's relevant to the case.</span></span> <span data-ttu-id="41ac5-108">ケース保管担当者が管理管理権を持っていないが、関連するデータの所有者である可能性があるコンテンツの場所は、非保管データ ソースと *呼ばれる場所です*。</span><span class="sxs-lookup"><span data-stu-id="41ac5-108">Content locations where case custodians don't have administrative control but may be owners of relevant data, are known as *non-custodial data sources*.</span></span>

<span data-ttu-id="41ac5-109">Advanced eDiscovery の場合、法務チームは組織内の個人を保管担当者として追加し、Exchange メールボックス、OneDrive アカウント、SharePoint サイト、Teams サイトなどの保管データ ソースを特定して保持できます。</span><span class="sxs-lookup"><span data-stu-id="41ac5-109">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and  identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="41ac5-110">また、保管されていないデータ ソースを特定して保持できます。</span><span class="sxs-lookup"><span data-stu-id="41ac5-110">They can also identify and preserve non-custodial data sources.</span></span> <span data-ttu-id="41ac5-111">Advanced eDiscovery で組み込みの保管担当者とデータ ソース管理ツールを使用することで、組織は不注意 (または意図的な) 削除から電子的に保存された情報を保護できます。</span><span class="sxs-lookup"><span data-stu-id="41ac5-111">By using the built-in custodian and data source management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="41ac5-112">これにより、法的保持プロセスを手動で実行する時間がかかり、エラーが発生しやすいプロセスを排除できます。</span><span class="sxs-lookup"><span data-stu-id="41ac5-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span>

<span data-ttu-id="41ac5-113">保管担当者の操作の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ac5-113">For more information about working with custodians, see the following articles:</span></span>

- [<span data-ttu-id="41ac5-114">ケースにカストディアンを追加する</span><span class="sxs-lookup"><span data-stu-id="41ac5-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="41ac5-115">カストディアンをケースに一括追加する</span><span class="sxs-lookup"><span data-stu-id="41ac5-115">Bulk-add custodians to a case</span></span>](bulk-add-custodians.md)

- [<span data-ttu-id="41ac5-116">ケースの保管担当者の管理</span><span class="sxs-lookup"><span data-stu-id="41ac5-116">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="41ac5-117">カストディアンのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="41ac5-117">View custodian activity</span></span>](view-custodian-activity.md)

- [<span data-ttu-id="41ac5-118">非カストディアンのデータ ソースをケースに追加する</span><span class="sxs-lookup"><span data-stu-id="41ac5-118">Add non-custodial data sources to a case</span></span>](non-custodial-data-sources.md)
