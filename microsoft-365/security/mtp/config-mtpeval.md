---
title: 試用版ラボ環境用の Microsoft 脅威保護の柱を構成する
description: Microsoft の脅威保護の柱、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、および Microsoft Defender ATP を試用している環境をテストする
keywords: microsoft threat Protection の試用版、Microsoft Threat Protection 試用版の構成、microsoft threat Protection の構成、Microsoft Threat protection の柱の構成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049511"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="439cb-104">試用版ラボ環境用に Microsoft Threat Protection の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="439cb-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="439cb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="439cb-105">**Applies to:**</span></span>
- <span data-ttu-id="439cb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="439cb-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="439cb-107">Microsoft の脅威保護の試用ラボ環境を作成して展開することは、3つのフェーズのプロセスです。</span><span class="sxs-lookup"><span data-stu-id="439cb-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護のテスト環境を準備する" />
      <br/><span data-ttu-id="439cb-109">フェーズ 1: 準備</a></span><span class="sxs-lookup"><span data-stu-id="439cb-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護のテスト環境をセットアップする" />
      <br/><span data-ttu-id="439cb-111">フェーズ 2: セットアップ</a></span><span class="sxs-lookup"><span data-stu-id="439cb-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Microsoft の脅威保護試用版ラボ環境およびオンボードエンドポイントの各 Microsoft 脅威保護の柱を構成する" />
      <br/><span data-ttu-id="439cb-113">フェーズ 3: 構成 & オンボード</a></span><span class="sxs-lookup"><span data-stu-id="439cb-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="439cb-114">現在、構成段階になっています。</span><span class="sxs-lookup"><span data-stu-id="439cb-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="439cb-115">正常な展開には、準備が重要です。</span><span class="sxs-lookup"><span data-stu-id="439cb-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="439cb-116">この記事では、Microsoft Defender ATP を展開するための準備として考慮する必要があるポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="439cb-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="439cb-117">Microsoft Threat Protection の柱</span><span class="sxs-lookup"><span data-stu-id="439cb-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="439cb-118">Microsoft の脅威保護は、4つの柱から構成されます。</span><span class="sxs-lookup"><span data-stu-id="439cb-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="439cb-119">1つの柱がネットワーク組織のセキュリティに価値を提供していますが、4つの Microsoft 脅威保護の柱を有効にすることで、組織は最大の価値を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="439cb-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![イメージ of_page](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="439cb-121">このセクションでは、以下を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="439cb-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="439cb-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="439cb-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="439cb-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="439cb-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="439cb-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="439cb-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="439cb-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="439cb-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="439cb-126">Office 365 Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="439cb-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="439cb-127">Office 365 Advanced Threat Protection を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="439cb-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="439cb-128">これらの設定の一部を決定するのに役立つ、 *Office 365 Advanced Threat Protection 推奨構成アナライザー (ORCA)* という名前の PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="439cb-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="439cb-129">テナントで管理者として実行すると、ORCAReport はスパム対策、フィッシング、その他のメッセージの検疫設定の評価を作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="439cb-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="439cb-130">このモジュールはからhttps://www.powershellgallery.com/packages/ORCA/ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="439cb-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="439cb-131">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com/homepage) > の**脅威管理** > **ポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="439cb-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="439cb-132">![イメージ of_page](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="439cb-133">[ **ATP のフィッシング対策**] をクリックし、[ポリシーの名前と説明を**作成**して入力] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="439cb-134">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-134">Click **Next**.</span></span>
