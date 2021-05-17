---
title: ネットワーク内の通信をAdvanced eDiscovery
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
description: Advanced eDiscovery、法的調査で保管担当者に通知する方法に関する法的ホールド通知ワークフローを簡単に管理できます。
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551245"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="a4cd1-103">ネットワーク内の通信をAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a4cd1-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="a4cd1-104">Advanced eDiscovery部門は、法的ホールド通知の追跡と配布に関するプロセスを簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="a4cd1-105">カストディアン通信ツールを使用すると、法務部門は、最初の通知からリマインダー、エスカレーションまで、法的保持プロセス全体を 1 つの場所で管理および自動化できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="a4cd1-106">法的保留通知とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="a4cd1-106">What is a legal hold notification?</span></span>

<span data-ttu-id="a4cd1-107">訴訟ホールド (訴訟ホールドとも呼 *ばれる)* 通知とは、組織の法務部門から、法的調査に関連する可能性のあるデータの従業員、または保管担当者に送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="a4cd1-108">これらの通知は、保管担当者に対して、電子的に保存された情報と、アクティブまたは差し迫った法的問題に関連する可能性のあるコンテンツを保持するよう指示します。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="a4cd1-109">法務チームは、各保管担当者が特定の指示を受け取り、読み、理解し、遵守することに同意したと知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="a4cd1-110">法的保留通知プロセス</span><span class="sxs-lookup"><span data-stu-id="a4cd1-110">The legal hold notification process</span></span>

<span data-ttu-id="a4cd1-111">組織は、差し迫った訴訟や規制調査について知った場合、関連情報を保持する義務があります。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="a4cd1-112">調査の保存要件に準拠するために、組織は、関連する情報を保持する義務について、潜在的な保管担当者に直ちに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="a4cd1-113">このAdvanced eDiscovery、法務チームは法的ホールド通知ワークフローを作成およびカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="a4cd1-114">カストディアン通信ツールを使用すると、法務チームは次の通知とワークフローを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="a4cd1-115">**発行通知:** 法的ホールド通知は、法務部門からケースに関する関連情報を持っている可能性のある保管担当者への通知によって発行 (または開始) されます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="a4cd1-116">この通知は、検出に必要なすべての情報を保存するようにカストディアンに指示します。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="a4cd1-117">**再発行に関する通知:** 場合によっては、以前に要求されたコンテンツよりも追加のコンテンツ (または少ないコンテンツ) を保持するために保管担当者が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="a4cd1-118">このシナリオでは、既存の保留通知を更新し、保管担当者に再発行できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="a4cd1-119">**リリース通知:** 問題が解決され、保管担当者が保存要件の対象とならなくなったら、保管担当者をケースから解放できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="a4cd1-120">さらに、保管担当者にコンテンツを保持する必要がなくなったと通知し、データに関する通常の作業アクティビティを再開する方法について指示を提供できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="a4cd1-121">**アラームとエスカレーション:** 場合によっては、通知を発行するだけで、法的な検出要件を満たすには十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="a4cd1-122">各通知によって、訴訟チームは、アラームやエスカレーションのワークフローのセットをスケジュールして、応答しないカストディアンに対して自動的にフォローアップします。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="a4cd1-123">**アラーム:** 一連の保管担当者に対して法的保留通知が発行または再発行された後、組織は応答しない保管担当者に警告するアラームを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="a4cd1-124">**エスカレーション:** 一定の期間に一連のアラームが発生しても保管担当者が応答しない場合、法務チームはエスカレーション ワークフローを設定して、応答しない保管担当者とそのマネージャーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="a4cd1-125">カストディアン通信プロセスの管理の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4cd1-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="a4cd1-126">法的保留通知を作成する</span><span class="sxs-lookup"><span data-stu-id="a4cd1-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="a4cd1-127">通信エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="a4cd1-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="a4cd1-128">保留通知を管理する</span><span class="sxs-lookup"><span data-stu-id="a4cd1-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="a4cd1-129">保留通知を確認する</span><span class="sxs-lookup"><span data-stu-id="a4cd1-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)