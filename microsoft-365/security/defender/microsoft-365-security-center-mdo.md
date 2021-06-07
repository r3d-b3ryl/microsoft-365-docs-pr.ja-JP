---
title: Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365
description: Office 365 セキュリティ/コンプライアンス センターから Microsoft 365 セキュリティ センターへの変更について説明します。
keywords: Microsoft 365セキュリティ、 Microsoft 365 セキュリティ センター、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、単一ウィンドウのガラス、新しいセキュリティ ポータル、新しい Defender セキュリティ ポータルの開始
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: ec5d22caa52ffaa061637cb8c510a0efaf566b6a
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782899"
---
# <a name="microsoft-defender-for-office-365-in-the-microsoft-365-security-center"></a><span data-ttu-id="c83ef-104">Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c83ef-104">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c83ef-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c83ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="c83ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c83ef-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="c83ef-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c83ef-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c83ef-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c83ef-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a><span data-ttu-id="c83ef-109">クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="c83ef-109">Quick reference</span></span>

<span data-ttu-id="c83ef-110">次の図と表に、コンプライアンス センターとセキュリティ センター Office 365セキュリティ センター&ナビゲーションMicrosoft 365示します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-110">The image and the table below lists the changes in navigation between the Office 365 Security & Compliance Center and the Microsoft 365 security center.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c83ef-111">![移動先のイメージ](../../media/mdo-m3d-security-center.png)</span><span class="sxs-lookup"><span data-stu-id="c83ef-111">![Image of what moved to where](../../media/mdo-m3d-security-center.png)</span></span>

<br>

****

