---
title: Office 365 の自動調査と応答
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の使用を開始します。
ms.openlocfilehash: d777ca0a61655c8df16d62c72691195bdec330a9
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175781"
---
# <a name="office-365-automated-investigation-and-response"></a><span data-ttu-id="f41cb-104">Office 365 の自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="f41cb-104">Office 365 automated investigation and response</span></span>

<span data-ttu-id="f41cb-105">[Office 365 Advanced Threat Protection](office-365-atp.md)Plan 2 には、セキュリティ運用チームの時間と労力を節約できる強力な自動化された調査と応答 (AIR) 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f41cb-105">[Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2 includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="f41cb-106">特定のアラートがトリガーされると、1つ以上のセキュリティプレイブックが開始され、自動調査プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-106">When certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="f41cb-107">これにより、セキュリティ運用チームが、トリガーされた通知を失うことなく、優先度の高いタスクに集中できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f41cb-107">This empowers your security operations team to focus on high-priority tasks without losing sight of alerts that are triggered.</span></span> 

<span data-ttu-id="f41cb-108">AIR の流れは大まかには次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f41cb-108">At a high level, the AIR flow works like this:</span></span>

|<span data-ttu-id="f41cb-109">手順</span><span class="sxs-lookup"><span data-stu-id="f41cb-109">Step</span></span>  |<span data-ttu-id="f41cb-110">結果</span><span class="sxs-lookup"><span data-stu-id="f41cb-110">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="f41cb-111">1-d</span><span class="sxs-lookup"><span data-stu-id="f41cb-111">1</span></span>     |<span data-ttu-id="f41cb-112">通知は Office イベントによってトリガーされ、[セキュリティのプレイブック](automated-investigation-response-office.md#security-playbooks)は選択した通知の自動調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="f41cb-112">An alert is triggered by an Office event and a [security playbook](automated-investigation-response-office.md#security-playbooks) initiates an automated investigation for selected alerts.</span></span> <br/><br/><span data-ttu-id="f41cb-113">あるいは、セキュリティアナリストは、[脅威エクスプローラー](threat-explorer.md)を使用して自動化され[た調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)することもできます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-113">Alternately, a security analyst can [trigger an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>        |
|<span data-ttu-id="f41cb-114">pbm-2</span><span class="sxs-lookup"><span data-stu-id="f41cb-114">2</span></span>     |<span data-ttu-id="f41cb-115">自動調査を実行すると、電子メールとその電子メールに関連するエンティティ (ファイル、Url、受信者) に関する追加データが収集されます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-115">While an automated investigation runs, it gathers additional data about the email and the entities related to that email – files, URLs, and recipients.</span></span>  <span data-ttu-id="f41cb-116">新しい関連する警告がトリガーされると、調査のスコープが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f41cb-116">The investigation's scope can increase, as new related alerts are triggered.</span></span>         |
|<span data-ttu-id="f41cb-117">1/3</span><span class="sxs-lookup"><span data-stu-id="f41cb-117">3</span></span>     |<span data-ttu-id="f41cb-118">自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-118">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="f41cb-119">結果には、検出された脅威に対処し、修復を行うためにとることができる[推奨処理](air-remediation-actions.md) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-119">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="f41cb-120">また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-120">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span><br/><br/><span data-ttu-id="f41cb-121">組織でカスタム レポート ソリューションまたはサード パーティのソリューションを使用している場合は、[Office 365 マネージメント アクティビティ API を使用して](air-custom-reporting.md)自動調査と脅威に関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-121">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>         |
|<span data-ttu-id="f41cb-122">2/4</span><span class="sxs-lookup"><span data-stu-id="f41cb-122">4</span></span>     |<span data-ttu-id="f41cb-123">セキュリティ運用チームは、[調査結果と推奨事項](air-view-investigation-results.md)を確認し、[修復アクションを承認](air-remediation-actions.md#approve-or-reject-pending-actions)します。</span><span class="sxs-lookup"><span data-stu-id="f41cb-123">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves remediation actions](air-remediation-actions.md#approve-or-reject-pending-actions).</span></span> <span data-ttu-id="f41cb-124">Office 365 では、アクションは自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="f41cb-124">In Office 365, no actions are taken automatically.</span></span> <span data-ttu-id="f41cb-125">修復処理は、組織のセキュリティチームによる承認時にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-125">Remediation actions are taken only upon approval by your organization's security team.</span></span>         |

<span data-ttu-id="f41cb-126">自動化された調査プロセスにおいて、セキュリティチームは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f41cb-126">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="f41cb-127">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="f41cb-127">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [<span data-ttu-id="f41cb-128">調査の結果の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="f41cb-128">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)
- [<span data-ttu-id="f41cb-129">調査の結果としてアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="f41cb-129">Review and approve actions as a result of an investigation</span></span>](air-remediation-actions.md#approve-or-reject-pending-actions)

<span data-ttu-id="f41cb-130">詳細については、「[エアのしくみ](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f41cb-130">To learn more, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>