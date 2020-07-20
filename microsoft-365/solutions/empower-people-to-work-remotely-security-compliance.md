---
title: '手順 3: リモート ワーカーのためのセキュリティとコンプライアンスの展開'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Microsoft 365 のセキュリティとコンプライアンスのサービスを使用して、リモート ワーカー向けにお客様のアプリケーション、データ、およびデバイスを保護します。
ms.openlocfilehash: 5ba60a04cf6717f8f9261ed72336445c8d7876bc
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127079"
---
# <a name="step-3-deploy-security-and-compliance-for-remote-workers"></a><span data-ttu-id="fea8d-103">手順 3: リモート ワーカーのためのセキュリティとコンプライアンスの展開</span><span class="sxs-lookup"><span data-stu-id="fea8d-103">Step 3: Deploy security and compliance for remote workers</span></span>

<span data-ttu-id="fea8d-104">リモート ワーカーの中にはオフィスを利用することが一切ない人や、利用頻度が低い人がいますが、セキュリティとコンプライアンスは、全体的なソリューションにおける重要な部分を占めています。</span><span class="sxs-lookup"><span data-stu-id="fea8d-104">For remote workers, some of whom never go into the office or who go infrequently, security and compliance are an important part of the overall solution.</span></span> <span data-ttu-id="fea8d-105">それらのリモート ワーカーのコミュニケーションが組織のイントラネットに限定されることはなく、すべてインターネットを介して行われます。</span><span class="sxs-lookup"><span data-stu-id="fea8d-105">All of their communications occur over the Internet instead of being confined to an organizational intranet.</span></span> 

<span data-ttu-id="fea8d-106">サイバーセキュリティのリスクを低減し、内部ポリシーやデータ規制へのコンプライアンスを管理しながら生産性を維持するために、お客様や作業者ができることがあります。</span><span class="sxs-lookup"><span data-stu-id="fea8d-106">There are things you and your workers can do to remain productive while decreasing cybersecurity risk and maintaining compliance with your internal policies and data regulations.</span></span>

<span data-ttu-id="fea8d-107">リモート ワークには、次のセキュリティやコンプライアンスの要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="fea8d-107">Remote work needs these elements of security and compliance:</span></span>

- <span data-ttu-id="fea8d-108">Microsoft Teams などの、リモート ワーカーが使用する生産性アプリに対するアクセスの制御</span><span class="sxs-lookup"><span data-stu-id="fea8d-108">Controlled access to the productivity apps that remote workers use, such as Microsoft Teams</span></span> 
- <span data-ttu-id="fea8d-109">チャットの会話や共有ファイルなど、リモート ワーカーが作成して使用するデータに対するアクセスや保護の制御</span><span class="sxs-lookup"><span data-stu-id="fea8d-109">Controlled access to and protection of the data that remote workers create and use, such as chat conversations or shared files</span></span>
- <span data-ttu-id="fea8d-110">マルウェアやその他の種類のサイバー攻撃からの Windows 10 デバイスの保護</span><span class="sxs-lookup"><span data-stu-id="fea8d-110">Protection of Windows 10 devices from malware and other types of cyberattacks</span></span>
- <span data-ttu-id="fea8d-111">秘密度や保護のレベルに応じた一貫性のあるラベル付けを使用したメール、ファイル、サイトの保護</span><span class="sxs-lookup"><span data-stu-id="fea8d-111">Protection of email, files, and site with consistent labeling for levels of sensitivity and protection</span></span>
- <span data-ttu-id="fea8d-112">情報の漏洩の防止</span><span class="sxs-lookup"><span data-stu-id="fea8d-112">Prevention of leaked information</span></span>
- <span data-ttu-id="fea8d-113">地域のデータ規制への準拠</span><span class="sxs-lookup"><span data-stu-id="fea8d-113">Adherence to regional data regulations</span></span>

