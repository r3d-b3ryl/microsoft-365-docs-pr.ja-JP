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
ms.openlocfilehash: 49c54fa93d5ed95c6c3e0aa948646dd544ea4a5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924446"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="097dd-103">EOP および Microsoft Defender の保護ポリシー用の構成アナライザー (Office 365)</span><span class="sxs-lookup"><span data-stu-id="097dd-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="097dd-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="097dd-104">**Applies to**</span></span>
- [<span data-ttu-id="097dd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="097dd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="097dd-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="097dd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="097dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="097dd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="097dd-108">セキュリティ & コンプライアンス センターの構成アナライザーは、設定が事前設定されたセキュリティ ポリシーの標準保護および厳密な保護プロファイル設定の下にあるセキュリティ ポリシーを見つけて修正するための中心的な場所を [提供します](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="097dd-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="097dd-109">次の種類のポリシーは、構成アナライザーによって分析されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="097dd-110">**Exchange Online Protection (EOP)** ポリシー : これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="097dd-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="097dd-111">[スパム対策ポリシー](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="097dd-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="097dd-112">[マルウェア対策ポリシー](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="097dd-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="097dd-113">[EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="097dd-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="097dd-114">**Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5 または Defender が 365 アドオン サブスクリプションの組織Office含まれます。</span><span class="sxs-lookup"><span data-stu-id="097dd-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="097dd-115">Microsoft Defender for Office 365 のフィッシング対策ポリシー。</span><span class="sxs-lookup"><span data-stu-id="097dd-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="097dd-116">EOP [フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings) ポリシーで使用できるスプーフィング設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="097dd-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="097dd-117">偽装設定</span><span class="sxs-lookup"><span data-stu-id="097dd-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="097dd-118">高度なフィッシングのしきい値</span><span class="sxs-lookup"><span data-stu-id="097dd-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="097dd-119">[セーフ リンク ポリシー](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="097dd-119">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="097dd-120">[安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="097dd-120">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="097dd-121">基準 **として使用** される Standard および **Strict** ポリシー設定の値については、「EOP および Microsoft Defender for Office [365 セキュリティの推奨設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="097dd-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="097dd-122">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="097dd-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="097dd-123"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="097dd-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="097dd-124">[構成アナライザー] ページに直接 **移動するには、** を使用します <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="097dd-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="097dd-125">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="097dd-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="097dd-126">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="097dd-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="097dd-127">構成アナライザーを使用してセキュリティ ポリシーを更新するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="097dd-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="097dd-128">構成アナライザーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティ リーダーの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="097dd-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="097dd-129">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="097dd-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="097dd-130">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="097dd-131">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="097dd-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="097dd-132">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="097dd-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="097dd-133">セキュリティ コンプライアンス センターの構成&使用する</span><span class="sxs-lookup"><span data-stu-id="097dd-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="097dd-134">セキュリティ 管理コンプライアンス センター&、脅威管理 **ポリシー** \> **構成アナライザーに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="097dd-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![[脅威管理ポリシー] ページの構成 \> アナライザー ウィジェット](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="097dd-136">構成アナライザーには、次の 2 つの主なタブがあります。</span><span class="sxs-lookup"><span data-stu-id="097dd-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="097dd-137">**設定と推奨事項**: [標準] または [厳密] を選択し、それらの設定を既存のセキュリティ ポリシーと比較します。</span><span class="sxs-lookup"><span data-stu-id="097dd-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="097dd-138">結果では、設定の値を調整して、Standard または Strict と同じレベルに設定できます。</span><span class="sxs-lookup"><span data-stu-id="097dd-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="097dd-139">**構成ドリフトの分析と履歴**: このビューでは、時間の流れによってポリシーの変更を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="097dd-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="097dd-140">構成アナライザーの [設定と推奨事項] タブ</span><span class="sxs-lookup"><span data-stu-id="097dd-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="097dd-141">既定では、標準保護プロファイルとの比較でタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="097dd-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="097dd-142">[厳密な推奨事項の表示] をクリックすると、厳密な保護プロファイルの **比較に切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="097dd-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="097dd-143">切り替えるには、[標準の **推奨事項の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="097dd-143">To switch back, select **View Standard recommendations**.</span></span>

![構成アナライザーの [設定と推奨事項] ビュー](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="097dd-145">既定では、[ **ポリシー グループ/** 設定名] 列には、さまざまな種類のセキュリティ ポリシーの折りたたまれているビューと、改善が必要な設定の数 (必要な場合) が含まれる。</span><span class="sxs-lookup"><span data-stu-id="097dd-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="097dd-146">ポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="097dd-146">The types of policies are:</span></span>

- <span data-ttu-id="097dd-147">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="097dd-147">**Anti-spam**</span></span>
- <span data-ttu-id="097dd-148">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="097dd-148">**Anti-phishing**</span></span>
- <span data-ttu-id="097dd-149">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="097dd-149">**Anti-malware**</span></span>
- <span data-ttu-id="097dd-150">**ATP の安全な添付** ファイル (サブスクリプションに Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="097dd-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="097dd-151">**ATP セーフ リンク** (サブスクリプションに Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="097dd-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="097dd-152">既定のビューでは、すべてが折りたためます。</span><span class="sxs-lookup"><span data-stu-id="097dd-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="097dd-153">各ポリシーの横には、ポリシー (変更できる) と、Standard または Strict Protection プロファイルの対応するポリシー (変更できない) の設定の比較結果の概要があります。</span><span class="sxs-lookup"><span data-stu-id="097dd-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="097dd-154">比較している保護プロファイルに関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="097dd-155">**緑**: すべての既存のポリシーのすべての設定は、少なくとも保護プロファイルと同じ安全です。</span><span class="sxs-lookup"><span data-stu-id="097dd-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="097dd-156">**オレンジ**: 既存のポリシーの設定の数が少ない場合、保護プロファイルほど安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="097dd-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="097dd-157">**赤**: 既存のポリシーの設定のかなりの数は、保護プロファイルほど安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="097dd-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="097dd-158">これは、多くのポリシーのいくつかの設定、または 1 つのポリシーの多くの設定である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="097dd-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="097dd-159">良好な比較を行う場合は、「すべての設定は推奨事項に従う」 **というテキスト** \<**Standard** or **Strict**\> **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="097dd-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="097dd-160">それ以外の場合は、変更する推奨設定の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="097dd-161">[ポリシー グループ **/設定** 名] を展開すると、注意が必要な各ポリシーのすべてのポリシーと関連付けられた設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="097dd-162">または、特定の種類のポリシー (スパム **対策など)** を展開して、注意が必要なポリシーの種類に設定を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="097dd-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="097dd-163">比較に改善の推奨事項がない場合 (緑)、ポリシーを展開すると何も表示しません。</span><span class="sxs-lookup"><span data-stu-id="097dd-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="097dd-164">改善に関する推奨事項 (オレンジまたは赤) が多数ある場合は、注意が必要な設定が表示され、対応する情報が次の列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="097dd-165">注意が必要な設定の名前。</span><span class="sxs-lookup"><span data-stu-id="097dd-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="097dd-166">たとえば、前のスクリーンショットでは、スパム **対策ポリシーの** バルク メールしきい値です。</span><span class="sxs-lookup"><span data-stu-id="097dd-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="097dd-167">**ポリシー**: 設定を含む影響を受けるポリシーの名前。</span><span class="sxs-lookup"><span data-stu-id="097dd-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="097dd-168">**適用:** 影響を受けるポリシーが適用されるユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="097dd-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="097dd-169">**現在の構成**: 設定の現在の値。</span><span class="sxs-lookup"><span data-stu-id="097dd-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="097dd-170">**最終更新日 :** ポリシーが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="097dd-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="097dd-171">**推奨事項**: Standard または Strict Protection プロファイルの設定の値。</span><span class="sxs-lookup"><span data-stu-id="097dd-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="097dd-172">ポリシーの設定の値を保護プロファイルの推奨値と一致する値に変更するには、[採用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="097dd-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="097dd-173">変更が成功した場合は、「推奨事項が正常に採用されました」 **というメッセージが表示されます**。</span><span class="sxs-lookup"><span data-stu-id="097dd-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="097dd-174">[ **最新の情報** に更新] をクリックすると、推奨事項の数が減り、結果から特定の設定/ポリシー行が削除されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="097dd-175">構成アナライザーの [構成ドリフト分析と履歴] タブ</span><span class="sxs-lookup"><span data-stu-id="097dd-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="097dd-176">このタブでは、カスタム セキュリティ ポリシーに加えた変更を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="097dd-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="097dd-177">既定では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="097dd-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="097dd-178">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="097dd-178">**Last modified**</span></span>
- <span data-ttu-id="097dd-179">**変更者**</span><span class="sxs-lookup"><span data-stu-id="097dd-179">**Modified by**</span></span>
- <span data-ttu-id="097dd-180">**設定名**</span><span class="sxs-lookup"><span data-stu-id="097dd-180">**Setting Name**</span></span>
- <span data-ttu-id="097dd-181">**Policy**</span><span class="sxs-lookup"><span data-stu-id="097dd-181">**Policy**</span></span>
- <span data-ttu-id="097dd-182">**型**</span><span class="sxs-lookup"><span data-stu-id="097dd-182">**Type**</span></span>

<span data-ttu-id="097dd-183">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="097dd-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="097dd-184">表示される **[フィルター** ] フライアウトで、次のフィルターから選択できます。</span><span class="sxs-lookup"><span data-stu-id="097dd-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="097dd-185">**開始時刻** と **終了時刻** (日付)</span><span class="sxs-lookup"><span data-stu-id="097dd-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="097dd-186">**標準保護または\*\*\*\*厳密な保護**</span><span class="sxs-lookup"><span data-stu-id="097dd-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="097dd-187">結果を .csv ファイルにエクスポートするには、[エクスポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="097dd-187">To export the results to a .csv file, click **Export**.</span></span>

![Configuration Analyzer の構成ドリフト分析と履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)