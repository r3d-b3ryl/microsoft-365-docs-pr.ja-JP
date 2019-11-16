---
title: Microsoft 365 エンタープライズテスト環境の Microsoft 365 セキュリティの強化
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、microsoft 365 エンタープライズテスト環境で追加の Microsoft 365 セキュリティ設定を有効にします。
ms.openlocfilehash: 3173796167a0a9fb59e23ee2dc6eebf5000ed3d7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672693"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="271a3-103">Microsoft 365 エンタープライズテスト環境の Microsoft 365 セキュリティの強化</span><span class="sxs-lookup"><span data-stu-id="271a3-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="271a3-104">*このテストラボガイドは、Microsoft 365 エンタープライズテスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="271a3-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="271a3-105">この記事の手順に従って、Microsoft 365 エンタープライズテスト環境のセキュリティを強化するために、その他の Microsoft 365 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="271a3-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="271a3-107">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="271a3-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="271a3-108">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="271a3-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="271a3-109">最小要件での軽量な方法で、強化された Microsoft 365 セキュリティを構成するだけの場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="271a3-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="271a3-110">シミュレートされたエンタープライズで、強化された Microsoft 365 セキュリティを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="271a3-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="271a3-111">Microsoft 365 セキュリティのテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズテスト環境を必要としません。</span><span class="sxs-lookup"><span data-stu-id="271a3-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="271a3-112">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="271a3-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="271a3-113">フェーズ 2: Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="271a3-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="271a3-114">このフェーズでは、Microsoft 365 エンタープライズテスト環境に対して、強化された Microsoft 365 セキュリティを有効にします。</span><span class="sxs-lookup"><span data-stu-id="271a3-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="271a3-115">その他の詳細と設定については、「 [Configure Your Office 365 tenant for security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="271a3-115">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="271a3-116">先進認証をサポートしていないアプリをブロックするように SharePoint Online を構成する</span><span class="sxs-lookup"><span data-stu-id="271a3-116">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="271a3-117">モダン認証をサポートしていないアプリには、 [id とデバイスのアクセス構成](microsoft-365-policies-configurations.md)を適用できません。これは、Microsoft 365 サブスクリプションとそのデジタル資産をセキュリティ保護するための重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="271a3-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="271a3-118">Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動し、全体管理者アカウントを使用して Office 365 テストラボサブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="271a3-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="271a3-119">ライトウェイトの Microsoft 365 テスト環境を使用している場合は、ローカルコンピューターからサインインします。</span><span class="sxs-lookup"><span data-stu-id="271a3-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="271a3-120">シミュレートされたエンタープライズ Microsoft 365 テスト環境を使用している場合は、 [Azure portal](https://portal.azure.com)を使用して client1 仮想マシンに接続し、client1 からサインインします。</span><span class="sxs-lookup"><span data-stu-id="271a3-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="271a3-121">新しい**Microsoft 365 管理センター**のタブで、[**管理センター > SharePoint**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
3. <span data-ttu-id="271a3-122">[新しい**SharePoint 管理センター** ] タブで、[**アクセス制御**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="271a3-123">**モダン認証をサポートしていないアプリ**の下で、[**ブロック**] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="271a3-124">SharePoint、OneDrive for Business、Microsoft Teams の Advanced Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="271a3-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="271a3-125">Office 365 Advanced Threat Protection (ATP) for SharePoint、OneDrive、Microsoft Teams は、悪意のあるファイルを誤って共有することから組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="271a3-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="271a3-126">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)に移動し、全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="271a3-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="271a3-127">左側のナビゲーションウィンドウで、[**脅威の管理**] の下の [**ポリシー > 安全な添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="271a3-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="271a3-128">**[SharePoint、OneDrive、および Microsoft Teams に対して ATP を有効にする]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="271a3-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="271a3-129">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="271a3-130">マルウェア対策を有効にする</span><span class="sxs-lookup"><span data-stu-id="271a3-130">Enable anti-malware</span></span>

<span data-ttu-id="271a3-131">マルウェアは、ウイルスとスパイウェアから構成されます。</span><span class="sxs-lookup"><span data-stu-id="271a3-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="271a3-132">ウイルスは、他のプログラムやデータに感染し、感染できるプログラムを探してコンピューター全体に蔓延します。</span><span class="sxs-lookup"><span data-stu-id="271a3-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="271a3-133">スパイウェアは、サインイン情報および個人データなどの個人情報を収集して作成者に送り返すマルウェアです。</span><span class="sxs-lookup"><span data-stu-id="271a3-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="271a3-134">Office 365 には、受信および送信メッセージを悪意のあるソフトウェアから保護し、スパムから保護するのに役立つ、組み込みのマルウェアおよびスパムフィルタリング機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="271a3-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="271a3-135">詳細については、「 [Office のスパム対策 & マルウェア対策保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)」を参照してください365</span><span class="sxs-lookup"><span data-stu-id="271a3-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="271a3-136">一般的な添付ファイルの種類を持つファイルに対してマルウェア対策処理が実行されることを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="271a3-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="271a3-137">ブラウザーの [戻る] ボタンをクリックすると、[**ポリシー** ] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="271a3-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="271a3-138">[**マルウェア対策**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="271a3-139">**Default**という名前のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="271a3-140">[**マルウェア対策ポリシー** ] ウィンドウで、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="271a3-141">[**一般的な添付ファイルの種類のフィルター**] で、[ **> 保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="271a3-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-the-threat-management-dashboard"></a><span data-ttu-id="271a3-142">フェーズ 3: 脅威管理ダッシュボードを調べる</span><span class="sxs-lookup"><span data-stu-id="271a3-142">Phase 3: Examine the threat management dashboard</span></span>

<span data-ttu-id="271a3-143">Office 365 の脅威管理は、組織のデータへのモバイルデバイスアクセスの制御と管理、データ損失からの組織の保護、および悪意のあるソフトウェアとスパムからの受信および送信メッセージの保護に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="271a3-143">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="271a3-144">また、脅威管理を使用して、ドメインの評価を保護し、送信者が悪意のあるドメインからのアカウントを偽装しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="271a3-144">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="271a3-145">詳細については、「 [Microsoft 365 セキュリティセンターの脅威管理](https://docs.microsoft.com/office365/securitycompliance/threat-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="271a3-145">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="271a3-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="271a3-146">Next steps</span></span>

<span data-ttu-id="271a3-147">これらの設定を運用環境で構成する情報およびリンクについては、**情報保護**フェーズの「 [365 Microsoft のセキュリティを構成](infoprotect-configure-increased-security-office-365.md)する」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="271a3-147">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="271a3-148">テスト環境でのその他の[情報保護](m365-enterprise-test-lab-guides.md#information-protection)機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="271a3-148">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="271a3-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="271a3-149">See also</span></span>

[<span data-ttu-id="271a3-150">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="271a3-150">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="271a3-151">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="271a3-151">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="271a3-152">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="271a3-152">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