<span data-ttu-id="439cb-135">![イメージ of_page](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="439cb-136">詳細な ATP のフィッシング対策ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="439cb-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="439cb-137">**Advanced フィッシングしきい値**を**2-アグレッシブ**に変更します。</span><span class="sxs-lookup"><span data-stu-id="439cb-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="439cb-138">[**条件の追加**] ドロップダウンメニューをクリックして、ドメインを受信者のドメインとして選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="439cb-139">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-139">Click **Next**.</span></span>
<span data-ttu-id="439cb-140">![イメージ of_page](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="439cb-141">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="439cb-141">Review your settings.</span></span> <span data-ttu-id="439cb-142">[**このポリシーを作成**する] をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="439cb-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="439cb-143">![イメージ of_page](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="439cb-144">[ **Atp の安全な添付ファイル**] を選択し、[ **SharePoint、OneDrive、MICROSOFT Teams で atp を有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="439cb-145">![イメージ of_page](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="439cb-146">[+] アイコンをクリックして、新しい安全な添付ファイルポリシーを作成し、ドメインに受信者ドメインとして適用します。</span><span class="sxs-lookup"><span data-stu-id="439cb-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="439cb-147">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-147">Click **Save**.</span></span>
<span data-ttu-id="439cb-148">![イメージ of_page](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="439cb-149">次に、 **ATP の安全なリンク**ポリシーを選択し、鉛筆アイコンをクリックして既定のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="439cb-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="439cb-150">**[ユーザーが安全なリンクをクリックしたときに追跡**しない] オプションが選択されていない状態で、残りのオプションがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="439cb-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="439cb-151">詳細については、「[安全なリンク設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="439cb-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="439cb-152">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-152">Click **Save**.</span></span> 
<span data-ttu-id="439cb-153">![イメージ of_page](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="439cb-154">次に、**マルウェア対策**ポリシーを選択し、既定値を選択して、鉛筆アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="439cb-155">[**設定**] をクリックし、[はい] を選択して、**既定の通知テキストを使用**して**マルウェア検出応答**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="439cb-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="439cb-156">**一般的な添付ファイルの種類のフィルター**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="439cb-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="439cb-157">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-157">Click **Save**.</span></span>
<br><span data-ttu-id="439cb-158">![イメージ of_page](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="439cb-159">[ [Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage) > **Search** > ] [**監査ログの検索**] の順に移動し、監査をオンにします。</span><span class="sxs-lookup"><span data-stu-id="439cb-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="439cb-160">![イメージ of_page](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="439cb-161">Microsoft Defender ATP に Office 365 ATP を統合します。</span><span class="sxs-lookup"><span data-stu-id="439cb-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="439cb-162">[Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage) > の**脅威管理** > **エクスプローラー**に移動し、画面の右上にある [ **wdatp 設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="439cb-163">[Microsoft Defender ATP 接続] ダイアログボックスで、[ **WINDOWS ATP への接続**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="439cb-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="439cb-164">![イメージ of_page](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="439cb-165">Azure Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="439cb-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="439cb-166">Azure Advanced Threat Protection を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="439cb-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="439cb-167">[Microsoft 365 セキュリティセンター](https://security.microsoft.com/info) > [**その他のリソース** > ] [**Azure Advanced Threat Protection**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="439cb-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="439cb-168">![イメージ of_page](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="439cb-169">[**作成**] をクリックして、Azure Advanced Threat Protection ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="439cb-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="439cb-170">![イメージ of_page](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="439cb-171">[ **Active Directory フォレストに接続するためのユーザー名とパスワードを入力**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="439cb-172">![イメージ of_page](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="439cb-173">Active Directory のオンプレミスの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="439cb-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="439cb-174">これには、Active Directory への読み取りアクセス権を持つユーザーアカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="439cb-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="439cb-175">![イメージ of_page](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="439cb-176">次に、[**センサーのセットアップをダウンロード**し、ファイルをドメインコントローラーに転送する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="439cb-177">![イメージ of_page](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="439cb-178">Azure ATP センサーのセットアップを実行して、ウィザードの次の作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="439cb-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="439cb-179">![イメージ of_page](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="439cb-180">センサー展開の種類で [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="439cb-181">![イメージ of_page](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="439cb-182">ウィザードで次のように入力する必要がある場合は、アクセスキーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="439cb-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="439cb-183">![イメージ of_page](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="439cb-184">ウィザードにアクセスキーをコピーし、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="439cb-185">![イメージ of_page](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="439cb-186">ご使用のドメインコントローラーに Azure Advanced Threat Protection が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="439cb-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="439cb-187">![イメージ of_page](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="439cb-188">[ [Azure AZURE atp](https://go.microsoft.com/fwlink/?linkid=2040449)の設定] セクションで、[ **Windows Defender atp**] を選択し、切り替えをオンにします。</span><span class="sxs-lookup"><span data-stu-id="439cb-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="439cb-189">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-189">Click **Save**.</span></span> 
<span data-ttu-id="439cb-190">![イメージ of_page](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="439cb-191">Windows Defender ATP は、Microsoft Defender ATP として再ブランド化されています。</span><span class="sxs-lookup"><span data-stu-id="439cb-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="439cb-192">すべてのポータルにわたる Rebranding の変更は、一貫性を保つために、を展開しています。</span><span class="sxs-lookup"><span data-stu-id="439cb-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="439cb-193">Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="439cb-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="439cb-194">Microsoft Cloud App Security を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="439cb-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="439cb-195">[Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **microsoft Cloud App Security**に移動します。</span><span class="sxs-lookup"><span data-stu-id="439cb-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="439cb-196">![イメージ of_page](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="439cb-197">Azure ATP を統合するための情報プロンプトで、[ **AZURE atp データ統合の有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="439cb-198">![イメージ of_page](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="439cb-199">このプロンプトが表示されない場合は、Azure ATP データ統合が既に有効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="439cb-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="439cb-200">ただし、わからない場合は、IT 管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="439cb-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="439cb-201">[**設定**] に移動し、 **Azure ATP 統合**をオンに切り替えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="439cb-202">![イメージ of_page](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="439cb-203">新しい Azure ATP インスタンスの場合、この統合トグルは自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="439cb-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="439cb-204">次の手順に進む前に、Azure ATP 統合が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="439cb-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="439cb-205">[クラウド検出の設定] で、[ **Microsoft DEFENDER ATP 統合**] を選択し、統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="439cb-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="439cb-206">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-206">Click **Save**.</span></span>
<span data-ttu-id="439cb-207">![イメージ of_page](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="439cb-208">[クラウド検出の設定] で、[**ユーザーエンリッチメント**] を選択して、Azure Active Directory との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="439cb-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="439cb-209">![イメージ of_page](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="439cb-210">Microsoft Defender Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="439cb-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="439cb-211">Microsoft Defender Advanced Threat Protection を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="439cb-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="439cb-212">[Microsoft 365 security center](https://security.microsoft.com/info) > **More Resources** > **microsoft Defender セキュリティセンター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="439cb-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="439cb-213">[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-213">Click **Open**.</span></span>
<br><span data-ttu-id="439cb-214">![イメージ of_page](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="439cb-215">Microsoft Defender Advanced Threat Protection ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="439cb-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="439cb-216">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-216">Click **Next**.</span></span> 
<br><span data-ttu-id="439cb-217">![イメージ of_page](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="439cb-218">推奨されるデータストレージの場所、データ保持ポリシー、組織のサイズ、およびプレビュー機能のオプトインに基づいて選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="439cb-219">![イメージ of_page](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="439cb-220">その後、データ保存場所など、一部の設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="439cb-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="439cb-221">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="439cb-221">Click **Next**.</span></span> 

4. <span data-ttu-id="439cb-222">[**続行**] をクリックすると、MICROSOFT Defender ATP テナントがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="439cb-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="439cb-223">![イメージ of_page](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="439cb-224">グループポリシー、Microsoft エンドポイントマネージャー、または Microsoft Defender ATP へのローカルスクリプトを実行することにより、エンドポイントをオンボードにします。</span><span class="sxs-lookup"><span data-stu-id="439cb-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="439cb-225">簡略化のために、このガイドではローカルスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="439cb-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="439cb-226">[**パッケージのダウンロード**] をクリックし、オンボードスクリプトをエンドポイントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="439cb-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="439cb-227">![イメージ of_page](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="439cb-228">エンドポイントで、オンボードスクリプトを管理者として実行し、[Y] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="439cb-229">![イメージ of_page](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="439cb-230">おめでとうございます。第1のエンドポイントを利用しました。</span><span class="sxs-lookup"><span data-stu-id="439cb-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![イメージ of_page](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="439cb-232">コピー-Microsoft Defender ATP ウィザードから検出テストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="439cb-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="439cb-233">![イメージ of_page](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="439cb-234">PowerShell スクリプトを昇格したコマンドプロンプトにコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="439cb-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="439cb-235">![イメージ of_page](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="439cb-236">[ウィザードから**Microsoft DEFENDER ATP の使用を開始する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="439cb-237">![イメージ of_page](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="439cb-238">[Microsoft Defender セキュリティセンター](https://securitycenter.windows.com/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="439cb-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="439cb-239">[**設定**] に移動し、[**拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="439cb-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="439cb-240">![イメージ of_page](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="439cb-241">**Azure Advanced Threat Protection**との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="439cb-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="439cb-242">![イメージ of_page](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="439cb-243">**Office 365 の脅威インテリジェンス**との統合をオンにします。</span><span class="sxs-lookup"><span data-stu-id="439cb-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="439cb-244">![イメージ of_page](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="439cb-245">**Microsoft Cloud App Security**との統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="439cb-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="439cb-246">![イメージ of_page](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="439cb-247">下にスクロールして [**保存の設定**] をクリックし、新しい統合を確認します。</span><span class="sxs-lookup"><span data-stu-id="439cb-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="439cb-248">![イメージ of_page](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="439cb-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="439cb-249">次の手順</span><span class="sxs-lookup"><span data-stu-id="439cb-249">Next steps</span></span>
<span data-ttu-id="439cb-250">[Microsoft の脅威保護を有効](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service)にしてから、[テストの警告を生成](generate-test-alert.md)します。</span><span class="sxs-lookup"><span data-stu-id="439cb-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
