---
title: 試用版Microsoft 365 Defender環境の柱を構成する
description: 試用版Microsoft 365 Defenderパイロット環境用に、microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security、Microsoft Defender for Endpoint などのMicrosoft 365 Defender柱を構成します。
keywords: 試用版Microsoft 365 Defender構成、Microsoft 365 Defender構成、パイロット プロジェクトMicrosoft 365 Defender構成、Microsoft 365 Defender柱の構成、Microsoft 365 Defender柱
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458448"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="b3f52-104">試用版Microsoft 365 Defender環境の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="b3f52-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b3f52-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b3f52-105">**Applies to:**</span></span>
- <span data-ttu-id="b3f52-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3f52-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="b3f52-107">試用版ラボMicrosoft 365 Defenderを作成して展開するには、次の 3 段階のプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="b3f52-108">[![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="b3f52-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="b3f52-109">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="b3f52-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="b3f52-110">[![フェーズ 2: 設定](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="b3f52-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="b3f52-111">フェーズ 2: 設定</span><span class="sxs-lookup"><span data-stu-id="b3f52-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![フェーズ 3: オンボード](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="b3f52-113">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="b3f52-113">Phase 3: Onboard</span></span> | <span data-ttu-id="b3f52-114">[![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="b3f52-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="b3f52-115">パイロット プレイブックに戻る</span><span class="sxs-lookup"><span data-stu-id="b3f52-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="b3f52-116">*お前はここにいる!*</span><span class="sxs-lookup"><span data-stu-id="b3f52-116">*You are here!*</span></span> | |

<span data-ttu-id="b3f52-117">現在、構成フェーズに入っている。</span><span class="sxs-lookup"><span data-stu-id="b3f52-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="b3f52-118">展開が成功するには、準備が重要です。</span><span class="sxs-lookup"><span data-stu-id="b3f52-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="b3f52-119">この記事では、Microsoft Defender for Endpoint の展開を準備する際に考慮する必要がある点について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>

## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="b3f52-120">Microsoft 365 Defender柱</span><span class="sxs-lookup"><span data-stu-id="b3f52-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="b3f52-121">Microsoft 365 Defenderは 4 つの柱で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b3f52-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="b3f52-122">1 つの柱は既にネットワーク組織のセキュリティに価値を提供することができますが、4 つの柱を有効にすると、Microsoft 365 Defenderが最も大きな価値を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3f52-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![イメージ of_Microsoftユーザー向け 365 Defender ソリューション、Microsoft Defender for Identity、エンドポイント用 Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、データの場合は Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="b3f52-124">このセクションでは、次の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-124">This section will guide you to configure:</span></span>

- <span data-ttu-id="b3f52-125">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b3f52-125">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="b3f52-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b3f52-126">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="b3f52-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3f52-127">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b3f52-128">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b3f52-128">Microsoft Defender for Endpoint</span></span>

## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="b3f52-129">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b3f52-129">Configure Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="b3f52-130">Defender for Office 365 を既に有効にしている場合は、この手順を省略Office 365。</span><span class="sxs-lookup"><span data-stu-id="b3f52-130">Skip this step if you've already enabled Defender for Office 365.</span></span>

<span data-ttu-id="b3f52-131">これらの設定の一部を特定するのに役立つ Office 365 Advanced *Threat Protection Recommended Configuration Analyzer (ORCA)* と呼ばれる PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="b3f52-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="b3f52-132">テナントで管理者として実行すると、get-ORCAReport はスパム対策、フィッシング対策、その他のメッセージ衛生設定の評価を生成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b3f52-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="b3f52-133">このモジュールは、 からダウンロードできます https://www.powershellgallery.com/packages/ORCA/ 。</span><span class="sxs-lookup"><span data-stu-id="b3f52-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span>

