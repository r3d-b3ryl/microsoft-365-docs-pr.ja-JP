---
title: データプライバシー規制の対象となる情報を管理する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 の保持ラベルとポリシーを使用して、Microsoft 365 環境で個人データを管理します。
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928438"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="805df-103">データプライバシー規制の対象となる情報を管理する</span><span class="sxs-lookup"><span data-stu-id="805df-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="805df-104">情報ガバナンス管理は、一般データ保護規則 (GDPR)、HIPAA-HITECH (米国の医療プライバシー法)、カリフォルニア州消費者保護法 (CCPA)、およびブラジルデータ保護法 (LGPD) に固有の番号を含む、データ プライバシーコンプライアンスのニーズに対応するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="805df-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="805df-105">これらのコントロールは、主に次のソリューション領域に含まれます。</span><span class="sxs-lookup"><span data-stu-id="805df-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="805df-106">保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="805df-106">Retention policies</span></span>
- <span data-ttu-id="805df-107">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="805df-107">Retention labels</span></span>
- <span data-ttu-id="805df-108">レコード管理</span><span class="sxs-lookup"><span data-stu-id="805df-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="805df-109">情報ガバナンス管理に影響を与えるデータプライバシー規制</span><span class="sxs-lookup"><span data-stu-id="805df-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="805df-110">情報ガバナンス制御に関連する可能性があるデータプライバシー規制の一覧の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="805df-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="805df-111">GDPR 記事 (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="805df-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="805df-112">GDPR 記事 (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="805df-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="805df-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="805df-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="805df-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="805df-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="805df-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="805df-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="805df-116">LGPD 第 46 条</span><span class="sxs-lookup"><span data-stu-id="805df-116">LGPD Article 46</span></span>

<span data-ttu-id="805df-117">これらの規制の詳細については、「データプライバシーリスクを評価し、機密情報を [特定する」の記事を参照してください](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="805df-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="805df-118">情報ガバナンスの場合、通常、データプライバシー規制では次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="805df-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="805df-119">Microsoft 365 に保存されている個人データの保持と削除に関する技術的なスキームを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="805df-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="805df-120">個人データを保存する場合は、データの保存期間を件名に通知します。これは、フロントエンド Web システムでの標準的な方法です。</span><span class="sxs-lookup"><span data-stu-id="805df-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="805df-121">個人データは、検証可能な方法を使用して、偶発的な処理、損失、または変更から保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="805df-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="805df-122">個人データに対して実行されるアクションは文書化する必要があります。そのドキュメントは指定された期間保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="805df-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="805df-123">データの保持と削除に関しては、データのプライバシーに関する規制は非常に具体的ではないので、Microsoft 365 サブスクリプションに保存されている個人情報に関する情報ガバナンス ガイドラインを決定する可能性があるその他の要因を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="805df-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="805df-124">いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="805df-124">Here are a few examples:</span></span>

- <span data-ttu-id="805df-125">5 年間の非アクティブ化後にコンシューマー アカウントをエージングし、その時点以降にアカウント データを削除または匿名化する必要があります。通知や他の自動化に関連するデータとワークフローを格納するシステム間のオーケストレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="805df-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="805df-126">GDPR に関連するポリシーと手順を、ポリシーと手順の保持スケジュールに合わせて組織の保持スケジュールに合わせて 3 年間保持するためのルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="805df-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="805df-127">サポート組織を通じて消費者と通信するための個別のサブスクリプションを維持する。</span><span class="sxs-lookup"><span data-stu-id="805df-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="805df-128">すべての電子メール通信は、システム内のプライバシー負債の増加を減らすために、2 週間後に保持および削除されました。</span><span class="sxs-lookup"><span data-stu-id="805df-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="805df-129">答える重要な質問は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="805df-129">A key question to answer is:</span></span> 

- <span data-ttu-id="805df-130">ビジネス上の有効な理由から、個人データを含む情報を保持し、"永遠に保つ" 方法を避ける必要がある期間。</span><span class="sxs-lookup"><span data-stu-id="805df-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="805df-131">これは、ビジネス継続性の保持ニーズとバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="805df-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="805df-132">個人情報を保持または削除する法的およびビジネス上の理由に関係なく、Microsoft は Microsoft 365 でデータ ガバナンス スキームを実装するためのさまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="805df-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="805df-133">Microsoft 365 での情報ガバナンスの管理</span><span class="sxs-lookup"><span data-stu-id="805df-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="805df-134">まず、「Manage [information Governance and Data](../compliance/manage-information-governance.md) [Retention, Deletion and Destruction in Microsoft 365」を参照してください](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="805df-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="805df-135">コンテナー、電子メール、およびコンテンツのデータ保持スケジュールを開発する</span><span class="sxs-lookup"><span data-stu-id="805df-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="805df-136">以下の点にご注意ください:</span><span class="sxs-lookup"><span data-stu-id="805df-136">Keep the following in mind:</span></span>

- <span data-ttu-id="805df-137">定義された情報の種類のデータ保持スケジュールを確立するには、保持または削除のスキームを実装するための前提条件と見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="805df-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="805df-138">ほとんどの組織が重要と考える情報の種類の数と、それに沿った対応する大規模なレコード保持スケジュールを考えると、データ保持とレコード管理戦略を実装するには計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="805df-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="805df-139">この種類の効果的なデータ ガバナンス戦略を確立する鍵は、より正式な管理を必要とする最も優先度の高いビジネス機能と情報の種類に焦点を当てすることです。</span><span class="sxs-lookup"><span data-stu-id="805df-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="805df-140">例としては、法的契約、財務諸表、および規制コンプライアンスに関するドキュメントがあります。</span><span class="sxs-lookup"><span data-stu-id="805df-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="805df-141">単一の情報の種類ごとに個別の保持スケジュールを設定しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="805df-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="805df-142">一般的なビジネス コンテンツの保持スケジュールが 7 年など、可能な限り一般的なカテゴリを使用してください。</span><span class="sxs-lookup"><span data-stu-id="805df-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="805df-143">環境内の個人情報の種類がよりよく知られたら、この種類のコンテンツの保持と削除のスケジュールを確立し、このような情報のガバナンスを容易にするために情報アーキテクチャを調整します。</span><span class="sxs-lookup"><span data-stu-id="805df-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="805df-144">たとえば、アクセスを制御する個別のサイト、ライブラリ、またはフォルダーで個人情報を分離します。</span><span class="sxs-lookup"><span data-stu-id="805df-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="805df-145">アイテム保持ポリシーと保持ラベル</span><span class="sxs-lookup"><span data-stu-id="805df-145">Retention policies and retention labels</span></span>

<span data-ttu-id="805df-146">アイテム [保持ポリシーと保持ラベルを使用](../compliance/retention.md) して、個人データを含む、または含まれると予想される Microsoft 365 のコンテンツを保持または削除します。</span><span class="sxs-lookup"><span data-stu-id="805df-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="805df-147">レコード管理</span><span class="sxs-lookup"><span data-stu-id="805df-147">Records management</span></span>

<span data-ttu-id="805df-148">コンテンツをレコードとして宣言する保持ラベルを使用して[](../compliance/records-management.md)、Microsoft 365 のデータのレコード管理ソリューションを実装します。</span><span class="sxs-lookup"><span data-stu-id="805df-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="805df-149">データのプライバシーを保護するために、法務部門が受け取ったデータ主体要求 (DSR) はレコードとして宣言され、規制活動保持仕様に準拠するために無期限に保存または証拠付き廃棄することができます。</span><span class="sxs-lookup"><span data-stu-id="805df-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>