---
title: 通信のコンプライアンスを計画する
description: 組織での通信コンプライアンスの使用の計画について説明します。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045852"
---
# <a name="plan-for-communication-compliance"></a><span data-ttu-id="0ac10-103">通信のコンプライアンスを計画する</span><span class="sxs-lookup"><span data-stu-id="0ac10-103">Plan for communication compliance</span></span>

<span data-ttu-id="0ac10-104">組織での[通信のコンプライアンス](communication-compliance.md)を開始する前に、情報技術およびコンプライアンス管理チームが検討する必要がある重要なアクティビティと考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="0ac10-104">Before getting started with [communication compliance](communication-compliance.md) in your organization, there are important planning activities and considerations that should be reviewed by your information technology and compliance management teams.</span></span> <span data-ttu-id="0ac10-105">以下の領域での展開を完全に理解し、計画することで、コミュニケーション機能の実装と使用がスムーズに進み、ソリューションのベストプラクティスに沿ったものになることができます。</span><span class="sxs-lookup"><span data-stu-id="0ac10-105">Thoroughly understanding and planning for deployment in the following areas will help ensure that your implementation and use of communication compliance features goes smoothly and is aligned with the best practices for the solution.</span></span>

## <a name="work-with-stakeholders-in-your-organization"></a><span data-ttu-id="0ac10-106">組織内の関係者と連携する</span><span class="sxs-lookup"><span data-stu-id="0ac10-106">Work with stakeholders in your organization</span></span>