1. <span data-ttu-id="b3f52-134">[コンプライアンス センター [Office 365管理&セキュリティ ポリシー](https://protection.office.com/homepage)  >  **] に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 セキュリティ & コンプライアンス センターの脅威管理ポリシー ページ](../../media/mtp-eval-32.png)

2. <span data-ttu-id="b3f52-136">[ **フィッシング対策] をクリックし**、[ポリシー **名と説明を作成** して入力する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="b3f52-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-137">Click **Next**.</span></span>

   ![ポリシーに名前Officeできる 365 セキュリティ & コンプライアンス センターのフィッシング対策ポリシー ページの画像](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="b3f52-139">Microsoft Defender で高度なフィッシング対策ポリシーを編集し、Office 365。</span><span class="sxs-lookup"><span data-stu-id="b3f52-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b3f52-140">[高度 **なフィッシングのしきい値] を** **2 - アグレッシブ に変更します**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="b3f52-141">[条件 **の追加] ドロップダウン メニュー** をクリックし、ドメインを受信者ドメインとして選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="b3f52-142">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & コンプライアンス センターのフィッシング対策ポリシー ページで、アプリケーションの条件を追加できます。](../../media/mtp-eval-34.png)

4. <span data-ttu-id="b3f52-144">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-144">Review your settings.</span></span> <span data-ttu-id="b3f52-145">[この **ポリシーの作成] をクリックして** 確認します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-145">Click **Create this policy** to confirm.</span></span>

   ![Image of_Office 365 Security & コンプライアンス センターのフィッシング対策ポリシー ページで、設定を確認し、[このポリシーの作成] ボタンをクリックします。](../../media/mtp-eval-35.png)

5. <span data-ttu-id="b3f52-147">**[セーフ添付ファイル]** を選択し、[ATP を有効にする] オプション **をSharePoint、OneDrive、Microsoft Teams** します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 セキュリティ & コンプライアンス センター] ページで、ATP を有効にし、SharePoint、OneDrive、およびMicrosoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="b3f52-149">[+] アイコンをクリックして新しい安全な添付ファイル ポリシーを作成し、ドメインに受信者ドメインとして適用します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="b3f52-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-150">Click **Save**.</span></span>

   ![Image of_Office 365 セキュリティ & コンプライアンス センター] ページで、新しい安全な添付ファイル ポリシーを作成できます](../../media/mtp-eval-37.png)

7. <span data-ttu-id="b3f52-152">次に、[リンク] セーフ **を** 選択し、鉛筆アイコンをクリックして既定のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="b3f52-153">残りのオプション **が選択** されている間は、[ユーザーが安全なリンクをクリックしても追跡しない] オプションが選択されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="b3f52-154">詳細については[セーフリンクの設定を](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3f52-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="b3f52-155">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-155">Click **Save**.</span></span>

   ![Image of_Office 365 セキュリティ & コンプライアンス センター] ページで、[ユーザーが安全をクリックしても追跡しない] オプションが選択されていないことを示します。](../../media/mtp-eval-38.png)

9. <span data-ttu-id="b3f52-157">次に、マルウェア **対策ポリシーを** 選択し、既定を選択し、鉛筆アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="b3f52-158">[マルウェア **設定]** をクリックし、[はい] を **選択し**、既定の通知テキストを使用してマルウェア検出応答 **を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="b3f52-159">[共通の **添付ファイルの種類] フィルターを有効** にする。</span><span class="sxs-lookup"><span data-stu-id="b3f52-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="b3f52-160">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-160">Click **Save**.</span></span>

    ![Image of_Office 365 Security & コンプライアンス センター] ページで、マルウェア検出応答が既定の通知でオンになっていて、一般的な添付ファイルの種類フィルターがオンになっていることを示します。](../../media/mtp-eval-39.png)

