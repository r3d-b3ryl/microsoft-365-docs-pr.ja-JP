---
title: Microsoft 365 Enterprise テスト環境の強化された Office 365 セキュリティ
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: その他の Office 365 のセキュリティ設定を有効にするのに Microsoft 365 エンタープライズ テスト環境に対応するこのテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869266"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="67b21-103">Microsoft 365 Enterprise テスト環境の強化された Office 365 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="67b21-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="67b21-104">この資料の手順についてで Microsoft 365 エンタープライズ テスト環境でセキュリティを強化する追加の Office 365 の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="67b21-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="67b21-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="67b21-107">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="67b21-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="67b21-108">最小要件で軽量な方法で Office 365 のセキュリティを強化を構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="67b21-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="67b21-109">シミュレートされた企業で Office 365 のセキュリティを強化を構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="67b21-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67b21-p101">Office 365 のセキュリティ強化のテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="67b21-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="67b21-112">フェーズ 2: Office 365 のセキュリティ強化の構成します。</span><span class="sxs-lookup"><span data-stu-id="67b21-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="67b21-p102">このフェーズでは、Microsoft 365 エンタープライズ テスト環境を Office 365 のセキュリティを向上させるを有効にします。追加の詳細と設定、[セキュリティ強化のため、Office 365 のテナントの構成](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="67b21-115">現代の認証をサポートしていないアプリケーションをブロックするのには SharePoint Online を構成します。</span><span class="sxs-lookup"><span data-stu-id="67b21-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="67b21-116">現代の認証をサポートしていないアプリケーションの[id とデバイスのアクセスの構成](microsoft-365-policies-configurations.md)、Microsoft 365 サブスクリプションと、デジタル資産のセキュリティ保護の重要な要素である、それらを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="67b21-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="67b21-117">Office のポータルに移動 ([https://office.com](https://office.com)) し、グローバル管理者アカウントを使用して、Office 365 の試用版サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="67b21-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="67b21-118">軽量の Microsoft 365 テスト環境を使用する場合、ローカル コンピューターからサインインします。</span><span class="sxs-lookup"><span data-stu-id="67b21-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="67b21-119">Microsoft 365 のシミュレートされたエンタープライズ テスト環境を使用する場合は、CLIENT1 バーチャル マシンに接続して、CLIENT1 からサインインし、 [Azure ポータル](https://portal.azure.com)を使用します。</span><span class="sxs-lookup"><span data-stu-id="67b21-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="67b21-120">**Microsoft 365 管理者センター** ] タブで、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="67b21-121">[新しい**Microsoft 365 管理者センター** ] タブをクリックして**管理センター > SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="67b21-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="67b21-122">[新しい**SharePoint 管理者センター** ] タブで、**アクセス制御**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="67b21-123">**現代の認証をサポートしていないアプリケーション**では、[**ブロック**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="67b21-124">脅威保護の詳細設定を有効にする) の SharePoint、ビジネス、およびマイクロソフトのチームの OneDrive</span><span class="sxs-lookup"><span data-stu-id="67b21-124">Enable Advanced Threat Protection) for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="67b21-p103">Office 365 の高度な脅威保護 (ATP) は、機能の Exchange オンライン保護 (EOP) を支援するあなたの電子メールからのマルウェアのままです。分析ツールは、Exchange 管理センター (EAC) またはセキュリティ ポリシーを作成する & ユーザーを保証するためコンプライアンス センターでは、識別できない悪意のある電子メールの添付ファイルまたはリンクのみにアクセスします。詳細については、[高度な脅威保護](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange Admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="67b21-128">[お使いのブラウザーの [ **Microsoft 365 管理センター** ] タブをクリックして**管理センター > セキュリティおよびコンプライアンスに関する**。</span><span class="sxs-lookup"><span data-stu-id="67b21-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="67b21-129">新しい**セキュリティおよびコンプライアンスに関する**タブをクリックして**脅威の管理 > ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="67b21-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="67b21-130">**ATP の安全な添付ファイル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="67b21-131">**安全な添付ファイル**のウィンドウ**SharePoint、OneDrive、およびマイクロソフトのチームの分析ツールを有効にする**を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="67b21-132">マルウェア対策を有効にします。</span><span class="sxs-lookup"><span data-stu-id="67b21-132">Enable anti-malware</span></span>

<span data-ttu-id="67b21-p104">マルウェアは、ウイルスやスパイウェアで構成されます。その他のプログラムやデータをウイルスに感染し、感染するプログラムを探してコンピューター全体にレプリケートされます。スパイウェアは、個人情報、サインイン情報などの個人データを収集し、マルウェアの作成者に送信するマルウェアを意味します。</span><span class="sxs-lookup"><span data-stu-id="67b21-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="67b21-p105">Office 365 は、組み込みのマルウェアやスパムのフィルタ リング機能が悪意のあるソフトウェアからの受信メッセージと送信メッセージを保護するため、迷惑メールから保護するためです。詳細については、 [Office 365 でのスパム対策およびマルウェア対策保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="67b21-138">マルウェア対策のことを確認するには、一般的な添付ファイルの種類を持つファイルの処理を実行しています。</span><span class="sxs-lookup"><span data-stu-id="67b21-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="67b21-139">**ポリシー**のページに戻るには、ブラウザーの [戻る] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="67b21-140">[**マルウェア対策**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="67b21-141">という名前の**既定**のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="67b21-142">**マルウェア対策ポリシー** ] ウィンドウで、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="67b21-143">**一般的な添付ファイルの種類のフィルター**] の下をクリックして**の > 保存**。</span><span class="sxs-lookup"><span data-stu-id="67b21-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="67b21-144">フェーズ 3: Office 365 のセキュリティ ツールとログを確認します。</span><span class="sxs-lookup"><span data-stu-id="67b21-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="67b21-145">このフェーズでは、セキュリティ イベントを通知して、全体的なセキュリティ体制を評価するための組み込みのサービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="67b21-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="67b21-146">脅威管理ダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="67b21-146">Threat management dashboard</span></span>

<span data-ttu-id="67b21-p106">Office 365 の脅威の管理制御し、管理を組織のデータへのモバイル デバイスへのアクセス、データの損失から組織を保護するため悪意のあるソフトウェアおよび迷惑メールからの受信メッセージと送信メッセージを保護するためにすることができます。ドメインからアカウントを管理ドメインの評判を保護するために、送信者がスプーフィング悪意を持っているかどうかを判断するのには脅威を使用します。詳細については、 [Office 365 のセキュリティとコンプライアンス センターでの脅威の管理](https://docs.microsoft.com/office365/securitycompliance/threat-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="67b21-150">Office 365 の脅威の管理ダッシュ ボードを表示するのには次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="67b21-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="67b21-151">[お使いのブラウザーの [ **Microsoft 365 管理センター** ] タブをクリックして**管理センター > セキュリティおよびコンプライアンスに関する**。</span><span class="sxs-lookup"><span data-stu-id="67b21-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="67b21-152">新しい**セキュリティおよびコンプライアンスに関する**タブをクリックして**脅威の管理 > ダッシュ ボード**。</span><span class="sxs-lookup"><span data-stu-id="67b21-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="67b21-153">新しい**ダッシュ ボード**] タブで、ブラウザーで、マルウェアの傾向、洞察、およびダッシュ ボードの他のセクションに注意してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="67b21-154">Office 365 のクラウド アプリケーションのセキュリティ ダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="67b21-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="67b21-p107">、Office 365 高度なセキュリティの管理と呼ばれていたクラウドのアプリケーションのセキュリティを office 365 では、ポリシーで監視し、調査の結果、実行可能なことができますように、Office 365 サブスクリプションの場合、不審なアクティビティの通知を作成できます。修復アクションです。詳細については、[概要の Office 365 クラウド アプリケーションのセキュリティ](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="67b21-157">[お使いのブラウザーの [ **Microsoft 365 管理センター** ] タブをクリックして**管理センター > セキュリティおよびコンプライアンスに関する**。</span><span class="sxs-lookup"><span data-stu-id="67b21-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="67b21-158">新しい**セキュリティおよびコンプライアンスに関する**タブをクリックして**警告 > アラートを高度な管理 > には、Office 365 のクラウド アプリケーションのセキュリティ**。</span><span class="sxs-lookup"><span data-stu-id="67b21-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="67b21-159">新しい**クラウド アプリケーションのセキュリティ**] タブでは、ダッシュ ボード ビューと、Office 365 サブスクリプション内でさまざまな活動を監視する既定のポリシーのリストを注意してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="67b21-160">追跡されているクラウド アプリケーションのセキュリティ活動の概要を表示するダッシュ ボードのアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="67b21-161">**調査**(眼鏡のアイコン) と、**アクティビティ ・ ログ**を最近使用した記号] の一覧およびその他のアクティビティを参照してください] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b21-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="67b21-162">セキュリティで保護されたスコア</span><span class="sxs-lookup"><span data-stu-id="67b21-162">Secure Score</span></span>

1. <span data-ttu-id="67b21-163">お使いのブラウザーで新しいタブを作成し、 **securescore.office.com**に移動します。</span><span class="sxs-lookup"><span data-stu-id="67b21-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="67b21-164">[**ダッシュ ボード] タブ**で、あなたのスコアを向上させるには、現在のセキュリティで保護されたスコアとキュー内のアクションのリストに注意してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="67b21-165">情報と実稼働環境でこれらの設定を構成するのにはリンクの**情報の保護**の段階では、[構成 Office 365 用にセキュリティを強化する](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b21-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="67b21-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="67b21-166">Next step</span></span>

<span data-ttu-id="67b21-167">追加[情報の保護](m365-enterprise-test-lab-guides.md#information-protection)機能と、テスト環境での機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="67b21-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="67b21-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="67b21-168">See also</span></span>

[<span data-ttu-id="67b21-169">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="67b21-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="67b21-170">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="67b21-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="67b21-171">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="67b21-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

