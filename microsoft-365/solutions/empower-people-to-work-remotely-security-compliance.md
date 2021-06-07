---
title: '手順 3: ハイブリッド ワーカーのためのセキュリティとコンプライアンスの展開'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 のセキュリティ センターとコンプライアンスのサービスを使用して、ハイブリッド ワーカー向けにご使用のアプリケーション、データ、およびデバイスを保護します。
ms.openlocfilehash: fc5a83bfc6c8ec2dcb801e6063514c0a90c83de8
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788942"
---
# <a name="step-3-deploy-security-and-compliance-for-hybrid-workers"></a><span data-ttu-id="c32dc-103">手順 3: ハイブリッド ワーカーのためのセキュリティとコンプライアンスの展開</span><span class="sxs-lookup"><span data-stu-id="c32dc-103">Step 3: Deploy security and compliance for hybrid workers</span></span>

<span data-ttu-id="c32dc-104">ハイブリッド ワーカーの中にはオフィスを利用することが一切ない人や、利用頻度が低い人がいますが、セキュリティとコンプライアンスは、全体的なソリューションにおける重要な部分を占めています。</span><span class="sxs-lookup"><span data-stu-id="c32dc-104">For hybrid workers, some of whom never go into the office or who go infrequently, security and compliance are an important part of the overall solution.</span></span> <span data-ttu-id="c32dc-105">それらのリモート ワーカーのコミュニケーションが組織のイントラネットに限定されることはなく、すべてインターネットを介して行われます。</span><span class="sxs-lookup"><span data-stu-id="c32dc-105">All of their communications occur over the Internet instead of being confined to an organizational intranet.</span></span> 

<span data-ttu-id="c32dc-106">サイバーセキュリティのリスクを低減し、内部ポリシーやデータ規制へのコンプライアンスを管理しながら生産性を維持するために、お客様や作業者ができることがあります。</span><span class="sxs-lookup"><span data-stu-id="c32dc-106">There are things you and your workers can do to remain productive while decreasing cybersecurity risk and maintaining compliance with your internal policies and data regulations.</span></span>

<span data-ttu-id="c32dc-107">リモート ワークには、次のセキュリティやコンプライアンスの要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="c32dc-107">Remote work needs these elements of security and compliance:</span></span>

- <span data-ttu-id="c32dc-108">Microsoft Teams などの、ハイブリッド ワーカーが使用する生産性アプリに対する制御されたアクセス</span><span class="sxs-lookup"><span data-stu-id="c32dc-108">Controlled access to the productivity apps that hybrid workers use, such as Microsoft Teams</span></span> 
- <span data-ttu-id="c32dc-109">チャットの会話や共有ファイルなど、ハイブリッド ワーカーが作成して使用するデータに対する制御されたアクセスや保護</span><span class="sxs-lookup"><span data-stu-id="c32dc-109">Controlled access to and protection of the data that hybrid workers create and use, such as chat conversations or shared files</span></span>
- <span data-ttu-id="c32dc-110">マルウェアやその他の種類のサイバー攻撃からの Windows 10 デバイスの保護</span><span class="sxs-lookup"><span data-stu-id="c32dc-110">Protection of Windows 10 devices from malware and other types of cyberattacks</span></span>
- <span data-ttu-id="c32dc-111">秘密度や保護のレベルに応じた一貫性のあるラベル付けを使用したメール、ファイル、サイトの保護</span><span class="sxs-lookup"><span data-stu-id="c32dc-111">Protection of email, files, and site with consistent labeling for levels of sensitivity and protection</span></span>
- <span data-ttu-id="c32dc-112">情報の漏洩の防止</span><span class="sxs-lookup"><span data-stu-id="c32dc-112">Prevention of leaked information</span></span>
- <span data-ttu-id="c32dc-113">地域のデータ規制への準拠</span><span class="sxs-lookup"><span data-stu-id="c32dc-113">Adherence to regional data regulations</span></span>

<span data-ttu-id="c32dc-114">ハイブリッド ワーカーにセキュリティとコンプライアンス サービスを提供する Microsoft 365 の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c32dc-114">Here are the features of Microsoft 365 that provide security and compliance services for hybrid workers.</span></span>

