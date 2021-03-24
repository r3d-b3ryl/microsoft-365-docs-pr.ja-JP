---
title: エンタープライズ テスト環境向け Microsoft 365 の Microsoft 365 セキュリティの強化
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテスト ラボ ガイドを使用して、Microsoft 365 のエンタープライズ テスト環境用の追加の Microsoft 365 セキュリティ設定を有効にします。
ms.openlocfilehash: 186452396af4227a94a7f6cd0fa0109e9d6a7e17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051272"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ced17-103">エンタープライズ テスト環境向け Microsoft 365 の Microsoft 365 セキュリティの強化</span><span class="sxs-lookup"><span data-stu-id="ced17-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ced17-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境の Microsoft 365 でのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="ced17-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ced17-105">この記事の手順では、エンタープライズ テスト環境向け Microsoft 365 のセキュリティを強化するために、追加の Microsoft 365 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ced17-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ced17-107">[ここ](../downloads/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ced17-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ced17-108">フェーズ 1: エンタープライズ テスト環境向け Microsoft 365 を構築する</span><span class="sxs-lookup"><span data-stu-id="ced17-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ced17-109">最小限の要件で Microsoft 365 セキュリティを軽量な方法で構成する場合は、「Lightweight base [configuration」の手順に従ってください](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="ced17-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ced17-110">シミュレートされたエンタープライズで強化された Microsoft 365 セキュリティを構成する場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="ced17-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ced17-111">Microsoft 365 セキュリティの強化をテストするには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="ced17-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ced17-112">これはオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。</span><span class="sxs-lookup"><span data-stu-id="ced17-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="ced17-113">フェーズ 2: 強化された Microsoft 365 セキュリティを構成する</span><span class="sxs-lookup"><span data-stu-id="ced17-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="ced17-114">このフェーズでは、エンタープライズ テスト環境向け Microsoft 365 の Microsoft 365 セキュリティの強化を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="ced17-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="ced17-115">詳細と設定については、「セキュリティ強化 [のためにテナントを構成する」を参照してください](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。</span><span class="sxs-lookup"><span data-stu-id="ced17-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="ced17-116">最新の認証をサポートしないアプリをブロックする SharePoint Online を構成する</span><span class="sxs-lookup"><span data-stu-id="ced17-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="ced17-117">最新の認証をサポートしていないアプリには、Microsoft 365 サブスクリプションとそのデジタル資産をセキュリティで保護する重要な要素である ID とデバイス アクセス構成を適用できません。 [](../security/defender-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="ced17-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="ced17-118">Microsoft 365 管理センター ( ) に移動し、グローバル管理者アカウントを使用して Microsoft 365 テスト ラボ サブスクリプション [https://portal.microsoft.com](https://portal.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ced17-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="ced17-119">軽量の Microsoft 365 テスト環境を使用している場合は、ローカル コンピューターからサインインします。</span><span class="sxs-lookup"><span data-stu-id="ced17-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="ced17-120">シミュレートされたエンタープライズ Microsoft 365 テスト環境を使用している場合は [、Azure portal](https://portal.azure.com) を使用して CLIENT1 仮想マシンに接続し、CLIENT1 からサインインします。</span><span class="sxs-lookup"><span data-stu-id="ced17-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="ced17-121">新しい **[Microsoft 365 管理** センター] タブの左側のナビゲーション ウィンドウ **の** [管理センター] で **、[SharePoint] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="ced17-122">新しい **[SharePoint 管理センター] タブで** 、[ポリシー] **>をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="ced17-123">[ **モダン認証をサポートしないアプリ] をクリックし**、[ **アクセスをブロック** する] を選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="ced17-124">SharePoint、OneDrive for business、および Microsoft Teams Office 365 の Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="ced17-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="ced17-125">Defender for Office 365 for SharePoint、OneDrive、および Microsoft Teams は、悪意のあるファイルを誤って共有する組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="ced17-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="ced17-126">コンプライアンス センターの [セキュリティ &に移動し](https://protection.office.com) 、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ced17-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="ced17-127">左側のナビゲーション ウィンドウの [脅威の管理]**で、[ポリシー**] をクリックし、[安全な添付ファイル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="ced17-128">**[SharePoint、OneDrive、および Microsoft Teams のファイルを保護する] の下に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="ced17-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="ced17-129">**[SharePoint、OneDrive、および Microsoft Teams** の ATP を有効にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ced17-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="ced17-130">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ced17-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="ced17-131">マルウェア対策を有効にする</span><span class="sxs-lookup"><span data-stu-id="ced17-131">Enable anti-malware</span></span>

<span data-ttu-id="ced17-132">マルウェアは、ウイルスとスパイウェアから構成されます。</span><span class="sxs-lookup"><span data-stu-id="ced17-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="ced17-133">ウイルスは、他のプログラムやデータに感染し、感染できるプログラムを探してコンピューター全体に蔓延します。</span><span class="sxs-lookup"><span data-stu-id="ced17-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="ced17-134">スパイウェアは、サインイン情報および個人データなどの個人情報を収集して作成者に送り返すマルウェアです。</span><span class="sxs-lookup"><span data-stu-id="ced17-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="ced17-135">Microsoft 365 には、悪意のあるソフトウェアから受信メッセージと送信メッセージを保護し、スパムから保護するのに役立つ組み込みのマルウェアおよびスパム フィルター機能があります。</span><span class="sxs-lookup"><span data-stu-id="ced17-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="ced17-136">詳細については、「スパム対策 [とマルウェア対策&を参照してください](../security/defender-365-security/anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="ced17-136">For more information, see [Anti-spam & anti-malware protection](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="ced17-137">一般的な添付ファイルの種類を持つファイルに対してマルウェア対策処理が実行されるのを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ced17-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="ced17-138">ブラウザーの [戻る] ボタンをクリックして、[ポリシー] ページに **戻** ります。</span><span class="sxs-lookup"><span data-stu-id="ced17-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="ced17-139">[マルウェア **対策] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="ced17-140">Default という名前のポリシーを **ダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="ced17-141">[マルウェア対策 **ポリシー] ウィンドウで、[** 設定] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="ced17-142">[共通 **の添付ファイルの種類] フィルターで**、[オン] **を** 選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="ced17-143">フェーズ 3: セキュリティ ダッシュボードを調べる</span><span class="sxs-lookup"><span data-stu-id="ced17-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="ced17-144">Microsoft 365 の脅威管理は、組織のデータへのモバイル デバイス アクセスを制御および管理し、データ損失から組織を保護し、悪意のあるソフトウェアやスパムから受信および送信メッセージを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ced17-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="ced17-145">また、脅威管理を使用して、ドメインの評判を保護し、送信者がドメインからアカウントを悪意を持ってスプーフィングするかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ced17-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="ced17-146">セキュリティ ダッシュボードを表示するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="ced17-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="ced17-147">必要に応じて、コンプライアンス センターの [セキュリティ &に移動](https://protection.office.com) し、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ced17-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="ced17-148">左側のナビゲーション ウィンドウの [脅威の管理] **で、[ダッシュボード**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="ced17-149">ダッシュボードのすべてのカードを詳しくは、提供された情報を理解してください。</span><span class="sxs-lookup"><span data-stu-id="ced17-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="ced17-150">詳細については、「セキュリティ ダッシュボード [」を参照してください](../security/defender-365-security/security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="ced17-150">For more information, see [Security Dashboard](../security/defender-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="ced17-151">フェーズ 4: Microsoft Secure Score を調べる</span><span class="sxs-lookup"><span data-stu-id="ced17-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="ced17-152">Microsoft Secure Score は、サブスクリプションで利用可能な機能に対する現在のレベルを示す、セキュリティの姿勢を数値で示します。</span><span class="sxs-lookup"><span data-stu-id="ced17-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="ced17-153">また、スコアを向上させるために実行できる改善アクションの一覧も表示されます。</span><span class="sxs-lookup"><span data-stu-id="ced17-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="ced17-154">ブラウザーで新しいタブを作成し [、Microsoft 365](https://security.microsoft.com/)セキュリティ センターに移動し、[セキュリティで保護されたスコア] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ced17-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="ced17-155">[概要 **] タブ**  で、現在の Secure Score と、それがグローバル平均とサブスクリプションと同じ数のライセンスと比較する方法をメモします。</span><span class="sxs-lookup"><span data-stu-id="ced17-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="ced17-156">[改善アクション **] タブ** で、スコアを上げするために実行できるアクションの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="ced17-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="ced17-157">詳細については [、「Microsoft Secure Score」を参照してください](../security/defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="ced17-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ced17-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="ced17-158">Next steps</span></span>

<span data-ttu-id="ced17-159">テスト環境 [の追加情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ced17-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ced17-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="ced17-160">See also</span></span>

[<span data-ttu-id="ced17-161">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="ced17-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ced17-162">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="ced17-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ced17-163">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="ced17-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)