![これらの Microsoft 365 サービスを使用して、セキュリティによる保護とコンプライアンスを維持します](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a><span data-ttu-id="fea8d-115">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="fea8d-115">Security</span></span>

<span data-ttu-id="fea8d-116">Microsoft 365 のこれらのセキュリティ機能を使用して、アプリケーションやデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-116">Protect your applications and data with these security features of Microsoft 365.</span></span>

| <span data-ttu-id="fea8d-117">機能</span><span class="sxs-lookup"><span data-stu-id="fea8d-117">Capability or feature</span></span> | <span data-ttu-id="fea8d-118">説明</span><span class="sxs-lookup"><span data-stu-id="fea8d-118">Description</span></span> | <span data-ttu-id="fea8d-119">ライセンス</span><span class="sxs-lookup"><span data-stu-id="fea8d-119">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="fea8d-120">Office 365 Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="fea8d-120">Office 365 Advanced Threat Protection (ATP)</span></span> | <span data-ttu-id="fea8d-121">メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-121">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> <br><br> <span data-ttu-id="fea8d-122">Office ATP はアプリからのシグナルを収集して分析し、セキュリティ リスクの検出、調査、修復を行い、メール メッセージ、リンク (URL)、共同作業のツールによってもたらされる悪意のある脅威から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-122">Office ATP collects and analyzes signals from your apps for detection, investigation, and remediation of security risks and safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> | <span data-ttu-id="fea8d-123">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-123">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="fea8d-124">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="fea8d-124">Malware protection</span></span> | <span data-ttu-id="fea8d-125">Windows Defender ウイルス対策と Device Guard は、デバイスベースのマルウェア対策を提供します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-125">‎Windows Defender Antivirus and Device Guard provides device-based malware protection.</span></span> <br><br> <span data-ttu-id="fea8d-126">SharePoint Online では、既知のマルウェアのファイル アップロードを自動的にスキャンします。</span><span class="sxs-lookup"><span data-stu-id="fea8d-126">SharePoint‎ Online automatically scans file uploads for known malware.</span></span> <span data-ttu-id="fea8d-127">‎</span><span class="sxs-lookup"><span data-stu-id="fea8d-127">‎</span></span><br><br> <span data-ttu-id="fea8d-128">Exchange Online Protection (EOP) は、クラウド メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-128">Exchange Online Protection‎ (‎EOP‎) secures cloud mailboxes.</span></span> | <span data-ttu-id="fea8d-129">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-129">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="fea8d-130">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="fea8d-130">Microsoft Defender ATP</span></span> | <span data-ttu-id="fea8d-131">サイバー攻撃の脅威やデータ侵害から組織のデバイスを保護し、高度な脅威を検出し、調査し、それらに対応します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-131">Protect your organization’s devices from cyberthreats and data breaches and detect, investigate, and respond to advanced threats.</span></span> | <span data-ttu-id="fea8d-132">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-132">Microsoft 365 E5</span></span> |
| <span data-ttu-id="fea8d-133">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fea8d-133">Cloud App Security</span></span> | <span data-ttu-id="fea8d-134">Microsoft 365 やその他の SaaS アプリなどのクラウドベースのサービスを攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-134">Protect your cloud-based services—both Microsoft 365 and other SaaS apps— from attack.</span></span> | <span data-ttu-id="fea8d-135">Microsoft 365 E5 または個別のクラウド アプリのセキュリティ ライセンス</span><span class="sxs-lookup"><span data-stu-id="fea8d-135">Microsoft 365 E5 or individual Cloud App Security licenses</span></span> |
| <span data-ttu-id="fea8d-136">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="fea8d-136">Azure AD Identity Protection</span></span>  | <span data-ttu-id="fea8d-137">ID ベースのリスクを自動的に検出して修正します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-137">Automate detection and remediation of identity-based risks.</span></span> <br><br><span data-ttu-id="fea8d-138">リスクベースの条件付きアクセス ポリシーを作成し、危険なサインインに対して多要素認証 (MFA) を要求します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-138">Create risk-based Conditional Access policies to require multi-factor authentication (MFA) for risky sign-ins.</span></span> | <span data-ttu-id="fea8d-139">Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3</span><span class="sxs-lookup"><span data-stu-id="fea8d-139">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
||||

<span data-ttu-id="fea8d-140">詳細については、「[Microsoft 365 コンプライアンスを開始するためのクイック タスク](../compliance/compliance-quick-tasks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea8d-140">See [Quick tasks for getting started with Microsoft 365 compliance](../compliance/compliance-quick-tasks.md) for more information.</span></span>

## <a name="compliance"></a><span data-ttu-id="fea8d-141">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="fea8d-141">Compliance</span></span>

<span data-ttu-id="fea8d-142">Microsoft 365 のこれらのコンプライアンス機能を使用して、内部ポリシーや規制要件に準拠します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-142">Comply with internal policies or regulatory requirements with these compliance features of Microsoft 365.</span></span>

| <span data-ttu-id="fea8d-143">機能</span><span class="sxs-lookup"><span data-stu-id="fea8d-143">Capability or feature</span></span> | <span data-ttu-id="fea8d-144">説明</span><span class="sxs-lookup"><span data-stu-id="fea8d-144">Description</span></span> | <span data-ttu-id="fea8d-145">ライセンス</span><span class="sxs-lookup"><span data-stu-id="fea8d-145">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="fea8d-146">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="fea8d-146">Sensitivity labels</span></span> | <span data-ttu-id="fea8d-147">メール、ファイル、サイトに様々な保護レベルを持ったラベルを適用することで、ユーザーの生産性や共同作業機能を妨げることなく、組織のデータを分類して保護します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-147">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="fea8d-148">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-148">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="fea8d-149">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="fea8d-149">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="fea8d-150">内部や外部での個人情報を含むデータの共有などの危険な共有、偶発的な共有、不適切な共有を検出し、警告し、ブロックします。</span><span class="sxs-lookup"><span data-stu-id="fea8d-150">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="fea8d-151">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-151">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="fea8d-152">アプリの条件付きアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="fea8d-152">Conditional Access App Control</span></span> | <span data-ttu-id="fea8d-153">機密データがユーザーの個人用デバイスでダウンロードされるのを防止します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-153">Prevent sensitive data from being downloaded to users' personal devices.</span></span> | <span data-ttu-id="fea8d-154">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-154">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="fea8d-155">データの保持ラベルとポリシー</span><span class="sxs-lookup"><span data-stu-id="fea8d-155">Data retention labels and policies</span></span> | <span data-ttu-id="fea8d-156">データの保持期間や、顧客の個人データの保管についての要件などの情報ガバナンスの制御を展開し、組織のポリシーやデータ規制に準拠します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-156">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="fea8d-157">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-157">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="fea8d-158">Office のメッセージの暗号化 (OME)</span><span class="sxs-lookup"><span data-stu-id="fea8d-158">Office message encryption (OME)</span></span> | <span data-ttu-id="fea8d-159">組織内外のユーザーとの間で、顧客の個人情報などの規制されたデータを含む暗号化されたメール メッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-159">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="fea8d-160">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-160">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="fea8d-161">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="fea8d-161">Compliance Manager</span></span> | <span data-ttu-id="fea8d-162">Microsoft Service Trust Portal のワークフローベースのリスク評価ツールを使用して、Microsoft のクラウド サービスに関連する組織の規制準拠の取り組みを管理します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-162">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="fea8d-163">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-163">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="fea8d-164">コンプライアンス スコア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="fea8d-164">Compliance Score (preview)</span></span> | <span data-ttu-id="fea8d-165">Microsoft 365 コンプライアンス センターで、現在のコンプライアンス構成の全体のスコアと改善のための推奨事項を確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="fea8d-165">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 Compliance Center.</span></span> | <span data-ttu-id="fea8d-166">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="fea8d-166">Microsoft 365 E3 and E5</span></span> |
||||

<span data-ttu-id="fea8d-167">詳細については、「[在宅勤務をサポートするセキュリティ チームのための最も重要な 12 のタスク](../security/top-security-tasks-for-remote-work.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea8d-167">See [Top 12 tasks for security teams to support working from home](../security/top-security-tasks-for-remote-work.md) for more information.</span></span>

## <a name="results-of-step-3"></a><span data-ttu-id="fea8d-168">手順 3 の結果</span><span class="sxs-lookup"><span data-stu-id="fea8d-168">Results of Step 3</span></span>

<span data-ttu-id="fea8d-169">リモートワーカーのために、次のものを実装しました。</span><span class="sxs-lookup"><span data-stu-id="fea8d-169">For your remote workers, you have implemented:</span></span>

- <span data-ttu-id="fea8d-170">セキュリティ:</span><span class="sxs-lookup"><span data-stu-id="fea8d-170">Security:</span></span>
  - <span data-ttu-id="fea8d-171">リモート ワーカーがコミュニケーションや共同作業を行うために使用するアプリやデータへのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="fea8d-171">Controlled access to apps and data that remote workers use to communicate and collaborate</span></span>
  - <span data-ttu-id="fea8d-172">クラウド サービスのデータ、メール、Windows 10 デバイスのマルウェア対策</span><span class="sxs-lookup"><span data-stu-id="fea8d-172">Malware protection for cloud service data, email, and Windows 10 devices</span></span> 
- <span data-ttu-id="fea8d-173">コンプライアンス:</span><span class="sxs-lookup"><span data-stu-id="fea8d-173">Compliance:</span></span>
  - <span data-ttu-id="fea8d-174">秘密度や保護のレベルに応じた一貫性のあるラベル付け</span><span class="sxs-lookup"><span data-stu-id="fea8d-174">Consistent labeling for levels of sensitivity and protection</span></span>
  - <span data-ttu-id="fea8d-175">情報漏洩を防止するためのポリシー</span><span class="sxs-lookup"><span data-stu-id="fea8d-175">Policies to prevention information leakage</span></span>
  - <span data-ttu-id="fea8d-176">地域のデータ規制への準拠</span><span class="sxs-lookup"><span data-stu-id="fea8d-176">Adherence to regional data regulations</span></span>

## <a name="next-step"></a><span data-ttu-id="fea8d-177">次の手順</span><span class="sxs-lookup"><span data-stu-id="fea8d-177">Next step</span></span>

<span data-ttu-id="fea8d-178">[手順 4](empower-people-to-work-remotely-manage-endpoints.md) に進み、デバイス、PC、その他のエンドポイントを管理します。</span><span class="sxs-lookup"><span data-stu-id="fea8d-178">Continue with [Step 4](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
