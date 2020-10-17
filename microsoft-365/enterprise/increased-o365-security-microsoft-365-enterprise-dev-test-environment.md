---
title: Microsoft 365 for enterprise テスト環境の Microsoft 365 セキュリティの強化
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
description: このテストラボガイドを使用して、その他の Microsoft 365 セキュリティ設定を Microsoft 365 for enterprise テスト環境に対して有効にします。
ms.openlocfilehash: 7c3300111f5999714b87a176087207a1651cdcaf
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487402"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fc7d2-103">Microsoft 365 for enterprise テスト環境の Microsoft 365 セキュリティの強化</span><span class="sxs-lookup"><span data-stu-id="fc7d2-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fc7d2-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="fc7d2-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="fc7d2-105">この記事の手順に従って、microsoft 365 for enterprise テスト環境のセキュリティを強化するために、その他の Microsoft 365 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="fc7d2-107">[ここ](../downloads/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fc7d2-108">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="fc7d2-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fc7d2-109">最小要件での軽量な方法で、強化された Microsoft 365 セキュリティを構成するだけの場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fc7d2-110">シミュレートされたエンタープライズで、強化された Microsoft 365 セキュリティを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc7d2-111">Microsoft 365 セキュリティのテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズテスト環境を必要としません。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="fc7d2-112">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="fc7d2-113">フェーズ 2: Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="fc7d2-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="fc7d2-114">このフェーズでは、エンタープライズテスト環境に microsoft 365 365 セキュリティを強化することができます。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="fc7d2-115">その他の詳細と設定については、「 [Configure your tenant for security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="fc7d2-116">先進認証をサポートしていないアプリをブロックするように SharePoint Online を構成する</span><span class="sxs-lookup"><span data-stu-id="fc7d2-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="fc7d2-117">モダン認証をサポートしていないアプリには、 [id とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md) を適用できません。これは、Microsoft 365 サブスクリプションとそのデジタル資産をセキュリティ保護するための重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="fc7d2-118">Microsoft 365 管理センター () に移動 [https://portal.microsoft.com](https://portal.microsoft.com) し、全体管理者アカウントを使用して microsoft 365 テストラボサブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="fc7d2-119">ライトウェイトの Microsoft 365 テスト環境を使用している場合は、ローカルコンピューターからサインインします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="fc7d2-120">シミュレートされたエンタープライズ Microsoft 365 テスト環境を使用している場合は、 [Azure portal](https://portal.azure.com) を使用して client1 仮想マシンに接続し、client1 からサインインします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="fc7d2-121">新しい **Microsoft 365 管理センター** のタブで、左側のナビゲーションウィンドウの [ **管理センター** ] の下にある [ **SharePoint**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="fc7d2-122">[新しい **SharePoint 管理センター** ] タブで、[ **ポリシー > アクセス制御**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="fc7d2-123">[ **モダン認証をサポートしていないアプリ**] をクリックし、[ **アクセスをブロック**する] を選択して、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="fc7d2-124">SharePoint、OneDrive for Business、Microsoft Teams の Advanced Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="fc7d2-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="fc7d2-125">Office 365 Advanced Threat Protection (ATP) for SharePoint、OneDrive、Microsoft Teams は、悪意のあるファイルを誤って共有することから組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="fc7d2-126">[セキュリティ & コンプライアンスセンター](https://protection.office.com)に移動し、全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="fc7d2-127">左側のナビゲーションウィンドウで、[ **脅威の管理**] の下の [ **ポリシー**] をクリックし、[ATP の **安全な添付ファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="fc7d2-128">[ **SharePoint、OneDrive、Microsoft Teams のファイルを保護**する] で。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="fc7d2-129">[ **SharePoint、OneDrive、Microsoft Teams に対して ATP を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="fc7d2-130">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="fc7d2-131">マルウェア対策を有効にする</span><span class="sxs-lookup"><span data-stu-id="fc7d2-131">Enable anti-malware</span></span>

<span data-ttu-id="fc7d2-132">マルウェアは、ウイルスとスパイウェアから構成されます。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="fc7d2-133">ウイルスは、他のプログラムやデータに感染し、感染できるプログラムを探してコンピューター全体に蔓延します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="fc7d2-134">スパイウェアは、サインイン情報および個人データなどの個人情報を収集して作成者に送り返すマルウェアです。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="fc7d2-135">Microsoft 365 には、受信および送信メッセージを悪意のあるソフトウェアから保護し、スパムから保護するのに役立つ、組み込みのマルウェアおよびスパムフィルタリング機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="fc7d2-136">詳細については、「 [スパム対策 & マルウェア対策保護](../security/office-365-security/anti-spam-and-anti-malware-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="fc7d2-137">一般的な添付ファイルの種類を持つファイルに対してマルウェア対策処理が実行されることを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="fc7d2-138">ブラウザーの [戻る] ボタンをクリックすると、[ **ポリシー** ] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="fc7d2-139">[ **マルウェア対策**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="fc7d2-140">**Default**という名前のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="fc7d2-141">[ **マルウェア対策ポリシー** ] ウィンドウで、[ **設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="fc7d2-142">[ **一般的な添付ファイルの種類のフィルター**] で、 **[オン] を選択し**、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="fc7d2-143">フェーズ 3: セキュリティダッシュボードを検証する</span><span class="sxs-lookup"><span data-stu-id="fc7d2-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="fc7d2-144">Microsoft 365 の脅威管理は、組織のデータへのモバイルデバイスアクセスの制御と管理、データ損失からの組織の保護、および悪意のあるソフトウェアとスパムからの受信および送信メッセージの保護に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="fc7d2-145">また、脅威管理を使用して、ドメインの評価を保護し、送信者が悪意のあるドメインからのアカウントを偽装しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="fc7d2-146">セキュリティダッシュボードを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="fc7d2-147">必要に応じて、 [セキュリティ & コンプライアンスセンター](https://protection.office.com) に移動し、全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="fc7d2-148">左側のナビゲーションウィンドウで、[ **脅威の管理**] の下の [ **ダッシュボード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="fc7d2-149">ダッシュボードのすべてのカードをよく見て、提供されている情報について理解してください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="fc7d2-150">詳細については、「 [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="fc7d2-151">フェーズ 4: Microsoft のセキュリティで保護されたスコアを調べる</span><span class="sxs-lookup"><span data-stu-id="fc7d2-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="fc7d2-152">Microsoft Secure Score は、お客様のサブスクリプションで利用可能な機能に対する現在のレベルを示す数値として、セキュリティの姿勢を示します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="fc7d2-153">また、スコアを向上させるために実行できる改善アクションの一覧も提供します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="fc7d2-154">ブラウザーで新しいタブを作成し、 [Microsoft 365 セキュリティセンター](https://security.microsoft.com/)に移動して、[ **セキュリティで保護されたスコア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="fc7d2-155">[ **概要**  ] タブで、現在のセキュリティスコアと、それが同じ数のライセンスを持つグローバルな平均およびサブスクリプションと比較されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="fc7d2-156">[ **改善アクション** ] タブで、スコアを増やすために実行できるアクションの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="fc7d2-157">詳細については、「 [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc7d2-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="fc7d2-158">Next steps</span></span>

<span data-ttu-id="fc7d2-159">テスト環境でのその他の [情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc7d2-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc7d2-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc7d2-160">See also</span></span>

[<span data-ttu-id="fc7d2-161">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="fc7d2-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fc7d2-162">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="fc7d2-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fc7d2-163">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc7d2-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
