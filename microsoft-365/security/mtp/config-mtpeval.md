---
title: 試用ラボまたはパイロット環境用の Microsoft 脅威保護の柱を構成する
description: 試用ラボやパイロット環境では、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、Microsoft Defender ATP などの Microsoft 脅威保護柱を構成します。
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
ms.openlocfilehash: 7e9060c804fcdb8445c8d833d8a43dc90a738b04
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418159"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="38475-104">試用ラボまたはパイロット環境用の Microsoft 脅威保護の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="38475-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="38475-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="38475-105">**Applies to:**</span></span>
- <span data-ttu-id="38475-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="38475-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="38475-107">Microsoft の脅威保護の試用ラボまたはパイロット環境を作成して展開するには、3つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="38475-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境の準備" />
      <br/><span data-ttu-id="38475-109">フェーズ 1: 準備 </a></span><span class="sxs-lookup"><span data-stu-id="38475-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップする" />
      <br/><span data-ttu-id="38475-111">フェーズ 2: セットアップ </a></span><span class="sxs-lookup"><span data-stu-id="38475-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Microsoft の脅威保護の試用ラボまたはパイロット環境およびオンボードエンドポイントの各 Microsoft 脅威保護の柱を構成する" />
      <br/><span data-ttu-id="38475-113">フェーズ 3: 構成 & オンボード </a></span><span class="sxs-lookup"><span data-stu-id="38475-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="38475-114">現在、構成段階になっています。</span><span class="sxs-lookup"><span data-stu-id="38475-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="38475-115">正常な展開には、準備が重要です。</span><span class="sxs-lookup"><span data-stu-id="38475-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="38475-116">この記事では、Microsoft Defender ATP を展開するための準備として考慮する必要があるポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38475-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="38475-117">Microsoft Threat Protection の柱</span><span class="sxs-lookup"><span data-stu-id="38475-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="38475-118">Microsoft の脅威保護は、4つの柱から構成されます。</span><span class="sxs-lookup"><span data-stu-id="38475-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="38475-119">1つの柱がネットワーク組織のセキュリティに価値を提供していますが、4つの Microsoft 脅威保護の柱を有効にすることで、組織は最大の価値を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="38475-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="38475-120">画像 of_Microsoft ユーザーのための脅威保護ソリューション、Azure Advanced Threat Protection、エンドポイントの Microsoft Defender Advanced Threat Protection、クラウドアプリ、Microsoft Cloud App Security、およびデータについては、Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="38475-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png)

<span data-ttu-id="38475-121">このセクションでは、以下を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38475-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="38475-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="38475-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="38475-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="38475-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="38475-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="38475-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="38475-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="38475-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="38475-126">Office 365 Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="38475-126">Configure Office 365 Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="38475-127">Office 365 Advanced Threat Protection を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="38475-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="38475-128">これらの設定の一部を決定するのに役立つ、 *Office 365 Advanced Threat Protection (ORCA)* という名前の PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="38475-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="38475-129">テナントで管理者として実行すると、ORCAReport はスパム対策、フィッシング、その他のメッセージの検疫設定の評価を作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38475-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="38475-130">このモジュールはからダウンロードでき https://www.powershellgallery.com/packages/ORCA/ ます。</span><span class="sxs-lookup"><span data-stu-id="38475-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="38475-131">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com/homepage)の  >  **脅威管理**  >  **ポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="38475-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターの脅威管理ポリシーページ](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="38475-133">[ **ATP のフィッシング対策**] をクリックし、[ポリシーの名前と説明を **作成** して入力] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="38475-134">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-134">Click **Next**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーのページに名前をつけることができます。](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="38475-136">詳細な ATP のフィッシング対策ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="38475-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="38475-137">**Advanced フィッシングしきい値**を**2-アグレッシブ**に変更します。</span><span class="sxs-lookup"><span data-stu-id="38475-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="38475-138">[ **条件の追加** ] ドロップダウンメニューをクリックして、ドメインを受信者のドメインとして選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="38475-139">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-139">Click **Next**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーページで、アプリケーションの条件を追加することができます。](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="38475-141">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="38475-141">Review your settings.</span></span> <span data-ttu-id="38475-142">[ **このポリシーを作成** する] をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="38475-142">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーページで設定を確認し、[このポリシーの作成] ボタンをクリックします。](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="38475-144">[ **Atp の安全な添付ファイル** ] を選択し、[ **SharePoint、OneDrive、MICROSOFT Teams で atp を有効にする** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & SharePoint、OneDrive、Microsoft Teams の ATP を有効にするためのコンプライアンスセンターページ](../../media/mtp-eval-36.png)

