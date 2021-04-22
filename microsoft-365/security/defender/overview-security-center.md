---
title: MDO、MDE、MDI、MCAS を組み合わせた Microsoft 365 セキュリティ センターの概要
description: Microsoft Defender for Office 365 (MDO) と Microsoft Defender for Endpoint (MDE) を、Microsoft Defender for Identity (MDI) と Microsoft Cloud App Security (MCAS) と組み合わせた、Microsoft 365 セキュリティ センターの利点。 この記事では、管理者向けの Microsoft 365 セキュリティ センターの進展について概説します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、モニター、レポート、ID、データ、デバイス、アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: f3920942925efbe334df84370c61fbe6a98ad49f
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939266"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a><span data-ttu-id="a7a8c-105">統合された Microsoft 365 セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="a7a8c-105">The unified Microsoft 365 security center overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a7a8c-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a7a8c-106">**Applies to:**</span></span>

- [<span data-ttu-id="a7a8c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7a8c-107">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="a7a8c-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a7a8c-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a7a8c-109">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a7a8c-109">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

> <span data-ttu-id="a7a8c-110">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a7a8c-110">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="a7a8c-111">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-111">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

<span data-ttu-id="a7a8c-112">改善された **Microsoft 365 セキュリティ センター** ([https://security.microsoft.com](https://security.microsoft.com)) は、保護、検出、調査、および、*メール*、*コラボレーション*、*ID*、*デバイス* の脅威への対応を中央ポータルに統合します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-112">The improved **Microsoft 365 security center** ([https://security.microsoft.com](https://security.microsoft.com)) combines protection, detection, investigation, and response to *email*, *collaboration*, *identity*, and *device* threats, in a central portal.</span></span>

<span data-ttu-id="a7a8c-113">Microsoft 365 セキュリティ センターは、Microsoft Defender セキュリティ センターや Office 365 セキュリティ/コンプライアンス センターなどの既存の Microsoft セキュリティ ポータルの機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-113">Microsoft 365 security center brings together functionality from existing Microsoft security portals, like Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span> <span data-ttu-id="a7a8c-114">セキュリティ センターは、情報への迅速なアクセス、よりシンプルなレイアウト、およびより簡単に使用できるように関連情報をまとめることを重視しています。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-114">The security center emphasizes quick access to information, simpler layouts, and bringing related information together for easier use.</span></span> <span data-ttu-id="a7a8c-115">このセンターには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-115">This center includes:</span></span>

- <span data-ttu-id="a7a8c-116">**[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 は、メールと Office 365 リソースを保護するための一連の防止、検出、調査、およびハンティング機能を使用して、組織が企業を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-116">**[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 helps organizations secure their enterprise with a set of prevention, detection, investigation and hunting features to protect email, and Office 365 resources.</span></span>
- <span data-ttu-id="a7a8c-117">**[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** は、組織内のデバイスに対して、予防的な保護、侵害後の検出、自動調査、および対応を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-117">**[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** delivers preventative protection, post-breach detection, automated investigation, and response for devices in your organization.</span></span>
- <span data-ttu-id="a7a8c-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** は、Microsoft の *Extended Detection and Response* (XDR) ソリューションの一部であり、Microsoft 365 セキュリティ ポートフォリオを活用して、ドメイン全体の脅威データを自動的に分析し、単一のダッシュボードで攻撃の全体像を構築します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** is part of Microsoft’s *Extended Detection and Response* (XDR) solution that leverages the Microsoft 365 security portfolio to automatically analyze threat data across domains, and build a picture of an attack on a single dashboard.</span></span>

<span data-ttu-id="a7a8c-119">Office 365 セキュリティ/コンプライアンス センターまたは Microsoft Defender セキュリティ センターからの変更点に関する情報が必要な場合は、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-119">If you need information about what's changed from the Office 365 Security & Compliance center or the Microsoft Defender Security Center, see:</span></span>

- [<span data-ttu-id="a7a8c-120">Microsoft 365 セキュリティ センターの Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a7a8c-120">Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="a7a8c-121">Microsoft 365 セキュリティ センターの Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a7a8c-121">Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a><span data-ttu-id="a7a8c-122">想定される変化</span><span class="sxs-lookup"><span data-stu-id="a7a8c-122">What to expect</span></span>

<span data-ttu-id="a7a8c-123">Office 365 セキュリティ/コンプライアンス センター (protection.office.com) および Microsoft Defender セキュリティ センター (securitycenter.microsoft.com) で使用するすべてのセキュリティ コンテンツは、*Microsoft 365 セキュリティ センター* にあります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-123">All the security content that you use in the Office 365 Security and Compliance Center (protection.office.com) and the Microsoft Defender security center (securitycenter.microsoft.com) can now be found in the *Microsoft 365 security center*.</span></span>

<span data-ttu-id="a7a8c-124">Microsoft 365 セキュリティ センターは、さまざまなワークロードからのシグナルを一連の統合エクスペリエンスに取り込み、セキュリティ チームが攻撃を調査して対応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-124">Microsoft 365 security center helps security teams investigate and respond to attacks by bringing in signals from different workloads into a set of unified experiences for:</span></span>

- <span data-ttu-id="a7a8c-125">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="a7a8c-125">Incidents & alerts</span></span>
- <span data-ttu-id="a7a8c-126">検索</span><span class="sxs-lookup"><span data-stu-id="a7a8c-126">Hunting</span></span>
- <span data-ttu-id="a7a8c-127">アクション センター</span><span class="sxs-lookup"><span data-stu-id="a7a8c-127">Action Center</span></span>
- <span data-ttu-id="a7a8c-128">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="a7a8c-128">Threat analytics</span></span>

<span data-ttu-id="a7a8c-129">Microsoft 365 セキュリティ センターは、Microsoft Defender for Office 365 および Microsoft Defender for Endpoint を統合する際に、*統一性、明確性、および共通の目標* を強調しています。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-129">The Microsoft 365 security center emphasizes *unity, clarity, and common goals* as it merges Microsoft Defender for Office 365 and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a7a8c-130">マージは、以下に示す優先順位に基づいて行われたので、各セキュリティ スイートが次の組み合わせに持ち込んだ機能を犠牲にすることなく行いました。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-130">The merge was based on the priorities listed below, and made without sacrificing the capabilities that each security suite brought to the combination of:</span></span>

- <span data-ttu-id="a7a8c-131">共通の構成要素</span><span class="sxs-lookup"><span data-stu-id="a7a8c-131">Common building blocks</span></span>
- <span data-ttu-id="a7a8c-132">一般的な用語</span><span class="sxs-lookup"><span data-stu-id="a7a8c-132">Common terminology</span></span>
- <span data-ttu-id="a7a8c-133">共通エンティティ</span><span class="sxs-lookup"><span data-stu-id="a7a8c-133">Common entities</span></span>
- <span data-ttu-id="a7a8c-134">他のワークロードとの機能のパリティ</span><span class="sxs-lookup"><span data-stu-id="a7a8c-134">Feature parity with other workloads</span></span>

> [!NOTE]
> <span data-ttu-id="a7a8c-135">統合された Microsoft 365 セキュリティ センターには、移行手順を実行したり、新しいライセンスを購入する必要なしにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-135">The unified Microsoft 365 security center will be accessible without any need for customers to take migration steps or purchase a new license.</span></span> <span data-ttu-id="a7a8c-136">たとえば、この新しいポータルは、Office 365 プラン 1 とプラン 2 の Microsoft Defender を使用する場合と同様に、E3 サブスクリプションを持つ管理者がアクセスできます。ただし、Exchange Online Protection または MDO Plan 1 のお客様には、サブスクリプション ライセンスでサポートされているセキュリティ機能だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-136">For example, this new portal will be accessible to administrators with an E3 subscription, just as it is to those with Microsoft Defender for Office 365 Plan 1 and Plan 2; however, Exchange Online Protection, or MDO Plan 1 customers will see only the security features their subscription license supports.</span></span> <span data-ttu-id="a7a8c-137">新しいセンターの目的は、セキュリティを一元化する方法です。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-137">The goal of the new center is to centralize security.</span></span>

## <a name="unified-investigations"></a><span data-ttu-id="a7a8c-138">統一された調査</span><span class="sxs-lookup"><span data-stu-id="a7a8c-138">Unified investigations</span></span>

<span data-ttu-id="a7a8c-139">セキュリティ センターを統合すると、Microsoft 365 全体でセキュリティ インシデントを調査する 1 つの場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-139">Converging security centers creates a single place for investigating security incidents across Microsoft 365.</span></span> <span data-ttu-id="a7a8c-140">主な例は **、[** インシデント]  & Microsoft 365 セキュリティ センターのクイック 起動時のアラートです。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-140">A primary example is **Incidents** under **Incidents & alerts** on the quick launch of the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Microsoft 365 セキュリティ センターの [インシデント] ページ。":::

<span data-ttu-id="a7a8c-142">インシデント名を選択すると、収束セキュリティ センターの値を示すページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-142">Selecting an incident name displays a page that demonstrates the value of converging security centers.</span></span>

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 セキュリティ センターのインシデントの概要ページの例":::

<!--
![Example of the Summary page for an incident in the Microsoft 365 security center](../../media/converged-incident-info-3.png)
--> 

<span data-ttu-id="a7a8c-144">インシデント ページの上部には、[概要] タブ、[通知] 、[**デバイス**] 、[**ユーザー**] 、[メールボックス] 、[調査]、および **[証拠**] タブが **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-144">Along the top of an incident page, you'll see the **Summary**, **Alerts**, **Devices**, **Users**, **Mailboxes**, **Investigations**, and **Evidence** tabs.</span></span> <span data-ttu-id="a7a8c-145">詳細については、次のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-145">Select these tabs for more detailed information.</span></span> <span data-ttu-id="a7a8c-146">たとえば、[ユーザー]タブには、統合ワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Cloud App Security) のユーザーの情報と、オンプレミスの Active Directory ドメイン サービス (AD DS)、Azure Active Directory (Azure AD)、サードパーティ ID プロバイダーなどのさまざまなソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-146">For example, the **Users** tab displays information for users from converged workloads (Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security) and a range of sources such as on-premises Active Directory Domain Services (AD DS), Azure Active Directory (Azure AD), and third-party identity providers.</span></span> <span data-ttu-id="a7a8c-147">詳細については、「ユーザーの調査 [」を参照してください](investigate-users.md)。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-147">For more information, see [investigate users](investigate-users.md).</span></span>

<span data-ttu-id="a7a8c-148">環境内のインシデントを確認し、これらのタブをドリルダウンし、さまざまな種類の脅威に対してインシデントに提供された情報にアクセスする方法について理解を深める方法を実践してください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-148">Take the time to review the incidents in your environment, drill down into these tabs, and practice building an understanding of how to access the information provided for incidents for different kinds of threats.</span></span>

<span data-ttu-id="a7a8c-149">詳細については [、「Microsoft 365 セキュリティ センターでのインシデント」を参照してください](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-149">For more information, see [incidents in the Microsoft 365 security center](incidents-overview.md).</span></span>

## <a name="improved-processes"></a><span data-ttu-id="a7a8c-150">改善されたプロセス</span><span class="sxs-lookup"><span data-stu-id="a7a8c-150">Improved processes</span></span>

<span data-ttu-id="a7a8c-151">共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードにまとめられて、見つけやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-151">Common controls and content either appear in the same place, or are condensed into one feed of data making it easier to find.</span></span> <span data-ttu-id="a7a8c-152">たとえば、統一された設定。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-152">For example, unified settings.</span></span>

### <a name="unified-settings"></a><span data-ttu-id="a7a8c-153">統一された設定</span><span class="sxs-lookup"><span data-stu-id="a7a8c-153">Unified settings</span></span>

![[役割] をクリックして、[設定] ページを開きました。このページには、[全般設定]、[アクセス許可]、[API]、および [ルール] が含まれています。](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a><span data-ttu-id="a7a8c-157">アクセス許可と役割</span><span class="sxs-lookup"><span data-stu-id="a7a8c-157">Permissions & roles</span></span>

![エンドポイントの役割とグループ、役割、およびデバイス グループを表示する [アクセス許可と役割] ページ。](../../media/converged-roles-5.png)

 <span data-ttu-id="a7a8c-159">Microsoft 365 セキュリティ センターへのアクセスは、Azure Active Directory グローバル ロールを使用して、またはカスタム ロールを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-159">Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles.</span></span> <span data-ttu-id="a7a8c-160">Defender for Endpoint については、「[Microsoft Defender セキュリティ センターへのユーザー アクセスの割り当て](/microsoft-365/security/defender-endpoint/assign-portal-access)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-160">For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/assign-portal-access).</span></span> <span data-ttu-id="a7a8c-161">Defender for Office 365 については、「[Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのアクセス許可](../office-365-security/permissions-microsoft-365-compliance-security.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-161">For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](../office-365-security/permissions-microsoft-365-compliance-security.md).</span></span>

- <span data-ttu-id="a7a8c-162">[Microsoft 365 Defender へのアクセスを管理する](m365d-permissions.md)方法の詳細</span><span class="sxs-lookup"><span data-stu-id="a7a8c-162">Learn more about how to [manage access to Microsoft 365 Defender](m365d-permissions.md)</span></span>
- <span data-ttu-id="a7a8c-163">Microsoft 365 セキュリティ センターで[カスタム ロールを作成する](custom-roles.md)方法の詳細</span><span class="sxs-lookup"><span data-stu-id="a7a8c-163">Learn more about how to [create custom roles](custom-roles.md) in Microsoft 365 security center</span></span>

> [!NOTE]
> <span data-ttu-id="a7a8c-164">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は、[Microsoft Defender セキュリティ センターでアクセスが許可される](./mssp-access.md)のと同じ方法で、[マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスの許可](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-164">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

### <a name="integrated-reports"></a><span data-ttu-id="a7a8c-165">統合レポート</span><span class="sxs-lookup"><span data-stu-id="a7a8c-165">Integrated reports</span></span>

<span data-ttu-id="a7a8c-166">レポートは、Microsoft 365 セキュリティ センターでも統合されています。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-166">Reports are also unified in the Microsoft 365 security center.</span></span> <span data-ttu-id="a7a8c-167">管理者は、一般的なセキュリティ レポートから始めて、エンドポイント、メール、コラボレーションに関する特定のレポートに分岐できます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-167">Admins can start with a general security report, and branch into specific reports about endpoints, email & collaboration.</span></span> <span data-ttu-id="a7a8c-168">ここでのリンクは、ワークロード構成に基づいて動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-168">The links here are dynamically generated based upon workload configuration.</span></span>

### <a name="quickly-view-your-microsoft-365-environment"></a><span data-ttu-id="a7a8c-169">Microsoft 365 環境をすばやく表示する</span><span class="sxs-lookup"><span data-stu-id="a7a8c-169">Quickly view your Microsoft 365 environment</span></span>

<span data-ttu-id="a7a8c-170">**ホーム** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-170">The **Home** page shows many of the common cards that security teams need.</span></span> <span data-ttu-id="a7a8c-171">カードとデータの構成は、ユーザーの役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-171">The composition of cards and data is dependent on the user role.</span></span> <span data-ttu-id="a7a8c-172">Microsoft 365 セキュリティ センターは役割ベースのアクセス制御を使用しているため、役割が異なれば、日常業務にとってより意味のあるカードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-172">Because the Microsoft 365 security center uses role-based access control, different roles will see cards that are more meaningful to their day to day jobs.</span></span>  

<span data-ttu-id="a7a8c-173">この一目でわかる情報は、組織内の最新の活動についていくのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-173">This at-a-glance information helps you keep up with the latest activities in your organization.</span></span> <span data-ttu-id="a7a8c-174">Microsoft 365 セキュリティ センターは、さまざまなソースからの信号をまとめて、Microsoft 365 環境の全体像を示します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-174">The Microsoft 365 security center brings together signals from different sources to present a holistic view of your Microsoft 365 environment.</span></span>

<span data-ttu-id="a7a8c-175">カードは次のカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-175">The cards fall into these categories:</span></span>

- <span data-ttu-id="a7a8c-176">**ID** - 組織内の ID を監視し、疑わしいまたは危険な行動を追跡します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-176">**Identities**- Monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="a7a8c-177">[ID 保護の詳細をご覧ください](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-177">[Learn more about identity protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>
- <span data-ttu-id="a7a8c-178">**データ** - 無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-178">**Data** - Help track user activity that could lead to unauthorized data disclosure.</span></span>
- <span data-ttu-id="a7a8c-179">**デバイス** - デバイス上のアラート、違反アクティビティ、およびその他の脅威に関する最新情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-179">**Devices** - Get up-to-date information on alerts, breach activity, and other threats on your devices.</span></span>
- <span data-ttu-id="a7a8c-180">**アプリ** - 組織でクラウド アプリがどのように使用されているかについての分析情報を得ます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-180">**Apps** - Gain insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="a7a8c-181">[Cloud App Security で検出されたアプリの詳細をご覧ください](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-181">[Learn more about Cloud App Security discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="threat-analytics-with-better-data-coverage"></a><span data-ttu-id="a7a8c-182">より優れたデータ カバレッジを備えた脅威の分析</span><span class="sxs-lookup"><span data-stu-id="a7a8c-182">Threat analytics with better data coverage</span></span>
<span data-ttu-id="a7a8c-183">次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡し、対応します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-183">Track and respond to emerging threats with the following Microsoft 365 Defender threat analytics integrated experience:</span></span>

- <span data-ttu-id="a7a8c-184">Microsoft Defender for Endpoint と Microsoft Defender for Office 365 の間のデータ カバレッジが向上し、インシデント管理、自動調査、修復、およびドメイン全体での予防的または事後対応的な脅威ハンティングの組み合わせが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-184">Better data coverage between Microsoft Defender for Endpoint and Microsoft Defender for Office 365, making combined incident management, automatic investigation, remediation, and proactive or reactive threat hunting across-domain possible.</span></span> 
- <span data-ttu-id="a7a8c-185">Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えて、Microsoft Defender for Office 365 からのメール関連の検出と軽減。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-185">Email-related detections and mitigations from Microsoft Defender for Office 365, in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="a7a8c-186">Microsoft Defender for Endpoint と Microsoft Defender for Office 365 全体のエンドツーエンドの攻撃ストーリーにアラートを集約して、作業キューを削減し、調査を簡素化および高速化する、脅威関連のインシデントのビュー。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-186">A view of threat-related incidents which aggregate alerts into end-to-end attack stories across Microsoft Defender for Endpoint and Microsoft Defender for Office 365 to reduce the work queue, as well as simplify and speed up your investigation.</span></span>
- <span data-ttu-id="a7a8c-187">Microsoft 365 Defender ソリューションによって検出され、ブロックされた攻撃の試み。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-187">Attack attempts detected and blocked by Microsoft 365 Defender solutions.</span></span> <span data-ttu-id="a7a8c-188">さらなる曝露のリスクを軽減し、回復力を高める予防措置を推進するために使用できるデータもあります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-188">There's also data that you can use to drive preventive actions that mitigate the risk of further exposure and increase resilience.</span></span> 
- <span data-ttu-id="a7a8c-189">実用的な情報にスポットライトを当て、緊急に焦点を合わせ、調査し、レポートから活用するデータをすばやく特定できるようにする拡張された設計。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-189">Enhanced design that puts actionable information in the spotlight to help you  quickly identify data to urgently focus on, investigate, and leverage from the reports.</span></span>

## <a name="a-centralized-learning-hub"></a><span data-ttu-id="a7a8c-190">一元化されたラーニング ハブ</span><span class="sxs-lookup"><span data-stu-id="a7a8c-190">A centralized Learning Hub</span></span>

<span data-ttu-id="a7a8c-191">Microsoft 365 セキュリティ センターには、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、docs.microsoft.com の公式ドキュメントなどのリソースから公式ガイダンスを作成するラーニング ハブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-191">The Microsoft 365 security center includes a learning hub that bubbles up official guidance from resources such as the Microsoft security blog, the Microsoft security community on YouTube, and the official documentation at docs.microsoft.com.</span></span>

<span data-ttu-id="a7a8c-192">ラーニング ハブ内では、メールとコラボレーション (Microsoft Defender for Office 365 または MDO) のガイダンスが、Endpoint (Microsoft Defender for Endpoint または MDE) および Microsoft 365 Defender ラーニング リソースと並んでいます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-192">Inside the learning hub, Email & Collaboration (Microsoft Defender for Office 365 or MDO) guidance is side-by-side with Endpoint (Microsoft Defender for Endpoint or MDE), and Microsoft 365 Defender learning resources.</span></span>

<span data-ttu-id="a7a8c-193">ラーニング ハブは、「Microsoft 365 Defender を使用して調査する方法」</span><span class="sxs-lookup"><span data-stu-id="a7a8c-193">The learning hub opens with Learning paths organized around topics such as “How to Investigate Using Microsoft 365 Defender?”</span></span> <span data-ttu-id="a7a8c-194">および「Microsoft Defender for Office 365 のベスト プラクティス」などのトピックを中心に編成されたラーニング パスで始まります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-194">and “Microsoft Defender for Office 365 Best Practices”.</span></span> <span data-ttu-id="a7a8c-195">このセクションは現在、Microsoft 内のセキュリティ製品グループによってキュレーションされています。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-195">This section is currently curated by the security Product Group inside Microsoft.</span></span> <span data-ttu-id="a7a8c-196">各ラーニング パスは、概念を理解するのにかかると予想される時間を反映しています。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-196">Each Learning path reflects a projected time it takes to get through the concepts.</span></span> <span data-ttu-id="a7a8c-197">たとえば、「Microsoft Defender for Office 365 ユーザー アカウントが侵害された場合の手順」は 8 分かかると予想されており、その場で学ぶ価値があります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-197">For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.</span></span>

<span data-ttu-id="a7a8c-198">コンテンツをクリックした後、このサイトをブックマークして、ブックマークを 'セキュリティ' または 'クリティカル' フォルダーに整理すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-198">After clicking through to the content, it may be useful to bookmark this site and organize bookmarks into a 'Security' or 'Critical' folder.</span></span> <span data-ttu-id="a7a8c-199">すべてのラーニング パスを表示するには、メイン パネルの [すべて表示] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-199">To see all Learning paths, click the Show all link in the main panel.</span></span>

> [!NOTE]
> <span data-ttu-id="a7a8c-200">Microsoft 365 セキュリティ センターのラーニング ハブの上部には、製品 (現在、Microsoft 365 Defender、Microsoft Defender for Endpoint、および Microsoft Defender for Office 365) から選択できる便利な **フィルター** があります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-200">There are helpful **filters** along the top of the Microsoft 365 security center learning hub that will let you choose between products (currently Microsoft 365 Defender, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365).</span></span> <span data-ttu-id="a7a8c-201">各セクションの学習リソースの数がリストされていることに注意してください。これは、学習者がトレーニングと学習のために手元にあるリソースの数を追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-201">Notice that the number of learning resources for each section is listed, which can help learners keep track of how many resources they have at hand for training and learning.</span></span>
>
> <span data-ttu-id="a7a8c-202">製品フィルターに沿って、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する知識または経験のレベル、セキュリティの役割、および製品の機能が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-202">Along with the Product filter, current topics, types of resources (from videos to webinars), levels of familiarity or experience with security areas, security roles, and product features are listed.</span></span>

> [!TIP]
> <span data-ttu-id="a7a8c-203">[Microsoft Learn](https://docs.microsoft.com/e/learn/)には他にも多くの学習機会があります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-203">There are lots of other learning opportunities in [Microsoft Learn](https://docs.microsoft.com/e/learn/).</span></span> <span data-ttu-id="a7a8c-204">コース [MS-500T02-A: Microsoft 365](https://docs.microsoft.com/learn/certifications/courses/ms-500t02)Threat Protection の実装などの認定トレーニングがあります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-204">You'll find certification training such as [Course MS-500T02-A: Implementing Microsoft 365 Threat Protection](https://docs.microsoft.com/learn/certifications/courses/ms-500t02).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="a7a8c-205">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="a7a8c-205">Send us your feedback</span></span>

<span data-ttu-id="a7a8c-206">フィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-206">We need your feedback.</span></span> <span data-ttu-id="a7a8c-207">私たちは常に改善を目指しています。ご要望がありましたら、[Microsoft 365 Defender のフィードバックを送信してください](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-207">We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).</span></span>

<span data-ttu-id="a7a8c-208">この記事からフィードバックを残すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-208">You can also leave feedback from this article.</span></span> <span data-ttu-id="a7a8c-209">[フィードバックの送信と表示] の下にある最後の [フィードバック] セクションには、オプション *[この製品]* または *[このページ]* があります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-209">In the 'Feedback' section at the end under 'Submit and view feedback for', the options are *This product*, or *This page*.</span></span>

<span data-ttu-id="a7a8c-210">*製品* のフィードバックには、**[この製品]** ボタンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-210">Use the **This product** button for *product* feedback:</span></span>

1. <span data-ttu-id="a7a8c-211">記事の下部にある *[この製品]* を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-211">Select *This product* at the bottom of the article.</span></span>
    1. <span data-ttu-id="a7a8c-212">これらの指示を読み続ける場合は、ボタンを右クリックして [新しいタブで開く] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-212">Right-click the button and 'Open in a new tab' if you want to keep reading these directions.</span></span>
2. <span data-ttu-id="a7a8c-213">これにより、**UserVoice フォーラム** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-213">This will navigate to the **UserVoice forum**.</span></span>
3. <span data-ttu-id="a7a8c-214">2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-214">You have 2 options:</span></span>
    1. <span data-ttu-id="a7a8c-215">テキスト ボックス「*Office 365 でコンプライアンスを改善したり、ユーザーをより適切に保護するにはどうすればよいですか?*」まで下にスクロールして、*Microsoft 365 セキュリティ センター* に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-215">Scroll down to the text box *How can we improve compliance or protect your users better in Office 365?* and paste in *Microsoft 365 security center*.</span></span> <span data-ttu-id="a7a8c-216">結果から自分のようなアイデアを探して賛成票を投じるか、**[新しいアイデアを投稿する]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-216">You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.</span></span>
    1. <span data-ttu-id="a7a8c-217">この問題がすでに報告されていると確信し、1 票または複数の票でそのプロファイルを上げたい場合は、UserVoice の右側にある *[フィードバックの送信]* ボックスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-217">If you feel certain this issue is already reported, and want to raise its profile with a vote (or votes), use the *Give Feedback* box on the right side of UserVoice.</span></span> <span data-ttu-id="a7a8c-218">*Microsoft 365 セキュリティ センター* を検索し、**問題を見つけ、投票ボタンを使用して** そのステータスを上げます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-218">Search for *Microsoft 365 security center*, **find the issue, and use the vote button** to raise its status.</span></span>

<span data-ttu-id="a7a8c-219">記事自体に関するフィードバックは、*[このページ]* を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-219">Use *This page* for feedback on the article itself.</span></span> <span data-ttu-id="a7a8c-220">フィードバックしていただき、ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-220">Thanks for your feedback.</span></span> <span data-ttu-id="a7a8c-221">あなたの声は製品の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-221">Your voice helps us improve products.</span></span>

### <a name="explore-what-the-security-center-has-to-offer"></a><span data-ttu-id="a7a8c-222">セキュリティ センターが提供するものを調べる</span><span class="sxs-lookup"><span data-stu-id="a7a8c-222">Explore what the security center has to offer</span></span>

<span data-ttu-id="a7a8c-223">Microsoft 365 セキュリティ センターの特徴と機能を調べてください。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-223">Keep exploring the features and capabilities in the Microsoft 365 security center:</span></span>

- [<span data-ttu-id="a7a8c-224">インシデントとアラートを管理する</span><span class="sxs-lookup"><span data-stu-id="a7a8c-224">Manage incidents and alerts</span></span>](manage-incidents.md)
- [<span data-ttu-id="a7a8c-225">脅威の分析を使用して、新たな脅威を追跡し対応する</span><span class="sxs-lookup"><span data-stu-id="a7a8c-225">Track and respond to emerging threats with threat analytics</span></span>](threat-analytics.md)
- [<span data-ttu-id="a7a8c-226">アクション センター</span><span class="sxs-lookup"><span data-stu-id="a7a8c-226">The Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="a7a8c-227">デバイス、メール、アプリ、ID 全体の脅威を探す</span><span class="sxs-lookup"><span data-stu-id="a7a8c-227">Hunt for threats across devices, emails, apps, and identities</span></span>](./advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a7a8c-228">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="a7a8c-228">Custom detection rules</span></span>](./custom-detection-rules.md)
- [<span data-ttu-id="a7a8c-229">メールとコラボレーションのアラート</span><span class="sxs-lookup"><span data-stu-id="a7a8c-229">Email & collaboration alerts</span></span>](../../compliance/alert-policies.md#default-alert-policies)
- <span data-ttu-id="a7a8c-230">[フィッシング攻撃のシミュレーションを作成し](../office-365-security/attack-simulation-training.md)、[チームをトレーニングするためのペイロードを作成する](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="a7a8c-230">[Create a phishing attack simulation](../office-365-security/attack-simulation-training.md) and [create a payload for training your teams](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span></span>
 
### <a name="related-information"></a><span data-ttu-id="a7a8c-231">関連情報</span><span class="sxs-lookup"><span data-stu-id="a7a8c-231">Related information</span></span>
- [<span data-ttu-id="a7a8c-232">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="a7a8c-232">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="a7a8c-233">Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a7a8c-233">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="a7a8c-234">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a7a8c-234">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="a7a8c-235">アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="a7a8c-235">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)