---
title: データプライバシーの規則に従って情報を管理する
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
ms.custom: ''
description: Microsoft 365 の保持ラベルとポリシーを使用して、Microsoft 365 環境の個人データを管理します。
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522303"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="796a7-103">データプライバシーの規則に従って情報を管理する</span><span class="sxs-lookup"><span data-stu-id="796a7-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="796a7-104">お客様の環境では、情報ガバナンス制御を使用して、一般的なデータ保護規則 (GDPR)、HIPAA ヒット回数 (米国の医療保険法)、カリフォルニアのコンシューマー保護法 (CCPA)、およびブラジルのデータ保護法 (LGPD) に固有の数値など、データのプライバシーに関するコンプライアンス要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="796a7-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="796a7-105">これらのコントロールは、主に次のソリューション領域に分類されます。</span><span class="sxs-lookup"><span data-stu-id="796a7-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="796a7-106">保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="796a7-106">Retention policies</span></span>
- <span data-ttu-id="796a7-107">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="796a7-107">Retention labels</span></span>
- <span data-ttu-id="796a7-108">レコード管理</span><span class="sxs-lookup"><span data-stu-id="796a7-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="796a7-109">情報ガバナンス統制に影響を与えるデータプライバシー規制</span><span class="sxs-lookup"><span data-stu-id="796a7-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="796a7-110">以下は、情報ガバナンス統制に関連する可能性があるデータプライバシー規制の例です。</span><span class="sxs-lookup"><span data-stu-id="796a7-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="796a7-111">GDPR 記事 (13) (2) (a)</span><span class="sxs-lookup"><span data-stu-id="796a7-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="796a7-112">GDPR 記事 (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="796a7-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="796a7-113">HIPAA のエコー (45 CFR 164.312 (c) (2))</span><span class="sxs-lookup"><span data-stu-id="796a7-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="796a7-114">HIPAA のエコー (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="796a7-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="796a7-115">HIPAA のエコー (45 CFR 164.316 (b) (1) (ii))</span><span class="sxs-lookup"><span data-stu-id="796a7-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="796a7-116">LGPD 記事46</span><span class="sxs-lookup"><span data-stu-id="796a7-116">LGPD Article 46</span></span>

<span data-ttu-id="796a7-117">これらの規則の詳細については、「[データプライバシーのリスクを評価し、機密情報を特定](information-protection-deploy-assess.md)する」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="796a7-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="796a7-118">情報ガバナンスでは、通常、次のようなデータプライバシー規制が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="796a7-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="796a7-119">Microsoft 365 に保存されている個人データの保存と削除については、技術的なスキームを採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="796a7-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="796a7-120">個人データを保存する場合は、データが格納される期間について、フロントエンド web システムの標準プラクティスであることを伝えます。</span><span class="sxs-lookup"><span data-stu-id="796a7-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="796a7-121">個人データは、検証可能な方法を使用して、偶発的な処理、損失、または変更から保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="796a7-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="796a7-122">個人データに対して実行されたアクションを文書化し、そのドキュメントを指定した期間保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="796a7-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="796a7-123">データの保存と削除に関しては、データプライバシーに関する規制は特に定められていないため、Microsoft 365 サブスクリプションに保存されている個人情報に関する情報ガバナンスガイドラインを考慮する必要があるという、他の要素を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="796a7-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="796a7-124">いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="796a7-124">Here are a few examples:</span></span>

- <span data-ttu-id="796a7-125">非アクティブな状態が5年後に消費者アカウントを削除し、その時点以降のアカウントデータの削除または匿名化を必要とするため、データを格納するシステムと通知やその他の自動化に関連するワークフローの間にオーケストレーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="796a7-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="796a7-126">GDPR に関連するポリシーと手順を、優先された後の3年間保持するルールを構成します。これらは、ポリシーと手順の組織の保持スケジュールと連携しています。</span><span class="sxs-lookup"><span data-stu-id="796a7-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="796a7-127">サポート組織からコンシューマーと通信するための個別のサブスクリプションを維持する。</span><span class="sxs-lookup"><span data-stu-id="796a7-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="796a7-128">すべての電子メール通信は、2週間後に保持され、システムでのプライバシーの借入金が減少します。</span><span class="sxs-lookup"><span data-stu-id="796a7-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="796a7-129">回答する主な質問は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="796a7-129">A key question to answer is:</span></span> 

- <span data-ttu-id="796a7-130">「無期限に保持する」の手順を回避するために、個人データを含む情報が有効なビジネス上の理由で保持される期間。</span><span class="sxs-lookup"><span data-stu-id="796a7-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="796a7-131">これは、ビジネス継続性の保持ニーズとバランスをとる必要があります。</span><span class="sxs-lookup"><span data-stu-id="796a7-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="796a7-132">個人情報を保存または削除する法的および業務上の理由に関係なく、microsoft では Microsoft 365 でデータガバナンススキームを実装するためのさまざまな機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="796a7-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="796a7-133">Microsoft 365 での情報ガバナンスの管理</span><span class="sxs-lookup"><span data-stu-id="796a7-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="796a7-134">開始するには、「Microsoft 365 での[情報ガバナンス](../compliance/manage-information-governance.md)と[データの保存、削除、破棄](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="796a7-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="796a7-135">コンテナー、電子メール、およびコンテンツのデータ保持スケジュールを開発する</span><span class="sxs-lookup"><span data-stu-id="796a7-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="796a7-136">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="796a7-136">Keep the following in mind:</span></span>

- <span data-ttu-id="796a7-137">定義された情報の種類についてデータ保持スケジュールを確立することは、保持または削除のスキームを実装するための前提条件と考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="796a7-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="796a7-138">多くの組織で重要と考えられている情報の種類の数と、それに対応する大規模レコードの保持スケジュールについては、計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="796a7-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="796a7-139">この種の効果的なデータガバナンス戦略を確立するための鍵は、より正式な管理を必要とする最も優先度の高いビジネス機能と情報の種類に焦点を当てることです。</span><span class="sxs-lookup"><span data-stu-id="796a7-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="796a7-140">例としては、法的契約、財務諸表、法令遵守のドキュメントが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="796a7-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="796a7-141">単一の情報の種類ごとに個別の保持スケジュールを使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="796a7-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="796a7-142">一般的なビジネスコンテンツの保持スケジュール (たとえば、7年間の保持スケジュール) を使用して、可能な限り一般的なカテゴリを使用してください。</span><span class="sxs-lookup"><span data-stu-id="796a7-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="796a7-143">お客様の環境内の個人情報の種類がよく知られている場合は、この種のコンテンツの保持と削除のスケジュールを確立し、情報アーキテクチャを調整してこの種の情報をより簡単に管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="796a7-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="796a7-144">たとえば、個別のサイト、ライブラリ、またはフォルダー内の個人情報を分離してアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="796a7-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="796a7-145">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="796a7-145">Retention policies</span></span>

<span data-ttu-id="796a7-146">自動的に適用されるサイト内のコンテンツの[保持ポリシー](../compliance/retention-policies.md)を作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="796a7-146">Create and deploy [retention policies](../compliance/retention-policies.md) for content in sites that are automatically applied.</span></span>

<span data-ttu-id="796a7-147">個人データを含むまたはを含んでいるサイトのデータのプライバシーを保護するには、組織の標準に対応するための保持ルールまたは削除ルールを指定します。</span><span class="sxs-lookup"><span data-stu-id="796a7-147">For data privacy for sites that contain or are expected to contain personal data, specify retention or deletion rules to address organizational standards.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="796a7-148">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="796a7-148">Retention labels</span></span>

<span data-ttu-id="796a7-149">コンテンツとメールの[保持ラベル](../compliance/labels.md)を作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="796a7-149">Create and deploy [retention labels](../compliance/labels.md) for content and email.</span></span>

<span data-ttu-id="796a7-150">個人データが含まれているか、または使用が想定されているサイト、ライブラリ、フォルダー、電子メールのデータプライバシーについては、自動保持または削除ルールを指定して、組織の標準に対応します。</span><span class="sxs-lookup"><span data-stu-id="796a7-150">For data privacy for sites, libraries, folders, and email that contain or are expected to contain personal data, specify auto retention or deletion rules to address organizational standards.</span></span>

### <a name="records-management"></a><span data-ttu-id="796a7-151">レコード管理</span><span class="sxs-lookup"><span data-stu-id="796a7-151">Records management</span></span>

<span data-ttu-id="796a7-152">レコード保持スケジュールおよびファイル計画に基づいて、レコード管理の保持ラベルを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="796a7-152">Create and deploy retention labels for records management based on a records retention schedule and file plan.</span></span>

<span data-ttu-id="796a7-153">データのプライバシーを保護するため、法務部門によって受信されるデータ主体要求 (DSRs) は、レコードを宣言して無期限に保管し、法的なアクティビティ保持の仕様に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="796a7-153">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and stored indefinitely to adhere to regulatory activity retention specifications.</span></span>

<span data-ttu-id="796a7-154">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="796a7-154">See these resources for more information:</span></span> 

- [<span data-ttu-id="796a7-155">レコード管理</span><span class="sxs-lookup"><span data-stu-id="796a7-155">Records Management</span></span>](../compliance/records-management.md)
- [<span data-ttu-id="796a7-156">ファイル計画マネージャー</span><span class="sxs-lookup"><span data-stu-id="796a7-156">File plan manager</span></span>](../compliance/file-plan-manager.md)
- [<span data-ttu-id="796a7-157">レコード管理用のイベントベースの保持</span><span class="sxs-lookup"><span data-stu-id="796a7-157">Event-based retention for records management</span></span>](../compliance/automate-event-driven-retention.md)
- [<span data-ttu-id="796a7-158">コンテンツの廃棄</span><span class="sxs-lookup"><span data-stu-id="796a7-158">Disposition of content</span></span>](../compliance/disposition-reviews.md)