<span data-ttu-id="0ac10-107">コミュニケーションコンプライアンス通知に対してアクションを実行するために、組織内の適切なステークホルダーを特定します。</span><span class="sxs-lookup"><span data-stu-id="0ac10-107">Identify the appropriate stakeholders in your organization to collaborate for taking actions on communication compliance alerts.</span></span> <span data-ttu-id="0ac10-108">最初の計画とエンドツーエンドの[コミュニケーションのコンプライアンスワークフロー](communication-compliance.md#workflow)については、組織の次の分野に属するユーザーが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="0ac10-108">Some recommended stakeholders to consider including in initial planning and the end-to-end [communication compliance workflow](communication-compliance.md#workflow) are people from the following areas of your organization:</span></span>

- <span data-ttu-id="0ac10-109">情報技術</span><span class="sxs-lookup"><span data-stu-id="0ac10-109">Information technology</span></span>
- <span data-ttu-id="0ac10-110">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="0ac10-110">Compliance</span></span>
- <span data-ttu-id="0ac10-111">プライバシー</span><span class="sxs-lookup"><span data-stu-id="0ac10-111">Privacy</span></span>
- <span data-ttu-id="0ac10-112">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0ac10-112">Security</span></span>
- <span data-ttu-id="0ac10-113">人事</span><span class="sxs-lookup"><span data-stu-id="0ac10-113">Human resources</span></span>
- <span data-ttu-id="0ac10-114">法務</span><span class="sxs-lookup"><span data-stu-id="0ac10-114">Legal</span></span>

## <a name="plan-for-the-investigation-and-remediation-workflow"></a><span data-ttu-id="0ac10-115">調査と修復のワークフローを計画する</span><span class="sxs-lookup"><span data-stu-id="0ac10-115">Plan for the investigation and remediation workflow</span></span>

<span data-ttu-id="0ac10-116">[専任のレビュー担当者] を選択して、 [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)の通常のリズムで警告を監視および確認します。</span><span class="sxs-lookup"><span data-stu-id="0ac10-116">Select dedicated reviewers to monitor and review the alerts on a regular cadence in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="0ac10-117">[新しい役割グループを作成](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)して、**監督レビュー管理者**、**ケース管理**、**コンプライアンス管理者**、および**レビュー**の役割を持つレビュー担当者のアクセス許可を有効にして、ポリシーが一致するメッセージを調査および修復する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ac10-117">Remember, you’ll need to [create a new role group](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) to enable permissions for reviewers with the **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

## <a name="plan-for-policies"></a><span data-ttu-id="0ac10-118">ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="0ac10-118">Plan for policies</span></span>

<span data-ttu-id="0ac10-119">通信コンプライアンスポリシーの作成は、不快感を持たない言語、機密情報、および規制へのコンプライアンスに関する[事前定義さ](communication-compliance-feature-reference.md#policy-templates)れたテンプレートを使用して、迅速かつ簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ac10-119">Creating communication compliance policies is quick and easy with the [pre-defined templates](communication-compliance-feature-reference.md#policy-templates) for offensive language, sensitive information, and regulatory compliance.</span></span> <span data-ttu-id="0ac10-120">カスタム通信コンプライアンスポリシーを使用すると、組織や要件に固有の問題の検出と調査が柔軟になります。</span><span class="sxs-lookup"><span data-stu-id="0ac10-120">Custom communication compliance policies allow the flexibility for detecting and investigation issues specific to your organization and requirements.</span></span>

<span data-ttu-id="0ac10-121">通信コンプライアンスポリシーを計画する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="0ac10-121">When planning for communication compliance policies, consider the following:</span></span>

- <span data-ttu-id="0ac10-122">コミュニケーションコンプライアンスポリシーの範囲内として、組織内のすべてのユーザーを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0ac10-122">Consider adding all users in your organization as in-scope for your communication compliance policies.</span></span> <span data-ttu-id="0ac10-123">特定のユーザーを個々のポリシーのスコープ内で識別することは、状況によっては便利ですが、多くの組織では、嫌がらせまたは差別検出のために最適化された通信コンプライアンスポリシーのすべてのユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac10-123">Identifying specific users as in-scope for individual policies are useful in some circumstances, however most organizations should include all users in communication compliance policies optimized for harassment or discrimination detection.</span></span>
- <span data-ttu-id="0ac10-124">セットアップを簡単にするために、コミュニケーションをレビューする必要があるユーザーのグループを作成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0ac10-124">To simplify your setup, consider creating groups for people who need their communications reviewed.</span></span> <span data-ttu-id="0ac10-125">グループを使用している場合いくつかの必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ac10-125">If you're using groups; you might need several.</span></span> <span data-ttu-id="0ac10-126">たとえば、2つの異なるユーザーグループ間の通信をスキャンする場合、または、監視されていないグループを指定する場合です。</span><span class="sxs-lookup"><span data-stu-id="0ac10-126">For example, if you want to scan communications between two distinct groups of people, or if you want to specify a group that isn't supervised.</span></span>
- <span data-ttu-id="0ac10-127">確認する通信のパーセンテージを100% に構成して、ポリシーが組織の通信に関する懸念のすべての問題をキャッチするようにします。</span><span class="sxs-lookup"><span data-stu-id="0ac10-127">Configure the percentage of communications to review at 100% to ensure that policies are catching all issues of concern in communications for your organization.</span></span>
- <span data-ttu-id="0ac10-128">Microsoft 365 組織のメールボックスにインポートされたデータについては、[サードパーティ製のソース](communication-compliance-feature-reference.md#supported-communication-types)からの通信をスキャンすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ac10-128">You can scan communications from [third-party sources](communication-compliance-feature-reference.md#supported-communication-types) for data imported into mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="0ac10-129">これらのプラットフォームでの通信の確認を含めるには、これらのサービスへのコネクタを構成して、メッセージの会議ポリシーの条件が通信ポリシーによって監視されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac10-129">To include review of communications in these platforms, you’ll need to configure a connector to these services before messages meeting policy conditions are monitored by communication policy.</span></span>
- <span data-ttu-id="0ac10-130">ポリシーでは、カスタム通信コンプライアンスポリシーの英語以外の監視言語をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="0ac10-130">Policies can support monitoring languages other than English in custom communication compliance policies.</span></span> <span data-ttu-id="0ac10-131">任意の言語で[ユーザー設定のキーワード辞書](communication-compliance-feature-reference.md#custom-keyword-dictionaries)を作成するか、Microsoft 365 の[trainable 分類子](classifier-getting-started-with.md)を使用して独自の machine learning モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ac10-131">Build a [custom keyword dictionary](communication-compliance-feature-reference.md#custom-keyword-dictionaries) of offensive words in the language of your choice or build your own machine-learning model using [trainable classifiers](classifier-getting-started-with.md) in Microsoft 365.</span></span>
- <span data-ttu-id="0ac10-132">すべての組織には、異なる通信基準とポリシーニーズがあります。</span><span class="sxs-lookup"><span data-stu-id="0ac10-132">All organizations have different communication standards and policy needs.</span></span> <span data-ttu-id="0ac10-133">特定の種類の情報については、通信コンプライアンス[ポリシーの条件](communication-compliance-feature-reference.md#conditional-settings)またはモニターを使用して、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md)を使用して特定のキーワードを監視します。</span><span class="sxs-lookup"><span data-stu-id="0ac10-133">Monitor for specific keywords using communication compliance [policy conditions](communication-compliance-feature-reference.md#conditional-settings) or monitor for specific types of information with [custom sensitive information types](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="0ac10-134">始める準備はいいですか。</span><span class="sxs-lookup"><span data-stu-id="0ac10-134">Ready to get started?</span></span>

<span data-ttu-id="0ac10-135">Microsoft 365 組織の通信コンプライアンスを構成する方法については、「 [configure communications コンプライアンス For microsoft 365](communication-compliance-configure.md) 」または「 [Contoso 社向けのケーススタディ](communication-compliance-case-study.md)」を参照してください。また、Microsoft Teams、Exchange Online、Yammer の通信で不快な言葉を監視するための通信コンプライアンスポリシーをどのように構成したかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ac10-135">To configure communication compliance for your Microsoft 365 organization, see [Configure communication compliance for Microsoft 365](communication-compliance-configure.md) or check out the [case study for Contoso](communication-compliance-case-study.md) and how they quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications.</span></span>
