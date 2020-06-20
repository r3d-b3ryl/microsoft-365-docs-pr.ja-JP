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
ms.openlocfilehash: 400793a6779cef5b1e823f40fa08cc1e05f93f15
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815494"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a><span data-ttu-id="812bb-103">Advanced eDiscovery で保管担当者を操作する</span><span class="sxs-lookup"><span data-stu-id="812bb-103">Work with custodians in Advanced eDiscovery</span></span>

<span data-ttu-id="812bb-104">組織が法的調査に応答した場合、関連するデータを保管担当者する組織内のユーザーに基づいて、潜在的な関連性のあるコンテンツを特定し、保持し、収集することに関するワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="812bb-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="812bb-105">電子情報開示では、これらの個人は*data 保管担当者*(または*保管担当者*) と呼ばれ、"ドキュメントまたは電子ファイルの管理制御を持つ人" として定義されています。</span><span class="sxs-lookup"><span data-stu-id="812bb-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="812bb-106">たとえば、電子メールメッセージの保管担当者は、関連するメッセージが含まれるメールボックスの所有者である場合があります。</span><span class="sxs-lookup"><span data-stu-id="812bb-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>  

<span data-ttu-id="812bb-107">調査の開始時に、電子情報開示チームは、ケースに関連するすべての関連保管担当者とデータソースを迅速に特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="812bb-107">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="812bb-108">時間の経過と共に、保管担当者のリストとそのデータソースが増減することがあります。</span><span class="sxs-lookup"><span data-stu-id="812bb-108">Over time, the list of custodians and their data sources may increase or decrease.</span></span> <span data-ttu-id="812bb-109">その結果、組織は、ケースのライフサイクルを通じて、custodial コンテンツを識別、保持、および収集するための制御されたプロセスを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="812bb-109">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="812bb-110">高度な電子情報開示ケースでは、法務部門が組織内の個人を保管担当者として追加し、Exchange メールボックス、OneDrive アカウント、SharePoint、Teams サイトなどの、custodial データソースを自動的に識別して保持することができます。</span><span class="sxs-lookup"><span data-stu-id="812bb-110">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="812bb-111">高度な電子情報開示の組み込みの保管担当者管理ツールを使用することにより、組織は不用意 (または故意) による削除から電子的に保存された情報を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="812bb-111">By using the built-in custodian management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="812bb-112">これにより、訴訟ホールドプロセスを手動で実行するための時間がかかり、エラーが発生しやすいプロセスを排除することができます。</span><span class="sxs-lookup"><span data-stu-id="812bb-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span> 

<span data-ttu-id="812bb-113">保管担当者の使用の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="812bb-113">For more information about working with custodians, see the following:</span></span> 

- [<span data-ttu-id="812bb-114">ケースにカストディアンを追加する</span><span class="sxs-lookup"><span data-stu-id="812bb-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="812bb-115">ケースで保管担当者を管理する</span><span class="sxs-lookup"><span data-stu-id="812bb-115">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="812bb-116">カストディアンのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="812bb-116">View custodian activity</span></span>](view-custodian-activity.md)
