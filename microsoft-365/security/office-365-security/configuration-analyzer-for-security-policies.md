---
title: セキュリティ ポリシーの構成アナライザー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、構成アナライザーを使用して、標準保護と厳密な保護の事前設定されたセキュリティ ポリシーの下にあるセキュリティ ポリシーを見つけて修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d2ad1449730f392adc27c8ed2a8fc8e9ecc7a04
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789318"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="409e4-103">EOP および Microsoft Defender の保護ポリシー用の構成Office 365</span><span class="sxs-lookup"><span data-stu-id="409e4-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="409e4-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="409e4-104">**Applies to**</span></span>
- [<span data-ttu-id="409e4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="409e4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="409e4-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="409e4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="409e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="409e4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="409e4-108">Microsoft 365 セキュリティ センターの構成アナライザーは、設定が事前設定されたセキュリティ ポリシーの標準保護および厳密な保護プロファイル設定の下にあるセキュリティ ポリシーを見つけて修正するための中心的な場所を[提供します](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="409e4-108">Configuration analyzer in the Microsoft 365 security center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="409e4-109">次の種類のポリシーは、構成アナライザーによって分析されます。</span><span class="sxs-lookup"><span data-stu-id="409e4-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="409e4-110">**Exchange Online Protection (EOP)** ポリシー : これには、Microsoft 365メールボックスを持Exchange Onlineスタンドアロンの EOP 組織が含Exchange Onlineされます。</span><span class="sxs-lookup"><span data-stu-id="409e4-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="409e4-111">[スパム対策ポリシー](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="409e4-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="409e4-112">[マルウェア対策ポリシー](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="409e4-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="409e4-113">[EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="409e4-113">[EOP anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="409e4-114">**Microsoft Defender for Office 365 ポリシー**: これには、アドオン サブスクリプションの Microsoft 365 E5または Defender をOffice 365組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="409e4-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="409e4-115">Microsoft Defender のフィッシング対策ポリシーは、次Office 365含まれます。</span><span class="sxs-lookup"><span data-stu-id="409e4-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>
    - <span data-ttu-id="409e4-116">EOP [フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings) ポリシーで使用できるスプーフィング設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="409e4-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="409e4-117">偽装設定</span><span class="sxs-lookup"><span data-stu-id="409e4-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="409e4-118">高度なフィッシングのしきい値</span><span class="sxs-lookup"><span data-stu-id="409e4-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - <span data-ttu-id="409e4-119">[セーフリンク ポリシー](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="409e4-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>
  - <span data-ttu-id="409e4-120">[セーフ添付ファイル ポリシー](set-up-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="409e4-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="409e4-121">基準 **として使用** される標準ポリシーと **厳密** なポリシー設定の値については [、「EOP](recommended-settings-for-eop-and-office365.md)および Microsoft Defender のセキュリティに関する推奨設定Office 365されています。</span><span class="sxs-lookup"><span data-stu-id="409e4-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="409e4-122">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="409e4-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="409e4-123"><https://security.microsoft.com> でセキュリティ センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="409e4-123">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="409e4-124">[構成アナライザー] ページに直接 **移動するには、** を使用します <https://security.microsoft.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="409e4-124">To go directly to the **Configuration analyzer** page, use <https://security.microsoft.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="409e4-125">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409e4-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="409e4-126">この記事の手順を実行するには、セキュリティ センターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="409e4-126">You need to be assigned permissions in the security center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="409e4-127">構成アナライザーを使用してセキュリティ ポリシーを更新するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="409e4-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="409e4-128">構成アナライザーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティ リーダーの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="409e4-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="409e4-129">詳細については、「セキュリティ センター[のアクセス許可Microsoft 365参照してください](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="409e4-129">For more information, see [Permissions in the Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="409e4-130">ユーザーを対応する Azure Active Directory ロールに追加すると、セキュリティ センターで必要なアクセス許可と、セキュリティ センター内の他の機能に対するアクセス許可Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="409e4-130">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the security center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="409e4-131">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409e4-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="409e4-132">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="409e4-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security-center"></a><span data-ttu-id="409e4-133">セキュリティ センターで構成アナライザーを使用する</span><span class="sxs-lookup"><span data-stu-id="409e4-133">Use the configuration analyzer in the security center</span></span>

<span data-ttu-id="409e4-134">セキュリティ センターで、[メール] グループ **&[** 脅威&ポリシー] セクションの [構成アナライザー] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="409e4-134">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Templated policies** section \> **Configuration analyzer**.</span></span>

<span data-ttu-id="409e4-135">構成アナライザーには、次の 2 つの主なタブがあります。</span><span class="sxs-lookup"><span data-stu-id="409e4-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="409e4-136">**設定推奨事項**: Standard または **Strict** を選択し、それらの設定を既存のセキュリティ ポリシーと比較します。 </span><span class="sxs-lookup"><span data-stu-id="409e4-136">**Settings and recommendations**: You pick **Standard** or **Strict** and compare those settings to your existing security policies.</span></span> <span data-ttu-id="409e4-137">結果では、設定の値を調整して、Standard または Strict と同じレベルに設定できます。</span><span class="sxs-lookup"><span data-stu-id="409e4-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>
- <span data-ttu-id="409e4-138">**構成ドリフトの分析と履歴**: このビューでは、時間の流れによってポリシーの変更を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="409e4-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="409e4-139">構成アナライザーの [設定と推奨事項] タブ</span><span class="sxs-lookup"><span data-stu-id="409e4-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="409e4-140">既定では、標準保護プロファイルとの比較でタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="409e4-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="409e4-141">[厳密な推奨事項の表示] を選択して、厳密な保護プロファイルの **比較に切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="409e4-141">You can switch to the comparison of the Strict protection profile by selecting **View Strict recommendations**.</span></span> <span data-ttu-id="409e4-142">切り替えるには、[標準の **推奨事項の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="409e4-142">To switch back, select **View Standard recommendations**.</span></span>

![設定アナライザーの [推奨事項] ビューの設定と推奨事項](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="409e4-144">既定では、[ **ポリシー グループ/** 設定名] 列には、さまざまな種類のセキュリティ ポリシーの折りたたまれているビューと、改善が必要な設定の数 (必要な場合) が含まれる。</span><span class="sxs-lookup"><span data-stu-id="409e4-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="409e4-145">ポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="409e4-145">The types of policies are:</span></span>

- <span data-ttu-id="409e4-146">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="409e4-146">**Anti-spam**</span></span>
- <span data-ttu-id="409e4-147">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="409e4-147">**Anti-phishing**</span></span>
- <span data-ttu-id="409e4-148">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="409e4-148">**Anti-malware**</span></span>
- <span data-ttu-id="409e4-149">**セーフ添付ファイル**(サブスクリプションに Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="409e4-149">**Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="409e4-150">**セーフ リンク**(サブスクリプションに Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="409e4-150">**Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="409e4-151">既定のビューでは、すべてが折りたためます。</span><span class="sxs-lookup"><span data-stu-id="409e4-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="409e4-152">各ポリシーの横には、ポリシー (変更できる) と、Standard または Strict Protection プロファイルの対応するポリシー (変更できない) の設定の比較結果の概要があります。</span><span class="sxs-lookup"><span data-stu-id="409e4-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="409e4-153">比較している保護プロファイルに関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="409e4-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="409e4-154">**緑**: すべての既存のポリシーのすべての設定は、少なくとも保護プロファイルと同じ安全です。</span><span class="sxs-lookup"><span data-stu-id="409e4-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="409e4-155">**オレンジ**: 既存のポリシーの設定の数が少ない場合、保護プロファイルほど安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="409e4-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="409e4-156">**赤**: 既存のポリシーの設定のかなりの数は、保護プロファイルほど安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="409e4-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="409e4-157">これは、多くのポリシーのいくつかの設定、または 1 つのポリシーの多くの設定である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="409e4-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="409e4-158">良好な比較を行う場合は、「すべての設定は推奨事項に従う」 **というテキスト** \<**Standard** or **Strict**\> **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="409e4-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="409e4-159">それ以外の場合は、変更する推奨設定の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="409e4-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="409e4-160">[ポリシー グループ **/設定** 名] を展開すると、注意が必要な各ポリシーのすべてのポリシーと関連付けられた設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="409e4-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="409e4-161">または、特定の種類のポリシー (スパム **対策など)** を展開して、注意が必要なポリシーの種類に設定を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="409e4-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="409e4-162">比較に改善の推奨事項がない場合 (緑)、ポリシーを展開すると何も表示しません。</span><span class="sxs-lookup"><span data-stu-id="409e4-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="409e4-163">改善に関する推奨事項 (オレンジまたは赤) が多数ある場合は、注意が必要な設定が表示され、対応する情報が次の列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="409e4-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="409e4-164">**ポリシー グループ/設定名**: 注意が必要な設定の名前。</span><span class="sxs-lookup"><span data-stu-id="409e4-164">**Policy group/setting name**: The name of the setting that requires your attention.</span></span> <span data-ttu-id="409e4-165">たとえば、前のスクリーンショットでは、既定のスパム対策ポリシーの設定です。</span><span class="sxs-lookup"><span data-stu-id="409e4-165">For example, in the previous screenshot, it's the settings in the default anti-spam policy.</span></span>
- <span data-ttu-id="409e4-166">**ポリシー**: 設定を含む影響を受けるポリシーの名前。</span><span class="sxs-lookup"><span data-stu-id="409e4-166">**Policy**: The name of the affected policy that contains the setting.</span></span>
- <span data-ttu-id="409e4-167">**適用:** 影響を受けるポリシーが適用されるユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="409e4-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>
- <span data-ttu-id="409e4-168">**現在の構成**: 設定の現在の値。</span><span class="sxs-lookup"><span data-stu-id="409e4-168">**Current configuration**: The current value of the setting.</span></span> <span data-ttu-id="409e4-169">すべての受信者に適用されるその種類の既定のポリシーでは、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="409e4-169">For the default policy of that type that applies to all recipients, this value is blank.</span></span>
- <span data-ttu-id="409e4-170">**最終更新日 :** ポリシーが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="409e4-170">**Last modified**: The date that the policy was last modified.</span></span>
- <span data-ttu-id="409e4-171">**推奨事項**: Standard または Strict Protection プロファイルの設定の値。</span><span class="sxs-lookup"><span data-stu-id="409e4-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="409e4-172">ポリシーの設定の値を保護プロファイルの推奨値と一致する値に変更するには、[採用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="409e4-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="409e4-173">変更が成功した場合は、「推奨事項が正常に採用されました」 **というメッセージが表示されます**。</span><span class="sxs-lookup"><span data-stu-id="409e4-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="409e4-174">[ **最新の情報** に更新] をクリックすると、推奨事項の数が減り、結果から特定の設定/ポリシー行が削除されます。</span><span class="sxs-lookup"><span data-stu-id="409e4-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="409e4-175">構成アナライザーの [構成ドリフト分析と履歴] タブ</span><span class="sxs-lookup"><span data-stu-id="409e4-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="409e4-176">このタブでは、カスタム セキュリティ ポリシーに加えた変更を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="409e4-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="409e4-177">既定では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="409e4-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="409e4-178">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="409e4-178">**Last modified**</span></span>
- <span data-ttu-id="409e4-179">**変更者**</span><span class="sxs-lookup"><span data-stu-id="409e4-179">**Modified by**</span></span>
- <span data-ttu-id="409e4-180">**設定名**</span><span class="sxs-lookup"><span data-stu-id="409e4-180">**Setting Name**</span></span>
- <span data-ttu-id="409e4-181">**ポリシー**</span><span class="sxs-lookup"><span data-stu-id="409e4-181">**Policy**</span></span>
- <span data-ttu-id="409e4-182">**型**</span><span class="sxs-lookup"><span data-stu-id="409e4-182">**Type**</span></span>
- <span data-ttu-id="409e4-183">**構成の変更**</span><span class="sxs-lookup"><span data-stu-id="409e4-183">**Configuration change**</span></span>
- <span data-ttu-id="409e4-184">**構成ドリフト**:**値の増減\*\*\*\*。**</span><span class="sxs-lookup"><span data-stu-id="409e4-184">**Configuration drift**: The value **Increase** or **Decrease**.</span></span>

<span data-ttu-id="409e4-185">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e4-185">To filter the results, click **Filter**.</span></span> <span data-ttu-id="409e4-186">表示される **[フィルター** ] フライアウトで、次のフィルターから選択できます。</span><span class="sxs-lookup"><span data-stu-id="409e4-186">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="409e4-187">**開始時刻** と **終了時刻** (日付)</span><span class="sxs-lookup"><span data-stu-id="409e4-187">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="409e4-188">**標準保護または\*\*\*\*厳密な保護**</span><span class="sxs-lookup"><span data-stu-id="409e4-188">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="409e4-189">結果をファイルにエクスポートするには、[エクスポート] .csvクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="409e4-189">To export the results to a .csv file, click **Export**.</span></span>

![Configuration Analyzer の構成ドリフト分析と履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