6. <span data-ttu-id="38475-146">[+] アイコンをクリックして、新しい安全な添付ファイルポリシーを作成し、ドメインに受信者ドメインとして適用します。</span><span class="sxs-lookup"><span data-stu-id="38475-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="38475-147">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-147">Click **Save**.</span></span>

   ![Image of_Office 365 Security & コンプライアンスセンターページ新しい安全な添付ファイルポリシーを作成する](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="38475-149">次に、 **ATP の安全なリンク** ポリシーを選択し、鉛筆アイコンをクリックして既定のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="38475-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="38475-150">**[ユーザーが安全なリンクをクリックしたときに追跡**しない] オプションが選択されていない状態で、残りのオプションがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38475-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="38475-151">詳細については、「 [安全なリンク設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38475-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="38475-152">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-152">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & コンプライアンスセンター] ページで、ユーザーが [セーフ] が選択されていないときに、オプションが追跡されないことを示します。](../../media/mtp-eval-38.png)

9. <span data-ttu-id="38475-154">次に、 **マルウェア対策** ポリシーを選択し、既定値を選択して、鉛筆アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="38475-155">[ **設定** ] をクリックし、[はい] を選択して、 **既定の通知テキストを使用** して **マルウェア検出応答**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="38475-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="38475-156">**一般的な添付ファイルの種類のフィルター**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="38475-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="38475-157">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-157">Click **Save**.</span></span>

    ![イメージ of_Office 365 セキュリティ & コンプライアンスセンターで、マルウェア検出応答が既定の通知で有効になっており、一般的な添付ファイルの種類フィルターが有効になっていることを示します。](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="38475-159">[ [Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage)]  >  **Search**  >  [**監査ログの検索**] の順に移動し、監査をオンにします。</span><span class="sxs-lookup"><span data-stu-id="38475-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![イメージ of_Office 365 セキュリティ & コンプライアンスセンター] ページで監査ログの検索を有効にする](../../media/mtp-eval-40.png)

12. <span data-ttu-id="38475-161">Microsoft Defender ATP に Office 365 ATP を統合します。</span><span class="sxs-lookup"><span data-stu-id="38475-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="38475-162">[Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage)の  >  **脅威管理**  >  **エクスプローラー**に移動し、画面の右上にある [ **wdatp 設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="38475-163">[Microsoft Defender ATP 接続] ダイアログボックスで、[ **WINDOWS ATP への接続**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="38475-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>

    ![Image of_Office 365 Security & コンプライアンスセンター] ページで Windows Defender ATP 接続をオンにすることができます。](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="38475-165">Azure Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="38475-165">Configure Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="38475-166">Azure Advanced Threat Protection を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="38475-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>

1. <span data-ttu-id="38475-167">[Microsoft 365 セキュリティセンター](https://security.microsoft.com/info) > [**その他のリソース**] [  >  **Azure Advanced Threat Protection**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="38475-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>

   ![Image of_Microsoft 365 セキュリティセンターのページには、Azure Advanced Threat Protection を開くオプションがあります。](../../media/mtp-eval-42.png)

2. <span data-ttu-id="38475-169">[ **作成** ] をクリックして、Azure Advanced Threat Protection ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="38475-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 

   ![Image of_Azure Advanced Threat Protection ウィザードページで、[作成] ボタンをクリックする必要があります。](../../media/mtp-eval-43.png)

3. <span data-ttu-id="38475-171">[ **Active Directory フォレストに接続するためのユーザー名とパスワードを入力**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![画像 of_Azure Advanced Threat Protection のウェルカムページ](../../media/mtp-eval-44.png)

4. <span data-ttu-id="38475-173">Active Directory のオンプレミスの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="38475-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="38475-174">これには、Active Directory への読み取りアクセス権を持つユーザーアカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="38475-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Azure Advanced Threat Protection ディレクトリサービスのページで、資格情報を入力する必要があります。](../../media/mtp-eval-45.png)

5. <span data-ttu-id="38475-176">次に、[ **センサーのセットアップをダウンロード** し、ファイルをドメインコントローラーに転送する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![[イメージ of_Azure の詳細な脅威保護] ページで、ダウンロードセンサーのセットアップを選択できます。](../../media/mtp-eval-46.png)

6. <span data-ttu-id="38475-178">Azure ATP センサーのセットアップを実行して、ウィザードの次の作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="38475-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>

   ![[イメージ of_Azure の詳細な脅威保護] ページで、[次へ] をクリックして Azure ATP センサーウィザードを実行します。](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="38475-180">センサー展開の種類で [ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-180">Click **Next** at the sensor deployment type.</span></span>

   ![Image of_Azure Advanced Threat Protection ページで、[次へ] をクリックして次のページに移動します。](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="38475-182">ウィザードで次に入力する必要があるため、アクセスキーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="38475-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![次の Azure ATP センサーセットアップウィザードページで入力する必要があるアクセスキーをコピーする必要のあるイメージ of_the センサーページ](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="38475-184">ウィザードにアクセスキーをコピーし、[ **インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Azure Advanced Threat Protection Azure ATP センサーウィザードページでアクセスキーを指定し、[インストール] ボタンをクリックします。](../../media/mtp-eval-50.png)

10. <span data-ttu-id="38475-186">ご使用のドメインコントローラーに Azure Advanced Threat Protection が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="38475-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>

    ![Image of_Azure Advanced Threat Protection Azure ATP センサーウィザードインストールの完了 [完了] ボタンをクリックする必要があります。](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="38475-188">[ [Azure AZURE atp](https://go.microsoft.com/fwlink/?linkid=2040449) の設定] セクションで、[ **Windows Defender atp**] を選択し、切り替えをオンにします。</span><span class="sxs-lookup"><span data-stu-id="38475-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="38475-189">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-189">Click **Save**.</span></span> 

    ![Image of_the [Azure Azure ATP 設定] ページで、Windows Defender ATP のオン/オフを切り替える必要があります。](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="38475-191">Windows Defender ATP は、Microsoft Defender ATP として再ブランド化されています。</span><span class="sxs-lookup"><span data-stu-id="38475-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="38475-192">すべてのポータルにわたる Rebranding の変更は、一貫性を保つために、を展開しています。</span><span class="sxs-lookup"><span data-stu-id="38475-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="38475-193">Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="38475-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="38475-194">Microsoft Cloud App Security を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="38475-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="38475-195">[Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Cloud App Security**に移動します。</span><span class="sxs-lookup"><span data-stu-id="38475-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 セキュリティセンターページには、Microsoft Cloud App card を参照して、[開く] ボタンをクリックする必要があります。](../../media/mtp-eval-53.png)

2. <span data-ttu-id="38475-197">Azure ATP を統合するための情報プロンプトで、[ **AZURE atp データ統合の有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span>
  
   ![画像の of_the 情報を表示して Azure ATP を統合するためのプロンプトを表示する Azure ATP データ統合リンクを選択する必要があります。](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="38475-199">このプロンプトが表示されない場合は、Azure ATP データ統合が既に有効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="38475-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="38475-200">ただし、わからない場合は、IT 管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="38475-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="38475-201">[ **設定**] に移動し、[ **Azure ATP 統合** ] のオン/オフを切り替えて、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 

   ![[イメージ of_the の設定] ページの [Azure ATP 統合] をオンにして、[保存] をクリックします。](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="38475-203">新しい Azure ATP インスタンスの場合、この統合トグルは自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="38475-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="38475-204">次の手順に進む前に、Azure ATP 統合が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38475-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="38475-205">[クラウド検出の設定] で、[ **Microsoft DEFENDER ATP 統合**] を選択し、統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="38475-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="38475-206">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-206">Click **Save**.</span></span>

   ![Image of_the Microsoft defender atp 統合の [承認されていないアプリをブロックする] チェックボックスがオンになっている Microsoft Defender ATP ページ。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="38475-209">[クラウド検出の設定] で、[ **ユーザーエンリッチメント**] を選択して、Azure Active Directory との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="38475-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![[エンリッチメントのユーザー識別子を Azure Active Directory ユーザー名で強化する] チェックボックスがオンになっているユーザーのイメージ](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="38475-211">Microsoft Defender Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="38475-211">Configure Microsoft Defender Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="38475-212">Microsoft Defender Advanced Threat Protection を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="38475-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="38475-213">[Microsoft 365 security center](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Defender セキュリティセンター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="38475-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="38475-214">[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-214">Click **Open**.</span></span>

   ![Microsoft 365 セキュリティセンターページの [イメージ of_Microsoft Defender セキュリティセンター] オプション](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="38475-216">Microsoft Defender Advanced Threat Protection ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="38475-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="38475-217">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-217">Click **Next**.</span></span> 

   ![Microsoft Defender セキュリティセンターのウェルカムウィザードページ of_the の画像](../../media/mtp-eval-59.png)

3. <span data-ttu-id="38475-219">推奨されるデータストレージの場所、データ保持ポリシー、組織のサイズ、およびプレビュー機能のオプトインに基づいて選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![[イメージ of_the] ページで、データストレージの国、アイテム保持ポリシー、組織のサイズを選択します。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="38475-222">その後、データ保存場所など、一部の設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="38475-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="38475-223">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38475-223">Click **Next**.</span></span> 

4. <span data-ttu-id="38475-224">[ **続行** ] をクリックすると、MICROSOFT Defender ATP テナントがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="38475-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>

   ![画像 of_the ページの表示 [続行] ボタンをクリックすると、クラウドインスタンスが作成されます。](../../media/mtp-eval-61.png)

5. <span data-ttu-id="38475-226">グループポリシー、Microsoft エンドポイントマネージャー、または Microsoft Defender ATP へのローカルスクリプトを実行することにより、エンドポイントをオンボードにします。</span><span class="sxs-lookup"><span data-stu-id="38475-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="38475-227">簡略化のために、このガイドではローカルスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="38475-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="38475-228">[ **パッケージのダウンロード** ] をクリックし、オンボードスクリプトをエンドポイントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="38475-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![画像 of_page の [パッケージのダウンロード] ボタンをクリックしてオンボードスクリプトをエンドポイントまたはエンドポイントにコピーするように求めるメッセージが表示されます。](../../media/mtp-eval-62.png)

7. <span data-ttu-id="38475-230">エンドポイントで、オンボードスクリプトを管理者として実行し、[Y] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![イメージ of_the、オンボードスクリプトを実行し、Y を選択して続行します。](../../media/mtp-eval-63.png)

8. <span data-ttu-id="38475-232">おめでとうございます。第1のエンドポイントを利用しました。</span><span class="sxs-lookup"><span data-stu-id="38475-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![イメージ of_the、第1のエンドポイントを利用することを確認するメッセージが表示されたコマンドライン。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="38475-235">コピー-Microsoft Defender ATP ウィザードから検出テストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="38475-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>

   ![Image of_the [コピー] をクリックして、コマンドプロンプトに貼り付ける必要のある検出テストスクリプトをコピーするための検出テスト手順を実行します。](../../media/mtp-eval-65.png)

10. <span data-ttu-id="38475-237">PowerShell スクリプトを昇格したコマンドプロンプトにコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="38475-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![イメージ of_command プロンプトに、管理者特権でのコマンドプロンプトに PowerShell スクリプトをコピーして実行します。](../../media/mtp-eval-66.png)

11. <span data-ttu-id="38475-239">[ウィザードから **Microsoft DEFENDER ATP の使用を開始する** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>

    ![[Microsoft Defender ATP の使用開始] をクリックする必要があるウィザードからのイメージ of_the 確認プロンプト](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="38475-241">[Microsoft Defender セキュリティセンター](https://securitycenter.windows.com/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38475-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="38475-242">[ **設定** ] に移動し、[ **拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![イメージ of_Microsoft Defender セキュリティセンターの設定] メニューで、高度な機能を選択する必要があります。](../../media/mtp-eval-68.png)

13. <span data-ttu-id="38475-244">**Azure Advanced Threat Protection**との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="38475-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能、Azure Advanced Threat Protection オプションのオン/オフを切り替える必要がある](../../media/mtp-eval-69.png)

14. <span data-ttu-id="38475-246">**Office 365 の脅威インテリジェンス**との統合をオンにします。</span><span class="sxs-lookup"><span data-stu-id="38475-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能である Office 365 脅威インテリジェンスのオプショントグルをオンにする必要がある](../../media/mtp-eval-70.png)

15. <span data-ttu-id="38475-248">**Microsoft Cloud App Security**との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="38475-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能、Microsoft Cloud App Security オプショントグルをオンにする必要がある](../../media/mtp-eval-71.png)

16. <span data-ttu-id="38475-250">下にスクロールして [ **保存の設定** ] をクリックし、新しい統合を確認します。</span><span class="sxs-lookup"><span data-stu-id="38475-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![クリックする必要があるイメージ of_Save の設定] ボタン](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="38475-252">Microsoft Threat Protection を開始する</span><span class="sxs-lookup"><span data-stu-id="38475-252">Start the Microsoft Threat Protection service</span></span>

>[!NOTE]
><span data-ttu-id="38475-253">2020年6月1日以降、対象のすべてのテナントに対して Microsoft の脅威保護機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="38475-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="38475-254">詳細については、 [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) の次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38475-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="38475-255">[Microsoft 365 セキュリティセンター](https://security.microsoft.com/homepage)に移動します。</span><span class="sxs-lookup"><span data-stu-id="38475-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="38475-256">[ **設定** ] に移動し、[ **Microsoft Threat Protection**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38475-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>

![<span data-ttu-id="38475-257">Microsoft 365 セキュリティセンターの [設定] ページの [イメージ of_Microsoft 脅威保護] オプションのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="38475-257">Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="38475-258">より包括的なガイダンスについては、「 [Microsoft Threat Protection を有効](mtp-enable.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38475-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="38475-259">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="38475-259">Congratulations!</span></span> <span data-ttu-id="38475-260">Microsoft の脅威保護の試用ラボまたはパイロット環境を作成したばかりです。</span><span class="sxs-lookup"><span data-stu-id="38475-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="38475-261">これで、Microsoft の脅威保護ユーザーインターフェイスに慣れることができました。</span><span class="sxs-lookup"><span data-stu-id="38475-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="38475-262">次の Microsoft Threat Protection 対話ガイドから学んだ内容を確認し、各ダッシュボードを使用して日常のセキュリティ操作タスクを行う方法を知ることができます。</span><span class="sxs-lookup"><span data-stu-id="38475-262">See what you can learn from the following Microsoft Threat Protection interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="38475-263">次に、攻撃をシミュレートし、製品間の機能を検出して通知を作成し、エンドポイントへの fileless 攻撃に自動的に応答する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="38475-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="38475-264">次のステップ</span><span class="sxs-lookup"><span data-stu-id="38475-264">Next step</span></span>
|<span data-ttu-id="38475-265">![アタックシミュレーションフェーズ](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="38475-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="38475-266">アタックシミュレーションフェーズ</span><span class="sxs-lookup"><span data-stu-id="38475-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="38475-267">Microsoft の脅威保護パイロット環境のアタックシミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="38475-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
