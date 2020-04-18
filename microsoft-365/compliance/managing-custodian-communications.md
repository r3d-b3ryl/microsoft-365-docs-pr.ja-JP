---
title: 高度な電子情報開示で通信を処理する
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
description: 高度な電子情報開示を使用すると、法的調査の保管担当者に関する法的情報保持通知ワークフローを簡単に管理できます。
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551245"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="7a18d-103">高度な電子情報開示で通信を処理する</span><span class="sxs-lookup"><span data-stu-id="7a18d-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="7a18d-104">上級電子情報開示を使用すると、法務部門は法的情報保留通知の追跡と配布に関するプロセスを簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="7a18d-105">保管担当者 communications tool を使用すると、法務部門は、最初の通知から、アラーム、およびエスカレーションを1か所で管理し、法的情報保留プロセス全体を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="7a18d-106">法的情報保留通知とは</span><span class="sxs-lookup"><span data-stu-id="7a18d-106">What is a legal hold notification?</span></span>

<span data-ttu-id="7a18d-107">法的情報保留 (*訴訟ホールド*とも呼ばれます) 通知とは、組織の法務部門から従業員、臨時スタッフ、または法的調査に関連する可能性がある保管担当者データに送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="7a18d-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="7a18d-108">これらの通知は、電子的に保存された情報と、アクティブまたは差し迫った法的事項に関連する可能性があるコンテンツを保持するように保管担当者に指示します。</span><span class="sxs-lookup"><span data-stu-id="7a18d-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="7a18d-109">法務部門のチームは、それぞれの保管担当者が受信、読み取り、理解、および所定の手順に準拠していることを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a18d-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="7a18d-110">法的情報保留通知プロセス</span><span class="sxs-lookup"><span data-stu-id="7a18d-110">The legal hold notification process</span></span>

<span data-ttu-id="7a18d-111">組織には、訴訟や規制に関する調査について学習したときに、関連する情報を保持するための職務があります。</span><span class="sxs-lookup"><span data-stu-id="7a18d-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="7a18d-112">調査の保持要件に準拠するために、組織はすぐに必要な情報を保持するために、自分の責務に関する保管担当者についてすぐに通知を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a18d-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="7a18d-113">高度な電子情報開示を使用すると、法務チームは法的情報保留通知ワークフローを作成およびカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="7a18d-114">保管担当者 communications tool を使用すると、法務部門が以下の通知とワークフローを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="7a18d-115">**発行通知:** 法務部門から保管担当者への通知によって法的情報保留通知が発行 (または開始) された場合は、ケースに関する関連情報があるか。</span><span class="sxs-lookup"><span data-stu-id="7a18d-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="7a18d-116">この通知は、検出に必要なすべての情報を保持するように保管担当者に指示します。</span><span class="sxs-lookup"><span data-stu-id="7a18d-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="7a18d-117">**再発行の通知:** ケースでは、以前に要求されたものよりも多くのコンテンツ (またはコンテンツを保持する) を保管担当者する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a18d-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="7a18d-118">このシナリオでは、既存の保留通知を更新して、保管担当者に再発行することができます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="7a18d-119">**リリース通知:** 問題が解決され、保管担当者が保持要件の対象ではなくなると、保管担当者をケースからリリースできます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="7a18d-120">さらに、コンテンツを保持する必要がなくなったことを保管担当者に通知し、そのデータに関して通常の作業アクティビティを再開する方法についての指示を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="7a18d-121">**アラームとエスカレーション:** 場合によっては、法的証拠開示の要件を満たすのに十分な通知を発行するだけではありません。</span><span class="sxs-lookup"><span data-stu-id="7a18d-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="7a18d-122">各通知で、法務部門は、応答のない保管担当者を自動的にフォローアップする一連のアラームおよびエスカレーションワークフローをスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="7a18d-123">**アラーム:** 法的情報保留通知を発行した後、または保管担当者のセットに再発行した後、応答しない保管担当者に警告する通知を組織で設定できます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="7a18d-124">**エスカレーション:** 場合によっては、長期間にわたってアラームのセットがあっても、保管担当者が応答しない場合、訴訟チームは応答のない保管担当者とその上司に通知するエスカレーションワークフローを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7a18d-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="7a18d-125">保管担当者通信プロセスの管理の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a18d-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="7a18d-126">法的情報保留通知を作成する</span><span class="sxs-lookup"><span data-stu-id="7a18d-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="7a18d-127">通信エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="7a18d-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="7a18d-128">保留通知を管理する</span><span class="sxs-lookup"><span data-stu-id="7a18d-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="7a18d-129">保留通知を確認する</span><span class="sxs-lookup"><span data-stu-id="7a18d-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)