11. <span data-ttu-id="b3f52-162">コンプライアンス センター[のOffice 365監査ログ&に](https://protection.office.com/homepage)移動し、[監査  >    >  ] をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="b3f52-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![監査ログOffice有効&コンプライアンス センター ページの image of_Office 365 Security](../../media/mtp-eval-40.png)

12. <span data-ttu-id="b3f52-164">Microsoft Defender for Office 365 Microsoft Defender for Endpoint に統合します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b3f52-165">[コンプライアンス センター [Office 365セキュリティ&管理](https://protection.office.com/homepage)エクスプローラー] に移動し、画面の右上隅にある [エンドポイント設定  >    >  Microsoft Defender **for Endpoint** 設定] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="b3f52-166">[Defender for Endpoint 接続] ダイアログ ボックスで、[エンドポイント用 Microsoft Defender Connect **を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Image of_Office 365 Security & コンプライアンス センター] ページで、Microsoft Defender for Endpoint 接続をオンにできます](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="b3f52-168">Id の Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="b3f52-168">Configure Microsoft Defender for Identity</span></span>

> [!NOTE]
> <span data-ttu-id="b3f52-169">Microsoft Defender for Identity を既に有効にしている場合は、この手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="b3f52-170">[セキュリティ センター] [Microsoft 365に移動>](https://security.microsoft.com/info) Microsoft Defender for Identity の  >  **その他のリソース] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![[of_Microsoft 365 セキュリティ センター] ページで、Microsoft Defender for Identity を開くオプションがあるイメージ](../../media/mtp-eval-42.png)

2. <span data-ttu-id="b3f52-172">[作成 **] を** クリックして、Microsoft Defender for Identity ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span>

   ![[of_Microsoft作成] ボタンをクリックする必要がある [Defender for Identity ウィザード] ページのイメージ](../../media/mtp-eval-43.png)

3. <span data-ttu-id="b3f52-174">[ **ユーザー名とパスワードを指定して Active Directory フォレストに接続する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>

   ![[Id of_Microsoftのイメージ ページ] [Defender for Identity ようこそ] ページ](../../media/mtp-eval-44.png)

4. <span data-ttu-id="b3f52-176">Active Directory のオンプレミス資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="b3f52-177">これは、Active Directory への読み取りアクセス権を持つ任意のユーザー アカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3f52-177">This can be any user account that has read access to Active Directory.</span></span>

   ![資格情報of_Microsoftする必要がある [Defender for Identity Directory Services] ページのイメージ](../../media/mtp-eval-45.png)

5. <span data-ttu-id="b3f52-179">次に、[ **センサーのセットアップをダウンロードして** ドメイン コントローラーにファイルを転送する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![[of_Microsoftセンサーセットアップのダウンロード] を選択できる [Defender for Identity] ページのイメージ](../../media/mtp-eval-46.png)

6. <span data-ttu-id="b3f52-181">Microsoft Defender for Identity Sensor Setup を実行し、ウィザードの実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![[of_Microsoft Defender for Identity] ページで、Microsoft Defender for Identity センサー ウィザードの横をクリックする必要があります。](../../media/mtp-eval-47.png)

7. <span data-ttu-id="b3f52-183">センサーの **展開の** 種類で [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-183">Click **Next** at the sensor deployment type.</span></span>

   ![[of_Microsoftをクリックして次のページに移動する必要がある [Defender for Identity] ページのイメージ](../../media/mtp-eval-48.png)

8. <span data-ttu-id="b3f52-185">ウィザードで次にアクセス キーを入力する必要がある場合は、アクセス キーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![次of_the Microsoft Defender for Identity センサー セットアップ ウィザード ページで入力する必要があるアクセス キーをコピーする必要があるイメージ センサー ページ](../../media/mtp-eval-49.png)

9. <span data-ttu-id="b3f52-187">アクセス キーをウィザードにコピーし、[インストール] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-187">Copy the access key into the Wizard and click **Install**.</span></span>

   ![Image of_Microsoft Defender for Identity センサー ウィザード ページで、アクセス キーを指定し、[インストール] ボタンをクリックする必要があります。](../../media/mtp-eval-50.png)

10. <span data-ttu-id="b3f52-189">おめでとうございます、ドメイン コントローラーで Microsoft Defender for Identity を正常に構成しました。</span><span class="sxs-lookup"><span data-stu-id="b3f52-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![イメージ of_Microsoft Defender for Identity センサー ウィザードのインストール完了で、[完了] ボタンをクリックする必要があります。](../../media/mtp-eval-51.png)

11. <span data-ttu-id="b3f52-191">[Microsoft [Defender for Identity の設定](https://go.microsoft.com/fwlink/?linkid=2040449) ] セクションで、[\*\*Microsoft Defender for Endpoint \*\*] を選択し、トグルをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="b3f52-192">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-192">Click **Save**.</span></span>

    ![[of_theの設定] ページの [Microsoft Defender for Endpoint] トグルをオンにする必要があるイメージ](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="b3f52-194">構成Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3f52-194">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="b3f52-195">この手順は、既に有効にしている場合はMicrosoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="b3f52-195">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span>

1. <span data-ttu-id="b3f52-196">[セキュリティ センターの [Microsoft 365リソース]](https://security.microsoft.com/info)  >  **ページに移動**  >  **Microsoft Cloud App Security。**</span><span class="sxs-lookup"><span data-stu-id="b3f52-196">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![イメージ of_Microsoft 365 セキュリティ センター ページで、Microsoft Cloud App カードを表示し、[開く] ボタンをクリックする必要があります。](../../media/mtp-eval-53.png)

2. <span data-ttu-id="b3f52-198">Microsoft Defender for Identity の統合を求める情報プロンプトで、[Id データの統合に Microsoft Defender を有効 **にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-198">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>

   ![[of_theを有効にする] を選択する必要がある Microsoft Defender for Identity の統合に関する情報プロンプトの画像](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="b3f52-200">このプロンプトが表示されていない場合は、Microsoft Defender for Identity データ統合が既に有効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3f52-200">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="b3f52-201">ただし、確認できない場合は、IT 管理者に問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="b3f52-201">However, if you are not sure, contact your IT Administrator to confirm.</span></span>

3. <span data-ttu-id="b3f52-202">[ユーザー]**設定、Microsoft** **Defender for Identity 統合** トグルをオンにし、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-202">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span>

   ![[of_the設定] ページで、Microsoft Defender for Identity 統合トグルをオンにし、[保存] をクリックします。](../../media/mtp-eval-55.png)

   > [!NOTE]
   > <span data-ttu-id="b3f52-204">新しい Microsoft Defender for Identity インスタンスの場合、この統合トグルは自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="b3f52-204">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="b3f52-205">次の手順に進む前に、Microsoft Defender for Identity 統合が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-205">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>

4. <span data-ttu-id="b3f52-206">[クラウド検出設定] で **、[Microsoft Defender for Endpoint integration] を選択し**、統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-206">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="b3f52-207">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-207">Click **Save**.</span></span>

   ![Image of_the Microsoft Defender for Endpoint ページで、[Microsoft Defender for Endpoint の統合] の下にある [ブロックが許可されていないアプリ] チェック ボックスがオンです。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="b3f52-210">[クラウド検出の設定] で、[**ユーザーのエンリッチメント]** を選択し、次に[クラウド検出] Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="b3f52-210">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![[ユーザー名を使用して検出されたユーザー識別子を強化する] チェック ボックスがオンAzure Active Directory[ユーザーエンリッチメント] セクションのイメージ](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="b3f52-212">エンドポイント用の Microsoft Defender の構成</span><span class="sxs-lookup"><span data-stu-id="b3f52-212">Configure Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="b3f52-213">Microsoft Defender for Endpoint を既に有効にしている場合は、この手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-213">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="b3f52-214">[セキュリティ センターの [Microsoft 365リソース]](https://security.microsoft.com/info)  >  **ページに移動**  >  **Microsoft Defender セキュリティ センター。**</span><span class="sxs-lookup"><span data-stu-id="b3f52-214">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="b3f52-215">[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-215">Click **Open**.</span></span>

   ![[of_Microsoft センター] ページの [Defender セキュリティ センター] Microsoft 365オプションのイメージ](../../media/mtp-eval-58.png)

2. <span data-ttu-id="b3f52-217">Microsoft Defender for Endpoint ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="b3f52-217">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="b3f52-218">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-218">Click **Next**.</span></span>

   ![イメージ of_the Microsoft Defender セキュリティ センターウェルカム ウィザード ページ](../../media/mtp-eval-59.png)

3. <span data-ttu-id="b3f52-220">優先するデータ保存場所、データ保持ポリシー、組織のサイズ、プレビュー機能のオプトインに基づいて選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-220">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![[of_the] ページで、データ ストレージの国、アイテム保持ポリシー、組織のサイズを選択します。](../../media/mtp-eval-60.png)

   > [!NOTE]
   > <span data-ttu-id="b3f52-223">後で、データストレージの場所など、一部の設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b3f52-223">You cannot change some of the settings, like data storage location, afterwards.</span></span>

   <span data-ttu-id="b3f52-224">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-224">Click **Next**.</span></span>

4. <span data-ttu-id="b3f52-225">[ **続行] を** クリックすると、Microsoft Defender for Endpoint テナントがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="b3f52-225">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![[of_the] ボタンをクリックしてクラウド インスタンスを作成するように求める画像のページ](../../media/mtp-eval-61.png)

5. <span data-ttu-id="b3f52-227">グループ ポリシー、グループ ポリシー、または Microsoft Defender for Endpoint Microsoft エンドポイント マネージャーローカル スクリプトを実行して、エンドポイントをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b3f52-228">わかりやすくするために、このガイドではローカル スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-228">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="b3f52-229">[ **パッケージのダウンロード]** をクリックし、オンボーディング スクリプトをエンドポイントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-229">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![イメージ of_page[パッケージのダウンロード] ボタンをクリックしてオンボーディング スクリプトをエンドポイントまたはエンドポイントにコピーするように求めるメッセージが表示されます。](../../media/mtp-eval-62.png)

7. <span data-ttu-id="b3f52-231">エンドポイントで、オンボーディング スクリプトを管理者として実行し、[Y] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-231">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>

   ![オンボード of_the実行し、[Y] を選択して続行するコマンド ラインのイメージ](../../media/mtp-eval-63.png)

8. <span data-ttu-id="b3f52-233">おめでとうございます、最初のエンドポイントをオンボードしました。</span><span class="sxs-lookup"><span data-stu-id="b3f52-233">Congratulations, you've onboarded your first endpoint.</span></span>

   ![イメージof_theコマンド ラインで、最初のエンドポイントをオンボードしたという確認を取得します。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="b3f52-236">検出テストを Microsoft Defender for Endpoint ウィザードからコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b3f52-236">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the検出テスト ステップを実行し、[コピー] をクリックして、コマンド プロンプトに貼り付ける検出テスト スクリプトをコピーします。](../../media/mtp-eval-65.png)

10. <span data-ttu-id="b3f52-238">PowerShell スクリプトを管理者特権のコマンド プロンプトにコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-238">Copy the PowerShell script to an elevated command prompt and run it.</span></span>

    ![PowerShell スクリプトof_command管理者特権でコマンド プロンプトにコピーし、実行する必要があるイメージ プロンプト](../../media/mtp-eval-66.png)

11. <span data-ttu-id="b3f52-240">ウィザードから **[Microsoft Defender for Endpoint の使用を** 開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-240">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![ウィザードof_the確認メッセージが表示されたら、[Microsoft Defender for Endpoint の使用を開始する] をクリックする必要があります。](../../media/mtp-eval-67.png)

12. <span data-ttu-id="b3f52-242">ページにアクセス[Microsoft Defender セキュリティ センター。](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="b3f52-242">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="b3f52-243">[詳細] に **設定** し、[高度な機能]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-243">Go to **Settings** and then select **Advanced features**.</span></span>

    ![[詳細of_Microsoftを選択する設定 Defender Security Center のイメージ メニュー](../../media/mtp-eval-68.png)

13. <span data-ttu-id="b3f52-245">Microsoft Defender for Identity との統合 **を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-245">Turn on the integration with **Microsoft Defender for Identity**.</span></span>

    ![イメージ of_Microsoft Defender Security Center Advanced 機能、有効にする必要がある Microsoft Defender for Identity オプショントグル](../../media/mtp-eval-69.png)

14. <span data-ttu-id="b3f52-247">脅威インテリジェンスとの統合を有効Office 365 **します**。</span><span class="sxs-lookup"><span data-stu-id="b3f52-247">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Defender security Center of_Microsoft高度な機能のイメージ、Office 365が有効にする必要がある脅威インテリジェンス オプショントグル](../../media/mtp-eval-70.png)

15. <span data-ttu-id="b3f52-249">ユーザーとの統合を **有効Microsoft Cloud App Security。**</span><span class="sxs-lookup"><span data-stu-id="b3f52-249">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![イメージ of_Microsoft Defender Security Center Advanced の機能、Microsoft Cloud App Securityする必要があるオプショントグル](../../media/mtp-eval-71.png)

16. <span data-ttu-id="b3f52-251">下にスクロールし、[ **基本設定の保存] をクリックして** 、新しい統合を確認します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-251">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![[of_Saveする必要がある画像の設定] ボタン](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="b3f52-253">Microsoft 365 Defender サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="b3f52-253">Start the Microsoft 365 Defender service</span></span>

> [!NOTE]
> <span data-ttu-id="b3f52-254">2020 年 6 月 1 日から、Microsoft は対象Microsoft 365 Defender機能を自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="b3f52-254">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="b3f52-255">詳細については[、この Microsoft Tech Communityのライセンスの適格性に関する記事](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3f52-255">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span>

<span data-ttu-id="b3f52-256">[セキュリティ センター [Microsoft 365] に移動します](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="b3f52-256">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="b3f52-257">[ファイル] に **設定** し、[次へ] を **Microsoft 365 Defender。**</span><span class="sxs-lookup"><span data-stu-id="b3f52-257">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![[of_Microsoft センター] ページのイメージ Microsoft 365 365 Defender 設定スクリーンショット](../../media/mtp-eval-72b.png)

<span data-ttu-id="b3f52-259">より包括的なガイダンスについては、「電源を入[Microsoft 365 Defender。](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="b3f52-259">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="b3f52-260">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="b3f52-260">Congratulations!</span></span> <span data-ttu-id="b3f52-261">試用版ラボまたはパイロット環境Microsoft 365 Defender作成しました。</span><span class="sxs-lookup"><span data-stu-id="b3f52-261">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="b3f52-262">これで、ユーザー インターフェイスのMicrosoft 365 Defender理解できます。</span><span class="sxs-lookup"><span data-stu-id="b3f52-262">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="b3f52-263">次の対話型ガイドから学習できる情報Microsoft 365 Defender、毎日のセキュリティ操作タスクに各ダッシュボードを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-263">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="b3f52-264">対話型のガイドをチェックしてください</span><span class="sxs-lookup"><span data-stu-id="b3f52-264">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="b3f52-265">次に、攻撃をシミュレートし、クロス製品機能がエンドポイントに対するファイルレス攻撃を検出、作成、および自動的に応答する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3f52-265">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="b3f52-266">次の手順</span><span class="sxs-lookup"><span data-stu-id="b3f52-266">Next step</span></span>

- <span data-ttu-id="b3f52-267">[テストアラートの生成](generate-test-alert.md)- テストテスト ラボで攻撃シミュレーションMicrosoft 365 Defender実行します。</span><span class="sxs-lookup"><span data-stu-id="b3f52-267">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>
