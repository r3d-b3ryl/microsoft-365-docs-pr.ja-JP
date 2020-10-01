---
title: セキュリティポリシーの構成アナライザー
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
description: 管理者は、構成アナライザーを使用して、標準保護と厳格な保護の事前設定セキュリティポリシーの下にあるセキュリティポリシーを検索して修正する方法を学習できます。
ms.openlocfilehash: ac70b7fa2b2d0ecc65cf81ea4e5e5f2e807f2467
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326581"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="71834-103">EOP および Office 365 ATP の保護ポリシーの構成アナライザー</span><span class="sxs-lookup"><span data-stu-id="71834-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="71834-104">このトピックで説明する機能はプレビュー段階にあり、組織によっては使用できず、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71834-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="71834-105">リリーススケジュールの詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="71834-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="71834-106">セキュリティ & コンプライアンスセンターの構成アナライザーでは、設定が [既定のセキュリティポリシー](preset-security-policies.md)の標準保護と厳密な保護プロファイル設定より下にあるセキュリティポリシーを検索して修正するための一元的な場所が提供されます。</span><span class="sxs-lookup"><span data-stu-id="71834-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="71834-107">次の種類のポリシーが、構成アナライザーによって分析されます。</span><span class="sxs-lookup"><span data-stu-id="71834-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="71834-108">**Exchange Online Protection (EOP) ポリシー**: これには、exchange online メールボックスを使用する Microsoft 365 組織と、exchange online メールボックスを持たないスタンドアロン EOP 組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71834-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="71834-109">[スパム対策ポリシー](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="71834-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="71834-110">[マルウェア対策ポリシー](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="71834-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="71834-111">[EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="71834-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="71834-112">**Office 365 Advanced Threat Protection (ATP) ポリシー**: これには、Microsoft 365 E5 または OFFICE 365 ATP アドオンサブスクリプションを使用する組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71834-112">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="71834-113">ATP のフィッシング対策ポリシーには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71834-113">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="71834-114">EOP のフィッシング対策ポリシーで使用可能なものと同じ [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="71834-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="71834-115">偽装設定</span><span class="sxs-lookup"><span data-stu-id="71834-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="71834-116">高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="71834-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="71834-117">「[安全なリンク」ポリシー](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="71834-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="71834-118">[安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="71834-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="71834-119">ベースラインとして使用される **標準** および **厳密** なポリシー設定値については、「 [EOP and Office 365 ATP security の推奨設定](recommended-settings-for-eop-and-office365-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71834-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="71834-120">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="71834-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="71834-121"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="71834-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="71834-122">[ **構成アナライザー** ] ページに直接移動するには、を使用 <https://protection.office.com/configurationAnalyzer> します。</span><span class="sxs-lookup"><span data-stu-id="71834-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="71834-123">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71834-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="71834-124">この記事に記載されている手順を実行するには、事前にアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="71834-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="71834-125">構成アナライザーを使用 **して** セキュリティポリシーを更新するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71834-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="71834-126">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="71834-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="71834-127">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="71834-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="71834-128">構成アナライザーへの読み取り専用アクセスでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71834-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="71834-129">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="71834-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="71834-130">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="71834-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="71834-131">セキュリティ & コンプライアンスセンターで構成アナライザーを使用する</span><span class="sxs-lookup"><span data-stu-id="71834-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="71834-132">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **構成アナライザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="71834-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![[脅威管理ポリシー] ページの [構成アナライザー] ウィジェット \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="71834-134">構成アナライザーには、次の2つの主要なタブがあります。</span><span class="sxs-lookup"><span data-stu-id="71834-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="71834-135">**設定と推奨事項**: Standard または Strict を選択し、それらの設定を既存のセキュリティポリシーと比較します。</span><span class="sxs-lookup"><span data-stu-id="71834-135">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="71834-136">結果では、設定の値を調整して、Standard または Strict と同じレベルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="71834-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="71834-137">**構成誤差の分析と履歴**: このビューを使用すると、時間の経過とともにポリシーの変更を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="71834-137">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="71834-138">構成アナライザーの [設定] タブと [おすすめ候補] タブ</span><span class="sxs-lookup"><span data-stu-id="71834-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="71834-139">既定では、タブは標準の保護プロファイルと比較して開きます。</span><span class="sxs-lookup"><span data-stu-id="71834-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="71834-140">厳密保護プロファイルの比較に切り替えるには、[厳密な **推奨事項の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71834-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="71834-141">元に戻すには、[ **標準的な推奨事項を表示**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71834-141">To switch back, select **View Standard recommendations**.</span></span>

![構成アナライザーの [設定と推奨事項] ビュー](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="71834-143">既定では、[ **ポリシーグループ] と [設定名** ] 列には、さまざまな種類のセキュリティポリシーと、改善が必要な設定 (存在する場合) の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="71834-144">ポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71834-144">The types of policies are:</span></span>

- <span data-ttu-id="71834-145">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="71834-145">**Anti-spam**</span></span>
- <span data-ttu-id="71834-146">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="71834-146">**Anti-phishing**</span></span>
- <span data-ttu-id="71834-147">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="71834-147">**Anti-malware**</span></span>
- <span data-ttu-id="71834-148">**Atp の安全な添付ファイル** (サブスクリプションに atp が含まれている場合)</span><span class="sxs-lookup"><span data-stu-id="71834-148">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="71834-149">**Atp の安全なリンク** (サブスクリプションに atp が含まれている場合)</span><span class="sxs-lookup"><span data-stu-id="71834-149">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="71834-150">既定のビューでは、すべてが折りたたまれています。</span><span class="sxs-lookup"><span data-stu-id="71834-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="71834-151">各ポリシーの横に、ポリシーからの比較結果 (変更可能) と、標準または厳密な保護プロファイルの対応するポリシーの設定 (変更できない) の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="71834-152">比較している保護プロファイルについて、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="71834-153">**緑**: すべての既存ポリシーのすべての設定は、少なくとも保護プロファイルと同じセキュリティで保護されています。</span><span class="sxs-lookup"><span data-stu-id="71834-153">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="71834-154">**オレンジ**: 既存のポリシーの設定の一部は、保護プロファイルほど安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="71834-154">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="71834-155">**赤**: 既存のポリシーの設定の多くは、保護プロファイルほど安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="71834-155">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="71834-156">これは、多くのポリシーの設定のいくつか、または1つのポリシーの多くの設定の場合があります。</span><span class="sxs-lookup"><span data-stu-id="71834-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="71834-157">好ましい比較には、次のテキストが表示されます。 **すべての設定**は \<**Standard** or **Strict**\> **推奨事項**に従います。</span><span class="sxs-lookup"><span data-stu-id="71834-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="71834-158">そうしないと、変更する推奨設定の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="71834-159">[ **ポリシーグループ]/[設定名**] を展開すると、アテンションを必要とする特定の各ポリシーのすべてのポリシーと関連付けられた設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-159">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="71834-160">または、特定の種類のポリシー ( **スパム対策**など) を拡張して、注意が必要な種類のポリシーの設定のみを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="71834-160">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="71834-161">比較に改善に関する推奨策 (緑色) がない場合は、ポリシーを拡張しても何も示されません。</span><span class="sxs-lookup"><span data-stu-id="71834-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="71834-162">改善に関していくつかの推奨事項 (黄色または赤) がある場合は、注意を要する設定が表示され、対応する情報が次の列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="71834-163">注意が必要な設定の名前。</span><span class="sxs-lookup"><span data-stu-id="71834-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="71834-164">たとえば、前のスクリーンショットでは、スパム対策ポリシーの **バルクメールのしきい値** です。</span><span class="sxs-lookup"><span data-stu-id="71834-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="71834-165">**Policy**: 設定を含む影響を受けるポリシーの名前。</span><span class="sxs-lookup"><span data-stu-id="71834-165">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="71834-166">**適用**対象: 影響を受けたポリシーが適用されるユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="71834-166">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="71834-167">**現在の構成**: 設定の現在の値。</span><span class="sxs-lookup"><span data-stu-id="71834-167">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="71834-168">**最終更新**日: ポリシーが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="71834-168">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="71834-169">**推奨事項**: 標準または厳密な保護プロファイルの設定値。</span><span class="sxs-lookup"><span data-stu-id="71834-169">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="71834-170">ポリシーの設定の値を、保護プロファイルの推奨値と一致するように変更するには、[ **採用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71834-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="71834-171">変更に成功すると、「 **推奨事項**」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="71834-172">[ **更新** ] をクリックして、推奨数の削減、および結果からの特定の設定/ポリシー行の削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="71834-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="71834-173">構成アナライザーの [構成誤差の分析と履歴] タブ</span><span class="sxs-lookup"><span data-stu-id="71834-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="71834-174">このタブでは、カスタムセキュリティポリシーに加えた変更を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="71834-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="71834-175">既定では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71834-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="71834-176">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="71834-176">**Last modified**</span></span>
- <span data-ttu-id="71834-177">**更新者**</span><span class="sxs-lookup"><span data-stu-id="71834-177">**Modified by**</span></span>
- <span data-ttu-id="71834-178">**設定名**</span><span class="sxs-lookup"><span data-stu-id="71834-178">**Setting Name**</span></span>
- <span data-ttu-id="71834-179">**ポリシー**</span><span class="sxs-lookup"><span data-stu-id="71834-179">**Policy**</span></span>
- <span data-ttu-id="71834-180">**Type**</span><span class="sxs-lookup"><span data-stu-id="71834-180">**Type**</span></span>

<span data-ttu-id="71834-181">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71834-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="71834-182">表示される [ **フィルター** ] ポップアップでは、次のフィルターから選択できます。</span><span class="sxs-lookup"><span data-stu-id="71834-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="71834-183">**開始** 時刻と **終了時刻** (date)</span><span class="sxs-lookup"><span data-stu-id="71834-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="71834-184">**標準保護** または **厳密な保護**</span><span class="sxs-lookup"><span data-stu-id="71834-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="71834-185">結果を .csv ファイルにエクスポートするには、[ **エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71834-185">To export the results to a .csv file, click **Export**.</span></span>

![構成アナライザーの構成誤差分析と履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
