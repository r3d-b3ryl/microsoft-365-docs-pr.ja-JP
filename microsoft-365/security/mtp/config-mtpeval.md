---
title: 試用ラボまたはパイロット環境用に Microsoft 365 Defender 柱を構成する
description: 試用ラボやパイロット環境では、microsoft Defender for Office 365、Id 用 microsoft Defender、Id、microsoft Cloud App Security、エンドポイントの Microsoft defender などの Microsoft 365 Defender 柱を構成します。
keywords: Microsoft の脅威保護の評価を構成する、Microsoft の脅威保護の評価の構成、Microsoft の脅威保護パイロットプロジェクトの構成、Microsoft の脅威保護の柱の構成、Microsoft Threat Protection の柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131299"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="82b2c-104">試用ラボまたはパイロット環境用に Microsoft 365 Defender 柱を構成する</span><span class="sxs-lookup"><span data-stu-id="82b2c-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="82b2c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="82b2c-105">**Applies to:**</span></span>
- <span data-ttu-id="82b2c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82b2c-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="82b2c-107">Microsoft 365 Defender 試用ラボまたはパイロット環境を作成して展開するには、3つのフェーズからなるプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="82b2c-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="82b2c-108">[![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="82b2c-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="82b2c-109">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="82b2c-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="82b2c-110">[![フェーズ 2: セットアップ](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="82b2c-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="82b2c-111">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="82b2c-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![フェーズ 3: オンボード](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="82b2c-113">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="82b2c-113">Phase 3: Onboard</span></span> | <span data-ttu-id="82b2c-114">[![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="82b2c-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="82b2c-115">パイロットプレイブックに戻る</span><span class="sxs-lookup"><span data-stu-id="82b2c-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="82b2c-116">*ここでは、*</span><span class="sxs-lookup"><span data-stu-id="82b2c-116">*You are here!*</span></span> | |

<span data-ttu-id="82b2c-117">現在、構成段階になっています。</span><span class="sxs-lookup"><span data-stu-id="82b2c-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="82b2c-118">正常な展開には、準備が重要です。</span><span class="sxs-lookup"><span data-stu-id="82b2c-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="82b2c-119">この記事では、エンドポイントの Microsoft Defender を展開するための準備として考慮する必要があるポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="82b2c-120">Microsoft 365 Defender 柱</span><span class="sxs-lookup"><span data-stu-id="82b2c-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="82b2c-121">Microsoft 365 Defender は、4つの柱から構成されています。</span><span class="sxs-lookup"><span data-stu-id="82b2c-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="82b2c-122">1つの柱は、既にネットワーク組織のセキュリティに価値を提供していますが、4つの Microsoft 365 Defender 柱を有効にすることで、組織にとって最大の価値を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![画像 of_Microsoft ユーザーの場合は 365 Defender ソリューション、エンドポイントの場合は microsoft defender、エンドポイントの場合は microsoft defender、クラウドアプリの場合は microsoft Cloud App Security、データについては Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="82b2c-124">このセクションでは、以下を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="82b2c-125">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="82b2c-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="82b2c-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="82b2c-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="82b2c-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="82b2c-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="82b2c-128">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="82b2c-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="82b2c-129">Microsoft Defender for Office 365 を構成する</span><span class="sxs-lookup"><span data-stu-id="82b2c-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="82b2c-130">Office 365 の Defender が既に有効になっている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="82b2c-131">これらの設定の一部を決定するのに役立つ、 *Office 365 Advanced Threat Protection (ORCA)* という名前の PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="82b2c-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="82b2c-132">テナントで管理者として実行すると、ORCAReport はスパム対策、フィッシング、その他のメッセージの検疫設定の評価を作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="82b2c-133">このモジュールはからダウンロードでき https://www.powershellgallery.com/packages/ORCA/ ます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="82b2c-134">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com/homepage)の  >  **脅威管理**  >  **ポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターの脅威管理ポリシーページ](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="82b2c-136">[ **フィッシング対策**] をクリックし、[ポリシー名] と [説明] を選択して [ **作成** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="82b2c-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-137">Click **Next**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーのページに名前をつけることができます。](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="82b2c-139">Office 365 の Microsoft Defender で、高度なフィッシング対策ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="82b2c-140">**Advanced フィッシングしきい値** を **2-アグレッシブ** に変更します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="82b2c-141">[ **条件の追加** ] ドロップダウンメニューをクリックして、ドメインを受信者のドメインとして選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="82b2c-142">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーページで、アプリケーションの条件を追加することができます。](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="82b2c-144">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-144">Review your settings.</span></span> <span data-ttu-id="82b2c-145">[ **このポリシーを作成** する] をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-145">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーページで設定を確認し、[このポリシーの作成] ボタンをクリックします。](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="82b2c-147">[ **安全な添付ファイル** ] を選択し、[ **SharePoint、OneDrive、MICROSOFT Teams で ATP を有効にする** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & SharePoint、OneDrive、Microsoft Teams の ATP を有効にするためのコンプライアンスセンターページ](../../media/mtp-eval-36.png)

6. <span data-ttu-id="82b2c-149">[+] アイコンをクリックして、新しい安全な添付ファイルポリシーを作成し、ドメインに受信者ドメインとして適用します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="82b2c-150">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-150">Click **Save**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターページ新しい安全な添付ファイルポリシーを作成する](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="82b2c-152">次に、[ **安全なリンク** ] ポリシーを選択し、鉛筆アイコンをクリックして既定のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="82b2c-153">**[ユーザーが安全なリンクをクリックしたときに追跡** しない] オプションが選択されていない状態で、残りのオプションがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="82b2c-154">詳細については、「 [安全なリンク設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b2c-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="82b2c-155">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-155">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & コンプライアンスセンター] ページで、ユーザーが [セーフ] が選択されていないときに、オプションが追跡されないことを示します。](../../media/mtp-eval-38.png)

9. <span data-ttu-id="82b2c-157">次に、 **マルウェア対策** ポリシーを選択し、既定値を選択して、鉛筆アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="82b2c-158">[ **設定** ] をクリックし、[はい] を選択して、 **既定の通知テキストを使用** して **マルウェア検出応答** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="82b2c-159">**一般的な添付ファイルの種類のフィルター** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="82b2c-160">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-160">Click **Save**.</span></span>

    ![イメージ of_Office 365 セキュリティ & コンプライアンスセンターで、マルウェア検出応答が既定の通知で有効になっており、一般的な添付ファイルの種類フィルターが有効になっていることを示します。](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="82b2c-162">[ [Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage)]  >  **Search**  >  [**監査ログの検索**] の順に移動し、監査をオンにします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![イメージ of_Office 365 セキュリティ & コンプライアンスセンター] ページで監査ログの検索を有効にする](../../media/mtp-eval-40.png)

12. <span data-ttu-id="82b2c-164">エンドポイントの Microsoft Defender に Microsoft defender を Office 365 と統合します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="82b2c-165">[Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage)の  >  **脅威管理**  >  **エクスプローラー** に移動し、画面の右上にある **エンドポイント設定に対して Microsoft Defender** を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="82b2c-166">[エンドポイントの接続の Defender] ダイアログボックスで、[ **エンドポイントの Microsoft defender への接続**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Image of_Office 365 Security & Microsoft Defender をエンドポイント接続に対してオンにできるコンプライアンスセンターページ](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="82b2c-168">Id 用に Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="82b2c-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="82b2c-169">Id に対して Microsoft Defender が既に有効になっている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="82b2c-170">[Microsoft 365 セキュリティセンター](https://security.microsoft.com/info) > 移動して、[id] に対して [**その他のリソース**]  >  **microsoft Defender** を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![イメージ of_Microsoft 365 セキュリティセンターのページ。 Id に対して Microsoft Defender を開くオプションがあります。](../../media/mtp-eval-42.png)

2. <span data-ttu-id="82b2c-172">[ **作成** ] をクリックして、Microsoft Defender for Identity ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![イメージ of_Microsoft [Id ウィザード] ページで、[作成] ボタンをクリックする必要があります。](../../media/mtp-eval-43.png)

3. <span data-ttu-id="82b2c-174">[ **Active Directory フォレストに接続するためのユーザー名とパスワードを入力** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Id ウェルカムページのイメージ of_Microsoft Defender](../../media/mtp-eval-44.png)

4. <span data-ttu-id="82b2c-176">Active Directory のオンプレミスの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="82b2c-177">これには、Active Directory への読み取りアクセス権を持つユーザーアカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-177">This can be any user account that has read access to Active Directory.</span></span>

   ![イメージ of_Microsoft、資格情報を入力する必要がある Id ディレクトリサービスページの Defender](../../media/mtp-eval-45.png)

5. <span data-ttu-id="82b2c-179">次に、[ **センサーのセットアップをダウンロード** し、ファイルをドメインコントローラーに転送する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![イメージ of_Microsoft の [Id] ページで、[センサーのセットアップのダウンロード] を選択できます。](../../media/mtp-eval-46.png)

6. <span data-ttu-id="82b2c-181">Id センサーのセットアップ用に Microsoft Defender を実行し、ウィザードのフォローを開始します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Id センサーウィザードの Microsoft Defender をフォローするには、[Id] ページの [イメージ of_Microsoft Defender] をクリックします。](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="82b2c-183">センサー展開の種類で [ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-183">Click **Next** at the sensor deployment type.</span></span>

   ![イメージ of_Microsoft、次のページに移動するには [次へ] をクリックする必要がある Id ページの Defender](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="82b2c-185">ウィザードで次に入力する必要があるため、アクセスキーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Id センサーセットアップウィザードの次の Microsoft Defender で入力する必要があるアクセスキーをコピーする必要があるイメージ of_the センサーページ](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="82b2c-187">ウィザードにアクセスキーをコピーし、[ **インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![イメージ of_Microsoft の Id センサーウィザードページでアクセスキーを指定し、[インストール] ボタンをクリックする必要があります。](../../media/mtp-eval-50.png)

10. <span data-ttu-id="82b2c-189">ご使用のドメインコントローラーで Id に対して Microsoft Defender が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="82b2c-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Id センサーウィザードインストールの完了時のイメージ of_Microsoft、[完了] ボタンをクリックする必要があります。](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="82b2c-191">[ [Id 設定のための Microsoft defender](https://go.microsoft.com/fwlink/?linkid=2040449) ] セクションで、[\* \* エンドポイントの場合は \* \*] を選択し、切り替えをオンにします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="82b2c-192">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-192">Click **Save**.</span></span> 

    ![[イメージ of_the Microsoft Defender の Id 設定] ページで、エンドポイントに対して Microsoft Defender をオンに切り替える必要があります。](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="82b2c-194">Windows Defender ATP は、エンドポイントの Microsoft Defender として再度ブランド化されています。</span><span class="sxs-lookup"><span data-stu-id="82b2c-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="82b2c-195">すべてのポータルにわたる Rebranding の変更は、一貫性を保つために、を展開しています。</span><span class="sxs-lookup"><span data-stu-id="82b2c-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="82b2c-196">Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="82b2c-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="82b2c-197">Microsoft Cloud App Security を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="82b2c-198">[Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Cloud App Security** に移動します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 セキュリティセンターページには、Microsoft Cloud App card を参照して、[開く] ボタンをクリックする必要があります。](../../media/mtp-eval-53.png)

2. <span data-ttu-id="82b2c-200">Id に Microsoft Defender を統合するための情報プロンプトで、[ **id データ統合のための Microsoft defender の有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Image of_the information のメッセージを表示し、id に対して microsoft Defender を統合します。この場合は、Id データ統合のための Microsoft Defender を有効にするリンクを選択します。](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="82b2c-202">このプロンプトが表示されない場合は、Id データ統合のための Microsoft Defender が既に有効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="82b2c-203">ただし、わからない場合は、IT 管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="82b2c-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="82b2c-204">[ **設定**] に移動し、[ **id 統合のための Microsoft Defender** ] をオンにして、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![[イメージ of_the の設定] ページで、Id 統合のために Microsoft Defender をオンにする必要があります。その後、[保存] をクリックします。](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="82b2c-206">Id インスタンス用の新しい Microsoft Defender の場合、この統合トグルは自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="82b2c-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="82b2c-207">次の手順に進む前に、Id 統合のための Microsoft Defender が有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82b2c-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="82b2c-208">[クラウド検出の設定] で、 **エンドポイント統合のための Microsoft Defender** を選択し、統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="82b2c-209">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-209">Click **Save**.</span></span>

   ![Image of_the microsoft Defender for endpoint 統合のための Microsoft Defender で [承認されていないアプリをブロックする] チェックボックスがオンになっているエンドポイントページ。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="82b2c-212">[クラウド検出の設定] で、[ **ユーザーエンリッチメント**] を選択して、Azure Active Directory との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![[エンリッチメントのユーザー識別子を Azure Active Directory ユーザー名で強化する] チェックボックスがオンになっているユーザーのイメージ](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="82b2c-214">エンドポイントの Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="82b2c-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="82b2c-215">エンドポイントに対して Microsoft Defender が既に有効になっている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="82b2c-216">[Microsoft 365 security center](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Defender セキュリティセンター** に移動します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="82b2c-217">[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-217">Click **Open**.</span></span>

   ![Microsoft 365 セキュリティセンターページの [イメージ of_Microsoft Defender セキュリティセンター] オプション](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="82b2c-219">エンドポイントの Microsoft Defender ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="82b2c-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="82b2c-220">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-220">Click **Next**.</span></span> 

   ![Microsoft Defender セキュリティセンターのウェルカムウィザードページ of_the の画像](../../media/mtp-eval-59.png)

3. <span data-ttu-id="82b2c-222">推奨されるデータストレージの場所、データ保持ポリシー、組織のサイズ、およびプレビュー機能のオプトインに基づいて選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![[イメージ of_the] ページで、データストレージの国、アイテム保持ポリシー、組織のサイズを選択します。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="82b2c-225">その後、データ保存場所など、一部の設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="82b2c-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="82b2c-226">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-226">Click **Next**.</span></span> 

4. <span data-ttu-id="82b2c-227">[ **続行** ] をクリックすると、エンドポイントテナントに対して Microsoft Defender がプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![画像 of_the ページの表示 [続行] ボタンをクリックすると、クラウドインスタンスが作成されます。](../../media/mtp-eval-61.png)

5. <span data-ttu-id="82b2c-229">エンドポイントをグループポリシー、Microsoft エンドポイントマネージャー、またはエンドポイントの Microsoft Defender に対して実行することによって、エンドポイントをオンボードにします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="82b2c-230">簡略化のために、このガイドではローカルスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="82b2c-231">[ **パッケージのダウンロード** ] をクリックし、オンボードスクリプトをエンドポイントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![画像 of_page の [パッケージのダウンロード] ボタンをクリックしてオンボードスクリプトをエンドポイントまたはエンドポイントにコピーするように求めるメッセージが表示されます。](../../media/mtp-eval-62.png)

7. <span data-ttu-id="82b2c-233">エンドポイントで、オンボードスクリプトを管理者として実行し、[Y] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![イメージ of_the、オンボードスクリプトを実行し、Y を選択して続行します。](../../media/mtp-eval-63.png)

8. <span data-ttu-id="82b2c-235">おめでとうございます。第1のエンドポイントを利用しました。</span><span class="sxs-lookup"><span data-stu-id="82b2c-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![イメージ of_the、第1のエンドポイントを利用することを確認するメッセージが表示されたコマンドライン。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="82b2c-238">コピー-エンドポイントの Microsoft Defender ウィザードから検出テストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the [コピー] をクリックして、コマンドプロンプトに貼り付ける必要のある検出テストスクリプトをコピーするための検出テスト手順を実行します。](../../media/mtp-eval-65.png)

10. <span data-ttu-id="82b2c-240">PowerShell スクリプトを昇格したコマンドプロンプトにコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![イメージ of_command プロンプトに、管理者特権でのコマンドプロンプトに PowerShell スクリプトをコピーして実行します。](../../media/mtp-eval-66.png)

11. <span data-ttu-id="82b2c-242">ウィザードから [ **エンドポイントの Microsoft Defender の使用を開始** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![画像 of_the エンドポイントの Microsoft Defender の使用を開始する] をクリックする必要があるウィザードからの確認プロンプト](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="82b2c-244">[Microsoft Defender セキュリティセンター](https://securitycenter.windows.com/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b2c-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="82b2c-245">[ **設定** ] に移動し、[ **拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![イメージ of_Microsoft Defender セキュリティセンターの設定] メニューで、高度な機能を選択する必要があります。](../../media/mtp-eval-68.png)

13. <span data-ttu-id="82b2c-247">**Id の Microsoft Defender** との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能については、Microsoft Defender の Id オプションをオンにする必要があります。](../../media/mtp-eval-69.png)

14. <span data-ttu-id="82b2c-249">**Office 365 の脅威インテリジェンス** との統合をオンにします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能である Office 365 脅威インテリジェンスのオプショントグルをオンにする必要がある](../../media/mtp-eval-70.png)

15. <span data-ttu-id="82b2c-251">**Microsoft Cloud App Security** との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b2c-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能、Microsoft Cloud App Security オプショントグルをオンにする必要がある](../../media/mtp-eval-71.png)

16. <span data-ttu-id="82b2c-253">下にスクロールして [ **保存の設定** ] をクリックし、新しい統合を確認します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![クリックする必要があるイメージ of_Save の設定] ボタン](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="82b2c-255">Microsoft 365 Defender サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="82b2c-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="82b2c-256">2020年6月1日以降、対象となるすべてのテナントに対して Microsoft 365 Defender の機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="82b2c-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="82b2c-257">詳細については、 [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) の次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b2c-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="82b2c-258">[Microsoft 365 セキュリティセンター](https://security.microsoft.com/homepage)に移動します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="82b2c-259">[ **設定** ] に移動してから、[ **Microsoft 365 Defender**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="82b2c-260">Image of_Microsoft 365 Defender option のスクリーンショット (Microsoft 365 セキュリティセンターの設定ページ)</span><span class="sxs-lookup"><span data-stu-id="82b2c-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="82b2c-261">より包括的なガイダンスについては、「 [Microsoft 365 Defender を有効](mtp-enable.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b2c-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="82b2c-262">おめでとうございます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-262">Congratulations!</span></span> <span data-ttu-id="82b2c-263">Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成したばかりです。</span><span class="sxs-lookup"><span data-stu-id="82b2c-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="82b2c-264">これで、Microsoft 365 Defender ユーザーインターフェイスについて理解を深められるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b2c-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="82b2c-265">次の Microsoft 365 Defender interactive ガイドから学んだ内容を確認し、各ダッシュボードを使用して日常のセキュリティ操作タスクを行う方法について知ることができます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="82b2c-266">次に、攻撃をシミュレートし、製品間の機能を検出して通知を作成し、エンドポイントへの fileless 攻撃に自動的に応答する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82b2c-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="82b2c-267">次の手順</span><span class="sxs-lookup"><span data-stu-id="82b2c-267">Next step</span></span>
|[<span data-ttu-id="82b2c-268">アタックシミュレーションフェーズ</span><span class="sxs-lookup"><span data-stu-id="82b2c-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="82b2c-269">Microsoft 365 Defender パイロット環境のアタックシミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="82b2c-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
