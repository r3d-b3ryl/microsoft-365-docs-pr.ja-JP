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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、構成アナライザーを使用して、標準保護と制限保護のプレセット セキュリティ ポリシーの下の設定を含むセキュリティ ポリシーを検索して修正する方法について学習できます。
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825775"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="a1def-103">EOP と Office 365 ATP の保護ポリシー Officeの構成アナライザー</span><span class="sxs-lookup"><span data-stu-id="a1def-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="a1def-104">このトピックで説明する機能はプレビューであり、すべての組織で利用できるものであり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1def-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="a1def-105">セキュリティ & コンプライアンス センターの Configuration Analyzer では、事前設定されたセキュリティ ポリシーの標準保護と制限保護のプロファイル設定の下に表示される設定を含むセキュリティ ポリシーを一元的に [検索して修正できます](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1def-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="a1def-106">構成アナライザーでは、以下の種類のポリシーが分析されます。</span><span class="sxs-lookup"><span data-stu-id="a1def-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="a1def-107">**Exchange Online Protection (EOP) ポリシー**: これには、Exchange Online メールボックスを使用している Microsoft 365 組織と Exchange Online メールボックスを持つスタンドアロン EOP 組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1def-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="a1def-108">[スパム対策ポリシー](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1def-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="a1def-109">[マルウェア対策ポリシー](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1def-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="a1def-110">[EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="a1def-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="a1def-111">**Office 365 Advanced Threat Protection (ATP) ポリシー**: これには、Microsoft 365 E5 または Office 365 の ATP アドオン サブスクリプションを持つ組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1def-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="a1def-112">ATP フィッシング対策ポリシーには、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1def-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="a1def-113">EOP フ [ィッシング](set-up-anti-phishing-policies.md#spoof-settings) 対策ポリシーで使用できるのと同じスプーフィング設定。</span><span class="sxs-lookup"><span data-stu-id="a1def-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="a1def-114">偽装の設定</span><span class="sxs-lookup"><span data-stu-id="a1def-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="a1def-115">高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="a1def-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="a1def-116">[安全なリンクポリシー](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)。</span><span class="sxs-lookup"><span data-stu-id="a1def-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="a1def-117">[安全な添付ファイル ポリシー](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)。</span><span class="sxs-lookup"><span data-stu-id="a1def-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="a1def-118">基準 **として** 使用 **される標準および制限の** ポリシー設定値については、EOP と [Office 365 ATP セキュリティの推奨設定に説明されています](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="a1def-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a1def-119">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a1def-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a1def-120"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1def-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a1def-121">構成アナライザーページ **に直接移動するには** 、以下を使用します <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="a1def-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="a1def-122">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1def-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a1def-123">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1def-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="a1def-124">構成アナライザ **ーを** 使用してセキュリティ ポリシーを更新するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1def-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="a1def-125">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="a1def-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="a1def-126">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="a1def-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="a1def-127">構成アナライザーに対する読み取り専用アクセスを実行するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1def-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="a1def-128">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="a1def-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="a1def-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="a1def-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="a1def-130">セキュリティ センターで構成アナライザー&使用する</span><span class="sxs-lookup"><span data-stu-id="a1def-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="a1def-131">セキュリティ/コンプライアンス センター&、脅威管理ポリシー **構成アナラ** \> **イザー** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1def-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![[脅威管理ポリシー] ページの構成アナライザー \> ウィジェット](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="a1def-133">構成アナライザーには 2 つの主なタブがあります。</span><span class="sxs-lookup"><span data-stu-id="a1def-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="a1def-134">**[設定] と推奨**事項: [標準] または [制限する] を選択し、それらの設定を既存のセキュリティ ポリシーと比較します。</span><span class="sxs-lookup"><span data-stu-id="a1def-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="a1def-135">結果の中で、設定の値を調整して、標準または高クォータと同じレベルに設定できます。</span><span class="sxs-lookup"><span data-stu-id="a1def-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="a1def-136">**構成重複分析と履歴**: このビューでは、構成アナライザーの結果に基づいてポリシーに加えた変更を一定期間で追跡できます。</span><span class="sxs-lookup"><span data-stu-id="a1def-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="a1def-137">構成アナライザーの [設定とおすすめ] タブ</span><span class="sxs-lookup"><span data-stu-id="a1def-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="a1def-138">既定では、タブは標準保護プロファイルとの比較で開かれます。</span><span class="sxs-lookup"><span data-stu-id="a1def-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="a1def-139">[フィルターする] をクリックして、[高一次的な保護プロファイル] をクリック **して、[書き込み] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1def-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="a1def-140">標準的な推奨事項の表示 **を選択して、前に戻す必要があります**。</span><span class="sxs-lookup"><span data-stu-id="a1def-140">To switch back, select **View Standard recommendations**.</span></span>

![構成アナライザーでの [設定と推奨事項] ビュー](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="a1def-142">既定では、 **ポリシー グループ/設定名** の列には、異なる種類のセキュリティ ポリシーと、改善が必要なポリシーの設定の数 (存在する場合) が折りたたまれたビューに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1def-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="a1def-143">ポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a1def-143">The types of policies are:</span></span>

- <span data-ttu-id="a1def-144">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="a1def-144">**Anti-spam**</span></span>
- <span data-ttu-id="a1def-145">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="a1def-145">**Anti-phishing**</span></span>
- <span data-ttu-id="a1def-146">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="a1def-146">**Anti-malware**</span></span>
- <span data-ttu-id="a1def-147">**ATP の安全な添付ファイル** (サブスクリプションに ATP が含まれている場合)</span><span class="sxs-lookup"><span data-stu-id="a1def-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="a1def-148">**ATP の安全なリンク** (サブスクリプションに ATP が含まれている場合)</span><span class="sxs-lookup"><span data-stu-id="a1def-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="a1def-149">既定のビューでは、すべてが折りたたされています。</span><span class="sxs-lookup"><span data-stu-id="a1def-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="a1def-150">各ポリシーの横に、ポリシーの比較結果の概要 (変更できます) と、標準または高レベルの保護プロファイル (変更することはできません) に対応するポリシーの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1def-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="a1def-151">次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1def-151">You'll see the following information:</span></span>

- <span data-ttu-id="a1def-152">**緑 : 既存**のすべてのポリシーのすべての設定は、比較する保護プロファイル以上に安全です。</span><span class="sxs-lookup"><span data-stu-id="a1def-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="a1def-153">**Amber**: 既存のポリシーの設定の数がわずかで、比較する保護プロファイルに安全でない。</span><span class="sxs-lookup"><span data-stu-id="a1def-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="a1def-154">**Red**: 既存のポリシーの設定の数が大幅にセキュアになっていないのは、その相性が安全な保護プロファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="a1def-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="a1def-155">これは、多くのポリシーの設定や、1 つのポリシー内の多くの設定にできます。</span><span class="sxs-lookup"><span data-stu-id="a1def-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="a1def-156">使い気に入りになっておりの比較を行う場合は、テキスト「すべての設定 **: 推奨事項」** \<**Standard** or **Strict**\> **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a1def-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="a1def-157">そうしないと、変更する推奨設定の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1def-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="a1def-158">ポリシー グループ/ **設定の名前を展開すると**、注意を必要とするすべてのポリシーおよび関連する設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1def-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="a1def-159">または、特定の種類のポリシー (スパム対策など) **を拡張**して、ユーザーの注意を必要とするポリシーの種類の設定だけを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a1def-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="a1def-160">比較に推奨事項が (緑) されていない場合は、ポリシーを拡張するものは何もありません。</span><span class="sxs-lookup"><span data-stu-id="a1def-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="a1def-161">改善するいくつかの推奨事項 (amber または red) がある場合、注意が必要な設定がわかり、対応する情報は次の列に示されています。</span><span class="sxs-lookup"><span data-stu-id="a1def-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="a1def-162">ユーザーの注意が必要な設定の名前。</span><span class="sxs-lookup"><span data-stu-id="a1def-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="a1def-163">たとえば、前のスクリーンショットでは、それはスパム対策ポリシー **のバルク** メールしきい値です。</span><span class="sxs-lookup"><span data-stu-id="a1def-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="a1def-164">**Policy:** 設定を含む影響を受けるポリシーの名前。</span><span class="sxs-lookup"><span data-stu-id="a1def-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="a1def-165">**適用:** 影響を受けるポリシーが適用されるユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="a1def-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="a1def-166">**現在の**構成 : 設定の現在の値。</span><span class="sxs-lookup"><span data-stu-id="a1def-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="a1def-167">**最終更新**日: ポリシーが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="a1def-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="a1def-168">**おす**すめ : 標準または [上書きの保護プロファイル] の設定値。</span><span class="sxs-lookup"><span data-stu-id="a1def-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="a1def-169">保護プロファイルの推奨値と一致するようにポリシーの設定の値を変更するには **、[Adopt] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1def-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="a1def-170">変更が成功すると、次のメッセージが表示されます: **おすすめは正しく導入されています**。</span><span class="sxs-lookup"><span data-stu-id="a1def-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="a1def-171">[ **更新]** をクリックすると、使用するおすすめ候トの数が減少し、特定の設定/ポリシー行が結果から削除されます。</span><span class="sxs-lookup"><span data-stu-id="a1def-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="a1def-172">構成ダッシュ化と構成アナライザーの [履歴] タブ</span><span class="sxs-lookup"><span data-stu-id="a1def-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="a1def-173">このタブでは、セキュリティ アナライザーの情報に基づいて、カスタム セキュリティ ポリシーに加えた変更を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="a1def-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="a1def-174">既定では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1def-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="a1def-175">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="a1def-175">**Last modified**</span></span>
- <span data-ttu-id="a1def-176">**更新者**</span><span class="sxs-lookup"><span data-stu-id="a1def-176">**Modified by**</span></span>
- <span data-ttu-id="a1def-177">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a1def-177">**Setting Name**</span></span>
- <span data-ttu-id="a1def-178">**ポリシー**</span><span class="sxs-lookup"><span data-stu-id="a1def-178">**Policy**</span></span>
- <span data-ttu-id="a1def-179">**型**</span><span class="sxs-lookup"><span data-stu-id="a1def-179">**Type**</span></span>

<span data-ttu-id="a1def-180">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1def-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a1def-181">表示される **[フィルター** ] ポップアップでは、次のフィルターから選択できます。</span><span class="sxs-lookup"><span data-stu-id="a1def-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="a1def-182">**開始時刻** と **終了時刻** (date)</span><span class="sxs-lookup"><span data-stu-id="a1def-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="a1def-183">**標準的** な **保護または高い保護**</span><span class="sxs-lookup"><span data-stu-id="a1def-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="a1def-184">結果を .csv ファイルにエクスポートするには、[エクスポート] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a1def-184">To export the results to a .csv file, click **Export**.</span></span>

![構成ダッシュの分析と Configuration Analyzer の履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