|<span data-ttu-id="c83ef-112">Office 365 セキュリティ/コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c83ef-112">Office 365 Security & Compliance</span></span>|<span data-ttu-id="c83ef-113">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="c83ef-113">Microsoft 365 security center</span></span>|<span data-ttu-id="c83ef-114">Microsoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="c83ef-114">Microsoft 365 compliance center</span></span>|<span data-ttu-id="c83ef-115">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="c83ef-115">Exchange admin center</span></span>|
|---|---|---|---|
|<span data-ttu-id="c83ef-116">アラート</span><span class="sxs-lookup"><span data-stu-id="c83ef-116">Alerts</span></span>|<span data-ttu-id="c83ef-117">メールと共同作業</span><span class="sxs-lookup"><span data-stu-id="c83ef-117">Email & collaboration</span></span>|||
|<span data-ttu-id="c83ef-118">分類</span><span class="sxs-lookup"><span data-stu-id="c83ef-118">Classification</span></span>||<span data-ttu-id="c83ef-119">コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="c83ef-119">See [Microsoft 365 compliance center](https://compliance.microsoft.com/homepage)</span></span>||
|<span data-ttu-id="c83ef-120">データ損失防止</span><span class="sxs-lookup"><span data-stu-id="c83ef-120">Data loss prevention</span></span>||<span data-ttu-id="c83ef-121">コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="c83ef-121">See [Microsoft 365 compliance center](https://compliance.microsoft.com/homepage)</span></span>||
|<span data-ttu-id="c83ef-122">レコード管理</span><span class="sxs-lookup"><span data-stu-id="c83ef-122">Records management</span></span>||<span data-ttu-id="c83ef-123">コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="c83ef-123">See [Microsoft 365 compliance center](https://compliance.microsoft.com/homepage)</span></span> ||
|<span data-ttu-id="c83ef-124">情報ガバナンス</span><span class="sxs-lookup"><span data-stu-id="c83ef-124">Information governance</span></span>||<span data-ttu-id="c83ef-125">コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="c83ef-125">See [Microsoft 365 compliance center](https://compliance.microsoft.com/homepage)</span></span>||
|<span data-ttu-id="c83ef-126">脅威の管理</span><span class="sxs-lookup"><span data-stu-id="c83ef-126">Threat management</span></span>|<span data-ttu-id="c83ef-127">メールと共同作業</span><span class="sxs-lookup"><span data-stu-id="c83ef-127">Email & collaboration</span></span>|||
|<span data-ttu-id="c83ef-128">メール フロー</span><span class="sxs-lookup"><span data-stu-id="c83ef-128">Mail flow</span></span>|||<span data-ttu-id="c83ef-129">「[管理Exchange」を参照してください。](https://admin.exchange.microsoft.com/#/)</span><span class="sxs-lookup"><span data-stu-id="c83ef-129">See [Exchange admin center](https://admin.exchange.microsoft.com/#/)</span></span>|
|<span data-ttu-id="c83ef-130">データのプライバシー</span><span class="sxs-lookup"><span data-stu-id="c83ef-130">Data privacy</span></span>||<span data-ttu-id="c83ef-131">コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="c83ef-131">See [Microsoft 365 compliance center](https://compliance.microsoft.com/homepage)</span></span>||
|<span data-ttu-id="c83ef-132">検索</span><span class="sxs-lookup"><span data-stu-id="c83ef-132">Search</span></span>|<span data-ttu-id="c83ef-133">検索</span><span class="sxs-lookup"><span data-stu-id="c83ef-133">Search</span></span>|||
|<span data-ttu-id="c83ef-134">レポート</span><span class="sxs-lookup"><span data-stu-id="c83ef-134">Reports</span></span>|<span data-ttu-id="c83ef-135">レポート</span><span class="sxs-lookup"><span data-stu-id="c83ef-135">Report</span></span>|||
|<span data-ttu-id="c83ef-136">サービス アシュアランス</span><span class="sxs-lookup"><span data-stu-id="c83ef-136">Service assurance</span></span>|<span data-ttu-id="c83ef-137">設定</span><span class="sxs-lookup"><span data-stu-id="c83ef-137">Settings</span></span>|||
|

<span data-ttu-id="c83ef-138"><https://security.microsoft.com> で強化された[Microsoft 365 セキュリティ センター](./overview-security-center.md) は、Microsoft Defender セキュリティ センターや Office 365 セキュリティ/コンプライアンス センターなどの既存の Microsoft セキュリティ ポータルのセキュリティ機能を組み合わせた製品です。</span><span class="sxs-lookup"><span data-stu-id="c83ef-138">The improved [Microsoft 365 security center](./overview-security-center.md) at <https://security.microsoft.com> combines security capabilities from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="c83ef-139">この強化されたセンターは、セキュリティ チームが脅威から組織を効果的かつ効率的に保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-139">This improved center helps security teams protect their organization from threats more effectively and efficiently.</span></span>

<span data-ttu-id="c83ef-140">この記事では、Office 365 セキュリティ/コンプライアンス ポータル (protection.office.com) を使い慣れたユーザーに、Microsoft 365 セキュリティ センターで行った変更と改善点について説明します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-140">If you are familiar with the Office 365 Security and Compliance portal (protection.office.com), this article describes some of the changes and improvements in the Microsoft 365 security center.</span></span>

<span data-ttu-id="c83ef-141">利点の詳細説明: [Microsoft 365 セキュリティ センターの概要](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c83ef-141">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

<span data-ttu-id="c83ef-142">コンプライアンス関連のアイテムをお探しの場合は、「[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/homepage)」へお越しください。</span><span class="sxs-lookup"><span data-stu-id="c83ef-142">If you are looking for compliance-related items, visit the [Microsoft 365 compliance center](https://compliance.microsoft.com/homepage).</span></span>

## <a name="whats-changed"></a><span data-ttu-id="c83ef-143">変更内容</span><span class="sxs-lookup"><span data-stu-id="c83ef-143">What's changed</span></span>

<span data-ttu-id="c83ef-144">この表は、 **セキュリティ/コンプライアンス センター** と **Microsoft 365 セキュリティ** ポータルの間で変更が発生したメールと共同作業の領域のクイック リファレンスです。</span><span class="sxs-lookup"><span data-stu-id="c83ef-144">This table is a quick reference of Email & Collaboration areas where change has occurred between the **Security & Compliance center** and the **Microsoft 365 Security** portal.</span></span> <span data-ttu-id="c83ef-145">これらの領域の詳細については、リンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="c83ef-145">Click the links to read more about these areas.</span></span>

<br>

****

|<span data-ttu-id="c83ef-146">分野</span><span class="sxs-lookup"><span data-stu-id="c83ef-146">Area</span></span>|<span data-ttu-id="c83ef-147">変更の説明</span><span class="sxs-lookup"><span data-stu-id="c83ef-147">Description of change</span></span>|
|---|---|
|<span data-ttu-id="c83ef-148">[[メール エンティティ] ページ](../office-365-security/mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="c83ef-148">[Email entity page](../office-365-security/mdo-email-entity-page.md)</span></span>|<span data-ttu-id="c83ef-149">このページは、今まで色々なページやビューに分散していたメール情報を **統合** します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-149">This page **unifies** email information that had been scattered across different pages or views in the past.</span></span> <span data-ttu-id="c83ef-150">脅威と傾向に関するメールの調査結果は、*1 か所に集中しています*。</span><span class="sxs-lookup"><span data-stu-id="c83ef-150">Investigating email for threats and trends is *centralized*.</span></span> <span data-ttu-id="c83ef-151">ヘッダー情報とメールプレビューは、他の便利なメール関連情報と共に同じメール ページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-151">Header information and email preview are accessible through the same email page, along with other useful email-related information.</span></span> <span data-ttu-id="c83ef-152">同様に、悪意のある添付ファイルまたは URL に対するデトネーションの状態は、同じページのタブにあります。</span><span class="sxs-lookup"><span data-stu-id="c83ef-152">Likewise, the detonation status for malicious file attachments or URLs can be found on a tab of the same page.</span></span> <span data-ttu-id="c83ef-153">[メール エンティティ] ページは、管理者やセキュリティ運用チームがメールの脅威とその状態をすばやく把握し、処理を迅速に決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-153">The Email entity page empowers admins and security operations teams to understand an email threat and its status, fast, and then act quickly determine handling.</span></span>|
|[<span data-ttu-id="c83ef-154">調査</span><span class="sxs-lookup"><span data-stu-id="c83ef-154">Investigation</span></span>](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-security-center)|<span data-ttu-id="c83ef-155">[Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) および[Defender for Endpoint](../defender-endpoint/automated-investigations.md)の AIR 機能を 1 つにまとめます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-155">Brings together AIR capabilities in [Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) and [Defender for Endpoint](../defender-endpoint/automated-investigations.md).</span></span> <span data-ttu-id="c83ef-156">これらの更新プログラムと改善により、セキュリティ運用チームは、メール、共同作業のコンテンツ、ユーザー アカウント、デバイスに対する自動調査と修復処理に関する詳細を 1 か所で確認できます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-156">With these updates and improvements, your security operations team will be able to view details about automated investigations and remediation actions across your email, collaboration content, user accounts, and devices, all in one place.</span></span>|
|[<span data-ttu-id="c83ef-157">通知ビュー</span><span class="sxs-lookup"><span data-stu-id="c83ef-157">Alert view</span></span>](../../compliance/alert-policies.md)|<span data-ttu-id="c83ef-158">Office Security and Compliance センターの **[通知の表示]** ウィンドウに、Microsoft 365 セキュリティ センターへのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="c83ef-158">The **View alerts** flyout pane in the Office Security and Compliance center now includes links to the Microsoft 365 security center.</span></span> <span data-ttu-id="c83ef-159">**[通知のページを開く]** のリンクをクリックすると、 Microsoft 365 セキュリティ センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-159">Click on the **Open Alert Page** link and the Microsoft 365 security center opens.</span></span> <span data-ttu-id="c83ef-160">通知キュー内の Office 365 をクリックすると、**[通知の表示]** ページにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-160">You can access the **View alerts** page by clicking on any Office 365 alert in the Alerts queue.</span></span>|
|[<span data-ttu-id="c83ef-161">攻撃シミュレーション トレーニング</span><span class="sxs-lookup"><span data-stu-id="c83ef-161">Attack Simulation training</span></span>](../office-365-security/attack-simulation-training-insights.md)|<span data-ttu-id="c83ef-162">攻撃シミュレーション トレーニングを使用して、組織内で現実的な攻撃シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-162">Use Attack Simulation training to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="c83ef-163">これらのシミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、従業員をトレーニングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-163">These simulated attacks can help train your workforce before a real attack impacts your organization.</span></span> <span data-ttu-id="c83ef-164">攻撃シミュレーション トレーニングには、より多くのオプション、強化されたレポート、および強化されたトレーニング フローおよび配信と管理がより容易になったトレーニングシナリオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c83ef-164">Attack simulation training includes, more options, enhanced reports, and improved training flows help make your attack simulation and training scenarios easier to deliver and manage.</span></span>|
|

<span data-ttu-id="c83ef-165">次の領域に変更はありません。</span><span class="sxs-lookup"><span data-stu-id="c83ef-165">No changes to these areas:</span></span>

- [<span data-ttu-id="c83ef-166">Explorer</span><span class="sxs-lookup"><span data-stu-id="c83ef-166">Explorer</span></span>](../office-365-security/threat-explorer.md)
- [<span data-ttu-id="c83ef-167">ポリシーとルール</span><span class="sxs-lookup"><span data-stu-id="c83ef-167">Policies & Rules</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="c83ef-168">キャンペーン</span><span class="sxs-lookup"><span data-stu-id="c83ef-168">Campaign</span></span>](../office-365-security/campaigns.md)
- [<span data-ttu-id="c83ef-169">Submissions</span><span class="sxs-lookup"><span data-stu-id="c83ef-169">Submissions</span></span>](../office-365-security/admin-submission.md)
- [<span data-ttu-id="c83ef-170">確認</span><span class="sxs-lookup"><span data-stu-id="c83ef-170">Review</span></span>](./m365d-action-center.md)
- [<span data-ttu-id="c83ef-171">脅威トラッカー</span><span class="sxs-lookup"><span data-stu-id="c83ef-171">Threat Tracker</span></span>](../office-365-security/threat-trackers.md)

<span data-ttu-id="c83ef-172">また、この記事の下にある **関連情報** セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-172">Also, check the **Related Information** section at the bottom of this article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c83ef-173">[Microsoft 365 セキュリティ ポータル ( <https://security.microsoft.com> ) は、 および でセキュリティ機能 <https://securitycenter.windows.com> を組み合わせたものになります <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="c83ef-173">The Microsoft 365 Security portal (<https://security.microsoft.com>) combines security features in <https://securitycenter.windows.com>, and <https://protection.office.com>.</span></span> <span data-ttu-id="c83ef-174">ただし、表示される内容はサブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c83ef-174">However, what you see will depend on your subscription.</span></span> <span data-ttu-id="c83ef-175">たとえば、Microsoft Defender for Office 365 Plan 1 または 2 をスタンドアロン サブスクリプションとしてお持ちの場合、Security for Endpoints 関連の機能は表示されません。また Defender for Office Plan 1 のお客様の場合、Threat Analytics などのアイテムは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c83ef-175">If you only have Microsoft Defender for Office 365 Plan 1 or 2, as standalone subscriptions, for example, you won't see capabilities around Security for Endpoints and Defender for Office Plan 1 customers won't see items such as Threat Analytics.</span></span>

> [!TIP]
> <span data-ttu-id="c83ef-176">EOP は Exchange Online Protectionの Defender のコア要素であるMicrosoft 365セキュリティ センターに含まれるすべてのOffice 365。</span><span class="sxs-lookup"><span data-stu-id="c83ef-176">All Exchange Online Protection (EOP) functions will be included in the Microsoft 365 security center, as EOP is a core element of Defender for Office 365.</span></span>

## <a name="microsoft-365-security-center-home-page"></a><span data-ttu-id="c83ef-177">Microsoft 365 セキュリティ センターのホーム ページ</span><span class="sxs-lookup"><span data-stu-id="c83ef-177">Microsoft 365 security center Home page</span></span>

<span data-ttu-id="c83ef-178">ポータルのホーム ページには次が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-178">The Home page of the portal surfaces:</span></span>

- <span data-ttu-id="c83ef-179">セキュリティ スコアの評価</span><span class="sxs-lookup"><span data-stu-id="c83ef-179">Secure Score ratings</span></span>
- <span data-ttu-id="c83ef-180">リスクに晒されているユーザーとデバイスの数</span><span class="sxs-lookup"><span data-stu-id="c83ef-180">the number of users and devices at risk</span></span>
- <span data-ttu-id="c83ef-181">アクティブなインシデント キュー</span><span class="sxs-lookup"><span data-stu-id="c83ef-181">active incident queue</span></span>
- <span data-ttu-id="c83ef-182">特権 OAuth アプリの一覧</span><span class="sxs-lookup"><span data-stu-id="c83ef-182">lists of privileged OAuth apps</span></span>
- <span data-ttu-id="c83ef-183">デバイス正常性データ</span><span class="sxs-lookup"><span data-stu-id="c83ef-183">device health data</span></span>
- <span data-ttu-id="c83ef-184">Microsoft のセキュリティ インテリジェンスの Twitter フィードからのツイート</span><span class="sxs-lookup"><span data-stu-id="c83ef-184">tweets from Microsoft’s security intelligence twitter feed</span></span>
- <span data-ttu-id="c83ef-185">その他のサマリー情報</span><span class="sxs-lookup"><span data-stu-id="c83ef-185">and more summary information</span></span>

<span data-ttu-id="c83ef-186">**ガイド 付 ツアー** を使用して、エンドポイントまたはメールと共同作業のページのクイック ツアーを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-186">Using the **Guided tour** you can take a quick tour of Endpoint or Email & collaboration pages.</span></span> <span data-ttu-id="c83ef-187">ここに表示される内容は、ライセンスが、Defender for Office 365、 Defender for Endpoint のどちらか、または両方をお持ちの場合によって異なる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c83ef-187">Note that what you see here will depend on if you have license for Defender for Office 365 and/or Defender for Endpoint.</span></span>

<span data-ttu-id="c83ef-188">**Office 365 セキュリティ/コンプライアンス センター** のリンクも異なります。</span><span class="sxs-lookup"><span data-stu-id="c83ef-188">Also included is a link to the **Office 365 Security and Compliance center** for comparison.</span></span> <span data-ttu-id="c83ef-189">最後のリンクは、最近の更新プログラムを表示する **[新機能]** ページへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="c83ef-189">The last link is to the **What's New** page that describes recent updates.</span></span>

## <a name="improved-capabilities"></a><span data-ttu-id="c83ef-190">強化された機能</span><span class="sxs-lookup"><span data-stu-id="c83ef-190">Improved capabilities</span></span>

<span data-ttu-id="c83ef-191">左側のナビゲーションまたはクイック起動バーは見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-191">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="c83ef-192">ただし、このセキュリティ センターには、いくつかの新しい要素や更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="c83ef-192">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="c83ef-193">インシデントと警告</span><span class="sxs-lookup"><span data-stu-id="c83ef-193">Incidents and alerts</span></span>

<span data-ttu-id="c83ef-194">メール、デバイス、ID 全体でインシデントと通知の管理を 1 か所で行います。</span><span class="sxs-lookup"><span data-stu-id="c83ef-194">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="c83ef-195">現在、警告が [調査] ノードの下に表示されており、攻撃のより広範なビューを提供しています。</span><span class="sxs-lookup"><span data-stu-id="c83ef-195">Alerts are now available under the Investigation node, and help provide a broader view of an attack.</span></span> <span data-ttu-id="c83ef-196">警告ページには、攻撃シグナルを組み合わせて詳細なストーリーを構築することで、アラートの完全なコンテキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-196">The alert page provides full context to the alert, by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="c83ef-197">以前は、アラートはさまざまなワークロードに特有のものでした。</span><span class="sxs-lookup"><span data-stu-id="c83ef-197">Previously, alerts were specific to different workloads.</span></span> <span data-ttu-id="c83ef-198">新しく統合されたエクスペリエンスにより、さまざまなワークロード全体で一貫した警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-198">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="c83ef-199">トリアージ、調査、効果的なアクションをすばやく実行できます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-199">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="c83ef-200">調査の詳細</span><span class="sxs-lookup"><span data-stu-id="c83ef-200">Learn more about Investigations</span></span>](incidents-overview.md)
- [<span data-ttu-id="c83ef-201">通知の管理に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="c83ef-201">Learn more about managing alerts</span></span>](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![通知とアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="c83ef-203">検索</span><span class="sxs-lookup"><span data-stu-id="c83ef-203">Hunting</span></span>

<span data-ttu-id="c83ef-204">エンドポイント、Office 365 メールボックスなどに対する脅威、マルウェア、悪意のあるアクティビティを積極的に検索するために、[高度な検索クエリ](advanced-hunting-overview.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-204">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="c83ef-205">これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方を示す脅威インジケーターとエンティティを見つけて確認できます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-205">These powerful queries can be used to  locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="c83ef-206">[カスタム検出ルール](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) は、高度な検索クエリから作成できます。侵害アクティビティや間違った構成のデバイスを示すイベントを積極的に監視することができます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-206">[Custom detection rules](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules)  can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>

### <a name="action-center"></a><span data-ttu-id="c83ef-207">アクション センター</span><span class="sxs-lookup"><span data-stu-id="c83ef-207">Action center</span></span>

<span data-ttu-id="c83ef-208">アクション センターには、自動調査と自動応答機能によって作成された調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-208">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="c83ef-209">この Microsoft 365 Defender の自動自己修復機能は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-209">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="c83ef-210">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="c83ef-210">Learn more about Action center</span></span>](m365d-action-center.md)

#### <a name="threat-analytics"></a><span data-ttu-id="c83ef-211">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="c83ef-211">Threat Analytics</span></span>

<span data-ttu-id="c83ef-212">専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-212">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="c83ef-213">脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-213">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="c83ef-214">脅威の分析には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-214">Threat Analytics includes:</span></span>

- <span data-ttu-id="c83ef-215">Microsoft Defender for Office 365 からのメール関連の検出と移行。</span><span class="sxs-lookup"><span data-stu-id="c83ef-215">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c83ef-216">これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-216">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="c83ef-217">脅威に関連するインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-217">Incidents view related to the threats.</span></span>
- <span data-ttu-id="c83ef-218">レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="c83ef-218">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>
<span data-ttu-id="c83ef-219">脅威の分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーからか、組織の上位の脅威を表示する専用のダッシュボード カードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-219">You can access Threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="c83ef-220">[[脅威の分析を使用して、新たな脅威を追跡し対応する]](./threat-analytics.md)の詳細説明</span><span class="sxs-lookup"><span data-stu-id="c83ef-220">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="email--collaboration"></a><span data-ttu-id="c83ef-221">メールと共同作業</span><span class="sxs-lookup"><span data-stu-id="c83ef-221">Email & collaboration</span></span>

<span data-ttu-id="c83ef-222">ユーザーのメールへの脅威を追跡および調査し、キャンペーンなどを追跡します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-222">Track and investigate threats to your users' email, track campaigns, and more.</span></span> <span data-ttu-id="c83ef-223">Office 365 セキュリティ/コンプライアンス センターをご利用の場合は、使い慣れたものになっています。</span><span class="sxs-lookup"><span data-stu-id="c83ef-223">If you've used the Office 365 Security and Compliance center, this will be familiar.</span></span>

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Microsoft 365 セキュリティ センターの左側にある [メールと共同作業] (または MSDO) のクイック起動メニュー。":::

### <a name="access-and-reports"></a><span data-ttu-id="c83ef-225">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="c83ef-225">Access and Reports</span></span>

<span data-ttu-id="c83ef-226">レポートの表示、設定の変更、およびユーザーの役割変更を行います。</span><span class="sxs-lookup"><span data-stu-id="c83ef-226">View reports, change your settings, and modify user roles.</span></span>

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="セキュリティ センターの左側にある、Microsoft 365 セキュリティ センターのアクセス許可とレポートのクイック起動メニュー。":::

> [!NOTE]
> <span data-ttu-id="c83ef-228">Office 365 ユーザーの Defender では、Microsoft 365 セキュリティセンターを通じて DomainKeys Identified Mail (DKIM) キーを管理および回転したり、ポリシー & ルールの脅威ポリシー <https://security.microsoft.com/threatpolicy>  \>  \> **DKIM** に移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-228">For Defender for Office 365 users, you can now *manage and rotate* DomainKeys Identified Mail (DKIM) keys through the Microsoft 365 security center: <https://security.microsoft.com/threatpolicy>, or navigate to **Policy & rules** \> **Threat policies** \> **DKIM**.</span></span>

## <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="c83ef-229">Microsoft Defender for Office 365 の高度な検出の例</span><span class="sxs-lookup"><span data-stu-id="c83ef-229">Advanced Hunting example for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c83ef-230">高度な検出を使用してメールの脅威の検索を開始しますか?</span><span class="sxs-lookup"><span data-stu-id="c83ef-230">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="c83ef-231">実行する操作:</span><span class="sxs-lookup"><span data-stu-id="c83ef-231">Try this:</span></span>

<span data-ttu-id="c83ef-232">[Microsoft Defender for Office 365の記事](/microsoft-365/security/office-365-security/defender-for-office-365)の「[使用を開始する](/microsoft-365/security/office-365-security/defender-for-office-365.md#getting-started)」セクションには、次のような論理的な早期構成用の単位があります。</span><span class="sxs-lookup"><span data-stu-id="c83ef-232">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365.md#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="c83ef-233">名前に 'Anti' を含むすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-233">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="c83ef-234">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="c83ef-234">Anti-malware</span></span>
   - <span data-ttu-id="c83ef-235">フィッシング対策</span><span class="sxs-lookup"><span data-stu-id="c83ef-235">Anti-phishing</span></span>
   - <span data-ttu-id="c83ef-236">スパム対策</span><span class="sxs-lookup"><span data-stu-id="c83ef-236">Anti-spam</span></span>
2. <span data-ttu-id="c83ef-237">名前に 'セーフ' を含むすべてを設定します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-237">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="c83ef-238">安全なリンク</span><span class="sxs-lookup"><span data-stu-id="c83ef-238">Safe Links</span></span>
   - <span data-ttu-id="c83ef-239">安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="c83ef-239">Safe Attachments</span></span>
3. <span data-ttu-id="c83ef-240">ワークロードを保護する (例:</span><span class="sxs-lookup"><span data-stu-id="c83ef-240">Defend the workloads (ex.</span></span> <span data-ttu-id="c83ef-241">SharePointオンライン、OneDrive、およびTeams)。</span><span class="sxs-lookup"><span data-stu-id="c83ef-241">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="c83ef-242">0 時間自動削除で保護します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-242">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="c83ef-243">[リンク](../office-365-security/protect-against-threats.md)をクリックすると、一気にジャンプして、第 1 日目から使用できる構成を入手できます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-243">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="c83ef-244">**開始** の最後の手順は、**ゼロアワー自動消去**(ZAP) によるユーザー保護です。</span><span class="sxs-lookup"><span data-stu-id="c83ef-244">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="c83ef-245">ZAP で不審なメールや悪意のあるメール、配信後のメールの自動消去が成功したどうかを知るのはとても重要です。</span><span class="sxs-lookup"><span data-stu-id="c83ef-245">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="c83ef-246">問題を探し出す場合に、Kusto クエリ言語にすばやく移動できることは、2 つのセキュリティ センターを集約する利点です。</span><span class="sxs-lookup"><span data-stu-id="c83ef-246">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="c83ef-247">セキュリティ チームは、次の手順を実行して、ZAP ミスを監視 [](https://security.microsoft.com/advanced-hunting) \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="c83ef-247">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="c83ef-248">[高度な検出] ページで [クエリ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c83ef-248">On the Advanced Hunting page, click Query.</span></span>
1. <span data-ttu-id="c83ef-249">次のクエリを[クエリ] ウィンドウにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c83ef-249">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="c83ef-250">[クエリの実行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-250">Select Run query.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="クエリ パネルの上部で [クエリ] を選択し、過去 7 日間の ZAP アクションをキャプチャするために Kusto クエリを実行した [高度な検索] ページ ([ハンティング] の下)。":::

<span data-ttu-id="c83ef-252">このクエリのデータは、クエリ自体の下の結果パネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-252">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="c83ef-253">結果には、カスタマイズ可能な結果セットに 'DeviceName', 'AccountDisplayName'、および 'ZapTime' が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c83ef-253">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="c83ef-254">ユーザーの記録用に、結果をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c83ef-254">Results can also be exported for your records.</span></span> <span data-ttu-id="c83ef-255">クエリがもう一度必要な場合は、**[保存する]** > **[以下の名前で保存する]** の順に選択し、クエリ、共有クエリ、またはコミュニティ クエリの一覧にそのクエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c83ef-255">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="c83ef-256">関連情報</span><span class="sxs-lookup"><span data-stu-id="c83ef-256">Related information</span></span>

- [<span data-ttu-id="c83ef-257">Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c83ef-257">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="c83ef-258">アクション センター</span><span class="sxs-lookup"><span data-stu-id="c83ef-258">The Action center</span></span>](./m365d-action-center.md)
- [<span data-ttu-id="c83ef-259">メールと共同作業の通知</span><span class="sxs-lookup"><span data-stu-id="c83ef-259">Email & collaboration alerts</span></span>](../../compliance/alert-policies.md#default-alert-policies)
- [<span data-ttu-id="c83ef-260">デバイス、メール、アプリ、ID 全体の脅威を探す</span><span class="sxs-lookup"><span data-stu-id="c83ef-260">Hunt for threats across devices, emails, apps, and identities</span></span>](./advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c83ef-261">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="c83ef-261">Custom detection rules</span></span>](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- <span data-ttu-id="c83ef-262">[フィッシング攻撃のシミュレーションを作成](../office-365-security/attack-simulation-training.md)して[従業員をトレーニングするためのペイロードを作成する](../office-365-security/attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="c83ef-262">[Create a phishing attack simulation](../office-365-security/attack-simulation-training.md) and [create a payload for training your people](../office-365-security/attack-simulation-training-payloads.md)</span></span>