![これらの Microsoft 365 サービスを使用して、セキュリティによる保護とコンプライアンスを維持します](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a><span data-ttu-id="c32dc-116">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c32dc-116">Security</span></span>

<span data-ttu-id="c32dc-117">Microsoft 365 のこれらのセキュリティ機能を使用して、アプリケーションやデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-117">Protect your applications and data with these security features of Microsoft 365.</span></span>

| <span data-ttu-id="c32dc-118">機能</span><span class="sxs-lookup"><span data-stu-id="c32dc-118">Capability or feature</span></span> | <span data-ttu-id="c32dc-119">なぜそれが必要なのか</span><span class="sxs-lookup"><span data-stu-id="c32dc-119">Why I need it</span></span> | <span data-ttu-id="c32dc-120">ライセンス</span><span class="sxs-lookup"><span data-stu-id="c32dc-120">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c32dc-121">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c32dc-121">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="c32dc-122">メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-122">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> <br><br> <span data-ttu-id="c32dc-p102">Microsoft Defender for Office 365 は、セキュリティ リスクの検出、調査、修復のためにアプリからのシグナルを収集して分析し、電子メール メッセージ、リンク (URL)、コラボレーション ツールによってもたらされる悪意のある脅威から組織を保護します。また、標準および厳格なセキュリティ体制のための自動化されたテナント構成評価と構成ツールも提供します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-p102">Microsoft Defender for Office 365 collects and analyzes signals from your apps for detection, investigation, and remediation of security risks and safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools. It also provides automated tenant configuration assessment and configuration tooling for standard and strict security postures.</span></span> | <span data-ttu-id="c32dc-125">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-125">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c32dc-126">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="c32dc-126">Malware protection</span></span> | <span data-ttu-id="c32dc-127">Microsoft Defender ウイルス対策と Device Guard は、デバイスベースのマルウェア対策を提供します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-127">‎Microsoft Defender Antivirus and Device Guard provides device-based malware protection.</span></span> <br><br> <span data-ttu-id="c32dc-p103">SharePoint Online では、既知のマルウェアのファイル アップロードを自動的にスキャンします。</span><span class="sxs-lookup"><span data-stu-id="c32dc-p103">SharePoint‎ Online automatically scans file uploads for known malware. ‎</span></span><br><br> <span data-ttu-id="c32dc-130">Exchange Online Protection (EOP) は、クラウド メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-130">Exchange Online Protection‎ (‎EOP‎) secures cloud mailboxes.</span></span> | <span data-ttu-id="c32dc-131">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-131">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c32dc-132">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c32dc-132">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="c32dc-133">サイバー攻撃の脅威やデータ侵害から組織のデバイスを保護し、高度な脅威を検出し、調査し、それらに対応します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-133">Protect your organization’s devices from cyber threats and data breaches and detect, investigate, and respond to advanced threats.</span></span> | <span data-ttu-id="c32dc-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-134">Microsoft 365 E5</span></span> |
| <span data-ttu-id="c32dc-135">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c32dc-135">Cloud App Security</span></span> | <span data-ttu-id="c32dc-136">Microsoft 365 やその他の SaaS アプリなどのクラウドベースのサービスを攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-136">Protect your cloud-based services—both Microsoft 365 and other SaaS apps—from attack.</span></span> | <span data-ttu-id="c32dc-137">Microsoft 365 E5 または個別のクラウド アプリのセキュリティ ライセンス</span><span class="sxs-lookup"><span data-stu-id="c32dc-137">Microsoft 365 E5 or individual Cloud App Security licenses</span></span> |
| <span data-ttu-id="c32dc-138">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="c32dc-138">Azure AD Identity Protection</span></span>  | <span data-ttu-id="c32dc-139">ID ベースのリスクを自動的に検出して修正します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-139">Automate detection and remediation of identity-based risks.</span></span> <br><br><span data-ttu-id="c32dc-140">リスクベースの条件付きアクセス ポリシーを作成し、危険なサインインに対して多要素認証 (MFA) を要求します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-140">Create risk-based Conditional Access policies to require multi-factor authentication (MFA) for risky sign-ins.</span></span> | <span data-ttu-id="c32dc-141">Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3</span><span class="sxs-lookup"><span data-stu-id="c32dc-141">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
||||

<span data-ttu-id="c32dc-142">最初の手順は、[Microsoft セキュア スコア ](/microsoft-365/security/defender/microsoft-secure-score)について学習し、使用することです。</span><span class="sxs-lookup"><span data-stu-id="c32dc-142">You first step should be to learn about and use [Microsoft Secure Score ](/microsoft-365/security/defender/microsoft-secure-score).</span></span>

<span data-ttu-id="c32dc-143">詳細については、「[在宅勤務をサポートするセキュリティ チームのための最も重要な 12 のタスク](../security/top-security-tasks-for-remote-work.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c32dc-143">See [Top 12 tasks for security teams to support working from home](../security/top-security-tasks-for-remote-work.md) for more information.</span></span>

<span data-ttu-id="c32dc-144">Microsoft 365 全体のセキュリティ センターの詳細については、「[Microsoft 365 セキュリティ センターに関するドキュメント](/microsoft-365/security)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c32dc-144">For information about security across Microsoft 365, see [Microsoft 365 security documentation](/microsoft-365/security).</span></span>

## <a name="compliance"></a><span data-ttu-id="c32dc-145">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c32dc-145">Compliance</span></span>

<span data-ttu-id="c32dc-146">Microsoft 365 のこれらのコンプライアンス機能を使用して、内部ポリシーや規制要件に準拠します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-146">Comply with internal policies or regulatory requirements with these compliance features of Microsoft 365.</span></span>

| <span data-ttu-id="c32dc-147">機能</span><span class="sxs-lookup"><span data-stu-id="c32dc-147">Capability or feature</span></span> | <span data-ttu-id="c32dc-148">なぜそれが必要なのか</span><span class="sxs-lookup"><span data-stu-id="c32dc-148">Why I need it</span></span> | <span data-ttu-id="c32dc-149">ライセンス</span><span class="sxs-lookup"><span data-stu-id="c32dc-149">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c32dc-150">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="c32dc-150">Sensitivity labels</span></span> | <span data-ttu-id="c32dc-151">メール、ファイル、サイトに様々な保護レベルを持ったラベルを適用することで、ユーザーの生産性や共同作業機能を妨げることなく、組織のデータを分類して保護します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-151">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="c32dc-152">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-152">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c32dc-153">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="c32dc-153">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="c32dc-154">内部や外部での個人情報を含むデータの共有などの危険な共有、偶発的な共有、不適切な共有を検出し、警告し、ブロックします。</span><span class="sxs-lookup"><span data-stu-id="c32dc-154">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="c32dc-155">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-155">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c32dc-156">アプリの条件付きアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="c32dc-156">Conditional Access App Control</span></span> | <span data-ttu-id="c32dc-157">機密データがユーザーの個人用デバイスでダウンロードされるのを防止します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-157">Prevent sensitive data from being downloaded to users' personal devices.</span></span> | <span data-ttu-id="c32dc-158">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-158">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c32dc-159">データの保持ラベルとポリシー</span><span class="sxs-lookup"><span data-stu-id="c32dc-159">Data retention labels and policies</span></span> | <span data-ttu-id="c32dc-160">データの保持期間や、顧客の個人データの保管についての要件などの情報ガバナンスの制御を展開し、組織のポリシーやデータ規制に準拠します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-160">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="c32dc-161">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-161">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c32dc-162">Office のメッセージの暗号化 (OME)</span><span class="sxs-lookup"><span data-stu-id="c32dc-162">Office message encryption (OME)</span></span> | <span data-ttu-id="c32dc-163">組織内外のユーザーとの間で、顧客の個人情報などの規制されたデータを含む暗号化されたメール メッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-163">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="c32dc-164">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c32dc-165">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="c32dc-165">Compliance Manager</span></span> | <span data-ttu-id="c32dc-166">Microsoft Service Trust Portal のワークフローベースのリスク評価ツールを使用して、Microsoft のクラウド サービスに関連する組織の規制準拠の取り組みを管理します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-166">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="c32dc-167">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-167">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c32dc-168">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="c32dc-168">Compliance Manager</span></span> | <span data-ttu-id="c32dc-169">Microsoft 365 コンプライアンス センターで、現在のコンプライアンス構成の全体のスコアと改善のための推奨事項を確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="c32dc-169">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="c32dc-170">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c32dc-170">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c32dc-171">通信コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c32dc-171">Communication Compliance</span></span>  | <span data-ttu-id="c32dc-172">組織内で不適切なメッセージを検出し、取り込んで、修復処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-172">Detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> | <span data-ttu-id="c32dc-173">コンプライアンスまたは Insider のリスク管理アドオンを備えた Microsoft 365 E5 または Microsoft 365 E3 </span><span class="sxs-lookup"><span data-stu-id="c32dc-173">Microsoft 365 E5 or Microsoft 365 E3 with the Compliance or Insider Risk Management add-ons</span></span> |
| <span data-ttu-id="c32dc-174">インサイダー リスク管理</span><span class="sxs-lookup"><span data-stu-id="c32dc-174">Insider Risk Management</span></span> |  <span data-ttu-id="c32dc-175">組織内の悪意のある不測の活動を検出および調査し、対処します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-175">Detect, investigate, and act on malicious and inadvertent risks in your organization.</span></span> <span data-ttu-id="c32dc-176">Microsoft 365 は、ワーカーが管理されていないデバイスを使用している場合でも、これらの種類のリスクを検出できます。</span><span class="sxs-lookup"><span data-stu-id="c32dc-176">Microsoft 365 can detect these kinds of risks even when a worker is using an unmanaged device.</span></span> | <span data-ttu-id="c32dc-177">コンプライアンスまたは Insider のリスク管理アドオンを備えた Microsoft 365 E5 または Microsoft 365 E3 </span><span class="sxs-lookup"><span data-stu-id="c32dc-177">Microsoft 365 E5 or Microsoft 365 E3 with the Compliance or Insider Risk Management add-ons</span></span> |
||||

<span data-ttu-id="c32dc-178">詳細については、「[Microsoft 365 コンプライアンスを開始するためのクイック タスク](../compliance/compliance-quick-tasks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c32dc-178">See [Quick tasks for getting started with Microsoft 365 compliance](../compliance/compliance-quick-tasks.md) for more information.</span></span>

## <a name="results-of-step-3"></a><span data-ttu-id="c32dc-179">手順 3 の結果</span><span class="sxs-lookup"><span data-stu-id="c32dc-179">Results of Step 3</span></span>

<span data-ttu-id="c32dc-180">ハイブリッド ワーカー のために、次を実装しました。</span><span class="sxs-lookup"><span data-stu-id="c32dc-180">For your hybrid workers, you have implemented:</span></span>

- <span data-ttu-id="c32dc-181">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c32dc-181">Security</span></span>
  - <span data-ttu-id="c32dc-182">ハイブリッド ワーカーがコミュニケーションや共同作業を行うために使用するアプリやデータへの制御されたアクセス</span><span class="sxs-lookup"><span data-stu-id="c32dc-182">Controlled access to apps and data that hybrid workers use to communicate and collaborate</span></span>
  - <span data-ttu-id="c32dc-183">クラウド サービスのデータ、メール、Windows 10 デバイスのマルウェア対策</span><span class="sxs-lookup"><span data-stu-id="c32dc-183">Malware protection for cloud service data, email, and Windows 10 devices</span></span> 
- <span data-ttu-id="c32dc-184">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c32dc-184">Compliance</span></span>
  - <span data-ttu-id="c32dc-185">秘密度や保護のレベルに応じた一貫性のあるラベル付け</span><span class="sxs-lookup"><span data-stu-id="c32dc-185">Consistent labeling for levels of sensitivity and protection</span></span>
  - <span data-ttu-id="c32dc-186">情報漏洩を防止するためのポリシー</span><span class="sxs-lookup"><span data-stu-id="c32dc-186">Policies to prevention information leakage</span></span>
  - <span data-ttu-id="c32dc-187">地域のデータ規制への準拠</span><span class="sxs-lookup"><span data-stu-id="c32dc-187">Adherence to regional data regulations</span></span>

## <a name="next-step"></a><span data-ttu-id="c32dc-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="c32dc-188">Next step</span></span>

<span data-ttu-id="c32dc-189">[![手順 4: デバイス、PC、その他のエンドポイントを管理する](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="c32dc-189">[![Step 4: Manage your devices, PCs, and other endpoints](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)</span></span>

<span data-ttu-id="c32dc-190">[手順 4](empower-people-to-work-remotely-manage-endpoints.md) に進み、デバイス、PC、その他のエンドポイントを管理します。</span><span class="sxs-lookup"><span data-stu-id="c32dc-190">Continue with [Step 4](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
