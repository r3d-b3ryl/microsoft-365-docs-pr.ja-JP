---
title: 試験ラボまたはパイロット環境用に Microsoft 365 Defender の柱を構成する
description: Office 365 用の Microsoft Defender、Id 用 Microsoft Defender、Microsoft Cloud App Security、エンドポイント用 Microsoft Defender などの Microsoft 365 Defender の柱を、試験ラボまたはパイロット環境用に構成します。
keywords: Microsoft Threat Protection 試用版の構成, Microsoft Threat Protection 試用版の構成, Microsoft Threat Protection パイロット プロジェクトの構成, Microsoft Threat Protection の柱の構成, Microsoft Threat Protection の柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932240"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="9ac36-104">試験ラボまたはパイロット環境用に Microsoft 365 Defender の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="9ac36-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9ac36-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9ac36-105">**Applies to:**</span></span>
- <span data-ttu-id="9ac36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ac36-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="9ac36-107">Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成して展開するには、次の 3 段階のプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="9ac36-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="9ac36-108">[![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="9ac36-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="9ac36-109">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="9ac36-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="9ac36-110">[![フェーズ 2: セットアップ](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="9ac36-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="9ac36-111">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="9ac36-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![フェーズ 3: オンボーディング](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="9ac36-113">フェーズ 3: オンボーディング</span><span class="sxs-lookup"><span data-stu-id="9ac36-113">Phase 3: Onboard</span></span> | <span data-ttu-id="9ac36-114">[![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="9ac36-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="9ac36-115">パイロット プレイブックに戻る</span><span class="sxs-lookup"><span data-stu-id="9ac36-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="9ac36-116">*ここにいます。*</span><span class="sxs-lookup"><span data-stu-id="9ac36-116">*You are here!*</span></span> | |

<span data-ttu-id="9ac36-117">現在、構成フェーズに入っている。</span><span class="sxs-lookup"><span data-stu-id="9ac36-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="9ac36-118">展開が成功するには、準備が重要です。</span><span class="sxs-lookup"><span data-stu-id="9ac36-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="9ac36-119">この記事では、Microsoft Defender for Endpoint の展開を準備する際に考慮する必要があるポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="9ac36-120">Microsoft 365 Defender の柱</span><span class="sxs-lookup"><span data-stu-id="9ac36-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="9ac36-121">Microsoft 365 Defender は、4 つの柱で構成されています。</span><span class="sxs-lookup"><span data-stu-id="9ac36-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="9ac36-122">1 つの柱は既にネットワーク組織のセキュリティに価値を提供することができますが、4 つの Microsoft 365 Defender の柱を有効にすると、組織が最も価値を持つものになります。</span><span class="sxs-lookup"><span data-stu-id="9ac36-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![ユーザー向of_Microsoft 365 Defender ソリューション、Id 用 Microsoft Defender、エンドポイント用の Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、データ用の Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="9ac36-124">このセクションでは、次の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="9ac36-125">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9ac36-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="9ac36-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="9ac36-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="9ac36-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9ac36-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="9ac36-128">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9ac36-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="9ac36-129">Microsoft Defender を Office 365 用に構成する</span><span class="sxs-lookup"><span data-stu-id="9ac36-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="9ac36-130">Defender for Office 365 を有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="9ac36-131">これらの設定の一部を決定するのに役立つ *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* と呼ばれる PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="9ac36-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="9ac36-132">テナントで管理者として実行すると、get-ORCAReport はスパム対策、フィッシング対策、その他のメッセージ検疫設定の評価を生成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9ac36-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="9ac36-133">このモジュールは、次のリンクからダウンロードできます https://www.powershellgallery.com/packages/ORCA/ 。</span><span class="sxs-lookup"><span data-stu-id="9ac36-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="9ac36-134">コンプライアンス センター [の脅威Office 365 セキュリティ &に](https://protection.office.com/homepage)  >  **移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![コンプライアンス センターの脅威Officeポリシー ページ&_365 セキュリティ センターの画像](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="9ac36-136">[ **フィッシング対策] をクリックし、[** 作成 **]** を選択し、ポリシー名と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="9ac36-137">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-137">Click **Next**.</span></span>

   ![ポリシーに名前をOfficeできる & 365 セキュリティ センターのフィッシング対策ポリシー ページの画像](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="9ac36-139">Microsoft Defender で高度なフィッシング対策ポリシーを編集して、Office 365 に適用します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9ac36-140">高度 **なフィッシングのしきい値を** **2 - 積極的に変更します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="9ac36-141">[条件 **の追加] ドロップダウン** メニューをクリックし、受信者ドメインとしてドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="9ac36-142">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="9ac36-144">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-144">Review your settings.</span></span> <span data-ttu-id="9ac36-145">[この **ポリシーの作成] をクリックして** 確認します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-145">Click **Create this policy** to confirm.</span></span> 

   ![[_Office 365 セキュリティ & コンプライアンス センターのフィッシング対策ポリシー] ページの画像。設定を確認して、このポリシー ボタンの作成をクリックできます。](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="9ac36-147">[ **安全な添付** ファイル] を選択し **、[SharePoint、OneDrive、Microsoft Teams** の ATP を有効にする] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![SharePoint、OneDrive Office Microsoft Teams の ATP &有効にできる [_Office 365 セキュリティ/コンプライアンス センター] ページの画像](../../media/mtp-eval-36.png)

6. <span data-ttu-id="9ac36-149">[+] アイコンをクリックして新しい安全な添付ファイル ポリシーを作成し、ドメインに受信者ドメインとして適用します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="9ac36-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-150">Click **Save**.</span></span>

   ![新しい安全Officeポリシー&作成できる [_Office 365 セキュリティ/コンプライアンス センター] ページの画像](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="9ac36-152">次に、[安全な **リンク]** ポリシーを選択し、鉛筆アイコンをクリックして既定のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="9ac36-153">[ユーザーが安全 **なリンク** をクリックしても追跡しない] オプションが選択されていないのに対し、残りのオプションは選択してください。</span><span class="sxs-lookup"><span data-stu-id="9ac36-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="9ac36-154">詳細については [、「安全なリンクの設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac36-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="9ac36-155">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-155">Click **Save**.</span></span> 

   ![[安全Officeクリックしても追跡しない] オプションが選択& 365 セキュリティ センター コンプライアンス センターの画像](../../media/mtp-eval-38.png)

9. <span data-ttu-id="9ac36-157">次に、マルウェア **対策ポリシーを** 選択し、既定のポリシーを選択して、鉛筆アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="9ac36-158">[ **設定] を** クリックし、[ **はい] を選択し** 、既定の通知テキストを使用してマルウェア検出応答 **を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="9ac36-159">共通添付 **ファイルの種類フィルターを有効** にする。</span><span class="sxs-lookup"><span data-stu-id="9ac36-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="9ac36-160">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-160">Click **Save**.</span></span>

    ![[_Office 365 セキュリティ & コンプライアンス センター] ページの画像。](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="9ac36-162">コンプライアンス センター [Office監査ログ& 365](https://protection.office.com/homepage)セキュリティ センターの検索に移動し、  >    >  監査を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="9ac36-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![監査ログ検索Office有効& 365 セキュリティ センター の [コンプライアンス センター] ページの画像](../../media/mtp-eval-40.png)

12. <span data-ttu-id="9ac36-164">Microsoft Defender for Office 365 と Microsoft Defender for Endpoint を統合します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9ac36-165">Office [365 Security & Compliance Center](https://protection.office.com/homepage)Threat management Explorer に移動し、画面の右上隅にある [エンドポイントの設定] で Microsoft  >    >   **Defender** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="9ac36-166">[Defender for Endpoint 接続] ダイアログ ボックスで、[Microsoft Defender for Endpoint への接続 **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Microsoft Defender for Endpoint Office有効にできる & 365 セキュリティ/コンプライアンス センター ページの画像](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="9ac36-168">Id 用に Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="9ac36-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="9ac36-169">既に Microsoft Defender for Identity を有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="9ac36-170">Microsoft [365 セキュリティ センターに](https://security.microsoft.com/info)移動し、[> Microsoft Defender の ID に関するその他  >  **のリソース] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Id of_Microsoft Microsoft Defender を開くオプションがある [365 セキュリティ センター] ページの画像](../../media/mtp-eval-42.png)

2. <span data-ttu-id="9ac36-172">[ **作成]** をクリックして、Microsoft Defender for Identity ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![[of_Microsoftの作成] ボタンをクリックする必要がある[Id 用 Defender ウィザード] ページの画像](../../media/mtp-eval-43.png)

3. <span data-ttu-id="9ac36-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span><span class="sxs-lookup"><span data-stu-id="9ac36-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Id of_Microsoft Defender のウェルカム ページの画像](../../media/mtp-eval-44.png)

4. <span data-ttu-id="9ac36-176">Active Directory のオンプレミス資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="9ac36-177">Active Directory への読み取りアクセス権を持つ任意のユーザー アカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9ac36-177">This can be any user account that has read access to Active Directory.</span></span>

   ![資格情報of_Microsoftする必要がある [Identity Directory サービス用 Defender] ページの画像](../../media/mtp-eval-45.png)

5. <span data-ttu-id="9ac36-179">次に、[ **センサーのセットアップのダウンロード] を選択** し、ドメイン コントローラーにファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Image of_Microsoft Defender for Identity page where you can select Download Sensor Setup](../../media/mtp-eval-46.png)

6. <span data-ttu-id="9ac36-181">Microsoft Defender for Identity Sensor セットアップを実行し、ウィザードの実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![[Of_Microsoft Defender for Identity] ページの画像。次にクリックして、Microsoft Defender for Identity センサー ウィザードに従う必要があります。](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="9ac36-183">センサー **の展開の** 種類で [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-183">Click **Next** at the sensor deployment type.</span></span>

   ![次of_Microsoftページに移動するためにクリックする必要がある[Id 用 Defender] ページの画像](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="9ac36-185">ウィザードで次に入力する必要があるアクセス キーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![次of_the Microsoft Defender for Identity センサーのセットアップ ウィザード ページで入力する必要があるアクセス キーをコピーする必要がある[センサーのイメージ] ページ](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="9ac36-187">ウィザードにアクセス キーをコピーし、[インストール] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Microsoft Defender for Identity sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)

10. <span data-ttu-id="9ac36-189">これで完了です。ドメイン コントローラーで Id 用に Microsoft Defender が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="9ac36-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="9ac36-191">[Id 設定 [用 Microsoft Defender] セクション](https://go.microsoft.com/fwlink/?linkid=2040449) で、[エンドポイント用 Microsoft Defender] を選択し、トグルをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="9ac36-192">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-192">Click **Save**.</span></span> 

    ![Microsoft Defender of_theを有効にする必要がある[ID の設定] ページの画像](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="9ac36-194">Windows Defender ATP は、Microsoft Defender for Endpoint として再ブランドされました。</span><span class="sxs-lookup"><span data-stu-id="9ac36-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9ac36-195">すべてのポータルで変更の再ブランド化を行い、一貫性を確保しています。</span><span class="sxs-lookup"><span data-stu-id="9ac36-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="9ac36-196">Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="9ac36-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="9ac36-197">Microsoft Cloud App Security を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="9ac36-198">Microsoft Cloud App Security に関するその他のリソースを Microsoft [365](https://security.microsoft.com/info)  >    >  **セキュリティ センターに移動します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![[Of_Microsoft 365 セキュリティ センター] ページで Microsoft Cloud App カードを表示し、[開く] ボタンをクリックする必要がある画像](../../media/mtp-eval-53.png)

2. <span data-ttu-id="9ac36-200">Id 用 Microsoft Defender を統合する情報プロンプトで、[Id データ統合 **用に Microsoft Defender を有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Id of_the Microsoft Defender for Identity を統合する情報プロンプトが表示されます。ここで、[Id データ統合用に Microsoft Defender を有効にする] リンクを選択する必要があります。](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="9ac36-202">このプロンプトが表示されていない場合は、Microsoft Defender for Identity データ統合が既に有効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9ac36-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="9ac36-203">ただし、確認できない場合は、IT 管理者に問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ac36-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="9ac36-204">[設定] **に** 移動し **、[Id 統合用 Microsoft Defender]** トグルをオンにし、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Id 統合of_the Microsoft Defender を有効にし、[保存] をクリックする必要がある[画像の設定] ページ](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="9ac36-206">ID インスタンス用の新しい Microsoft Defender の場合、この統合トグルは自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="9ac36-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="9ac36-207">次の手順に進む前に、Id 用 Microsoft Defender の統合が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac36-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="9ac36-208">クラウド検出の設定で、 **エンドポイント統合用の Microsoft Defender** を選択し、統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="9ac36-209">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-209">Click **Save**.</span></span>

   ![[エンドポイントof_the Microsoft Defender for Endpoint の統合の下にある[非許可アプリのブロック] チェック ボックスが選択されている[エンドポイント用 Microsoft Defender] ページの画像。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="9ac36-212">[クラウド検出の設定] で、[ユーザー エン **リッチメント**] を選択し、Azure Active Directory との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![[ユーザー エンリッチメント] セクションの画像。Azure Active Directory のユーザー名を使用して検出されたユーザー識別子を強化するチェック ボックスがオン](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="9ac36-214">エンドポイント用に Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="9ac36-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="9ac36-215">Microsoft Defender for Endpoint を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="9ac36-216">Microsoft [365 セキュリティ センターの](https://security.microsoft.com/info)  >  **その** 他のリソース  >  **Microsoft Defender セキュリティ センターに移動します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="9ac36-217">[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-217">Click **Open**.</span></span>

   ![Microsoft 365 of_Microsoftページの Defender セキュリティ センター オプションの画像](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="9ac36-219">Microsoft Defender for Endpoint ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="9ac36-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="9ac36-220">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-220">Click **Next**.</span></span> 

   ![Microsoft Defender of_theウィザードページの画像](../../media/mtp-eval-59.png)

3. <span data-ttu-id="9ac36-222">優先するデータ保存場所、データ保持ポリシー、組織のサイズ、プレビュー機能のオプトインに基づいて選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![画像of_theページで、データストレージの国、アイテム保持ポリシー、組織のサイズを選択できます。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="9ac36-225">後で、データの保存場所など、一部の設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ac36-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="9ac36-226">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-226">Click **Next**.</span></span> 

4. <span data-ttu-id="9ac36-227">[ **続行]** をクリックすると、Microsoft Defender for Endpoint テナントがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="9ac36-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![クラウド of_theを作成するために [続行] ボタンをクリックするように求める画像ページ](../../media/mtp-eval-61.png)

5. <span data-ttu-id="9ac36-229">グループ ポリシー、Microsoft Endpoint Manager、またはエンドポイント用 Microsoft Defender へのローカル スクリプトを実行して、エンドポイントをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9ac36-230">わかりやすくするために、このガイドではローカル スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="9ac36-231">[ **パッケージのダウンロード]** をクリックし、オンボード スクリプトをエンドポイントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![[of_page] ボタンをクリックしてオンボード スクリプトをエンドポイントまたはエンドポイントにコピーするように求めるメッセージが表示される画像](../../media/mtp-eval-62.png)

7. <span data-ttu-id="9ac36-233">エンドポイントで、オンボード スクリプトを管理者として実行し、Y を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![オンボード of_the実行し、Y を選択して続行するコマンド ラインのイメージ](../../media/mtp-eval-63.png)

8. <span data-ttu-id="9ac36-235">これで、最初のエンドポイントがオンボードされました。</span><span class="sxs-lookup"><span data-stu-id="9ac36-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![画像of_the、最初のエンドポイントをオンボードしたという確認が表示されるコマンド ラインです。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="9ac36-238">Microsoft Defender for Endpoint ウィザードから検出テストをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9ac36-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![イメージ of_the検出テスト ステップを実行します。ここで、[コピー] をクリックして、コマンド プロンプトに貼り付ける必要がある検出テスト スクリプトをコピーする必要があります。](../../media/mtp-eval-65.png)

10. <span data-ttu-id="9ac36-240">管理者特権のコマンド プロンプトに PowerShell スクリプトをコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![管理者of_commandコマンド プロンプトに PowerShell スクリプトをコピーして実行する必要がある場所を示す画像](../../media/mtp-eval-66.png)

11. <span data-ttu-id="9ac36-242">ウィザード **から [Microsoft Defender for Endpoint の使用を** 開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![ウィザードof_the確認プロンプトが表示されます。ここで、[Microsoft Defender for Endpoint の使用を開始する] をクリックする必要があります。](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="9ac36-244">Microsoft [Defender セキュリティ センターにアクセスします](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="9ac36-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="9ac36-245">[設定] **に移動し** 、[高度な機能] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![[Of_Microsoftセキュリティ センターの設定] メニューの [高度な機能] を選択する必要がある画像](../../media/mtp-eval-68.png)

13. <span data-ttu-id="9ac36-247">Id 用 Microsoft Defender との **統合を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![イメージ of_Microsoft Defender セキュリティ センターの高度な機能、有効にする必要がある Id 用 Microsoft Defender オプションの切り替え](../../media/mtp-eval-69.png)

14. <span data-ttu-id="9ac36-249">Office **365 脅威インテリジェンスとの統合を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![有効of_Microsoft必要な 365 脅威インテリジェンス オプションOffice Defender セキュリティ センターの高度な機能の画像](../../media/mtp-eval-70.png)

15. <span data-ttu-id="9ac36-251">Microsoft Cloud **App Security との統合を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Defender of_Microsoftセンターの高度な機能、有効にする必要がある Microsoft Cloud App Security オプションの切り替えの画像](../../media/mtp-eval-71.png)

16. <span data-ttu-id="9ac36-253">下にスクロールして [ **保存] 基本設定をクリック** し、新しい統合を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![クリックof_Save必要な [基本設定] ボタンの画像](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="9ac36-255">Microsoft 365 Defender サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="9ac36-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="9ac36-256">2020 年 6 月 1 日から、Microsoft は対象となるすべてのテナントに対して Microsoft 365 Defender 機能を自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ac36-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="9ac36-257">詳細については、 [ライセンスの利用資格に関する Microsoft Tech Community の記事](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac36-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="9ac36-258">Microsoft [365 セキュリティ センターに移動します](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="9ac36-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="9ac36-259">[設定] **に移動** し **、Microsoft 365 Defender を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9ac36-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="9ac36-260">Microsoft 365 of_Microsoft設定ページの 365 Defender オプションのスクリーンショットの画像</span><span class="sxs-lookup"><span data-stu-id="9ac36-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="9ac36-261">より包括的なガイダンスについては [、「Microsoft 365 Defender を有効にする」を参照してください](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="9ac36-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="9ac36-262">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="9ac36-262">Congratulations!</span></span> <span data-ttu-id="9ac36-263">Microsoft 365 Defender 試用版ラボまたはパイロット環境が作成されました。</span><span class="sxs-lookup"><span data-stu-id="9ac36-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="9ac36-264">これで、Microsoft 365 Defender のユーザー インターフェイスについて理解することができます。</span><span class="sxs-lookup"><span data-stu-id="9ac36-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="9ac36-265">次の Microsoft 365 Defender 対話型ガイドで学習できる情報を確認し、各ダッシュボードを使用して、毎日のセキュリティ操作タスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="9ac36-266">次に、攻撃をシミュレートし、クロス製品の機能がエンドポイントに対するファイルレス攻撃を検出、作成、および自動的に対応する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9ac36-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="9ac36-267">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ac36-267">Next step</span></span>
|[<span data-ttu-id="9ac36-268">攻撃シミュレーション フェーズ</span><span class="sxs-lookup"><span data-stu-id="9ac36-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="9ac36-269">Microsoft 365 Defender パイロット環境の攻撃シミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ac36-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
