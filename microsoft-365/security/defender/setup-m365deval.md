---
title: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップする
description: Access Microsoft 365 Security Center その後、Microsoft 365 Defender 試用版ラボ環境をセットアップする
keywords: Microsoft Threat Protection 試用版セットアップ、Microsoft Threat Protection パイロット セットアップ、Try Microsoft Threat Protection、Microsoft Threat Protection 評価ラボ セットアップ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 976f6a1ec010348e8a281c251064acdd7a26748b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066739"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="350c2-104">Microsoft 365 Defender 試用版ラボ環境のセットアップ</span><span class="sxs-lookup"><span data-stu-id="350c2-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="350c2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="350c2-105">**Applies to:**</span></span>
- <span data-ttu-id="350c2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="350c2-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="350c2-107">Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成し、それを展開するには、次の 3 段階のプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="350c2-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="350c2-108">[![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="350c2-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="350c2-109">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="350c2-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![フェーズ 2: セットアップ](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="350c2-111">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="350c2-111">Phase 2: Set up</span></span> |<span data-ttu-id="350c2-112">[![フェーズ 3: オンボード](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="350c2-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="350c2-113">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="350c2-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="350c2-114">[![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="350c2-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="350c2-115">パイロット プレイブックに戻る</span><span class="sxs-lookup"><span data-stu-id="350c2-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="350c2-116">*お前はここにいる!*</span><span class="sxs-lookup"><span data-stu-id="350c2-116">*You are here!*</span></span>  | | |


<span data-ttu-id="350c2-117">現在、セットアップ フェーズに入っている。</span><span class="sxs-lookup"><span data-stu-id="350c2-117">You're currently in the set up phase.</span></span> <span data-ttu-id="350c2-118">最初の手順を実行して Microsoft 365 セキュリティ センターにアクセスし、試用版ラボまたはパイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="350c2-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="350c2-119">Office 365 または Azure Active Directory サブスクリプションにサインアップして、Microsoft 365 E5 ライセンスにサインアップするために使用できる *.onmicrosoft.com* テナントを生成します。</span><span class="sxs-lookup"><span data-stu-id="350c2-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="350c2-120">既存の 365 または Azure Active Directory サブスクリプションOfficeしている場合は、Office 365 E5 試用版またはパイロット テナントの作成手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="350c2-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="350c2-121">このフェーズでは、次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="350c2-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="350c2-122">365 E5 Officeテナントを作成する</span><span class="sxs-lookup"><span data-stu-id="350c2-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="350c2-123">Microsoft 365 試用版サブスクリプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="350c2-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="350c2-124">365 E5 Officeテナントを作成する</span><span class="sxs-lookup"><span data-stu-id="350c2-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="350c2-125">既存のサブスクリプション 365 または Azure Active Directory サブスクリプションOfficeしている場合は、365 E5 試用版テナントの作成手順Officeスキップできます。</span><span class="sxs-lookup"><span data-stu-id="350c2-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="350c2-126">[365 E5 Officeに](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)移動し、[無料試用版]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="350c2-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Image of_Office 365 E5 無料試用版ページ](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="350c2-128">電子メール アドレス (個人または企業) を入力して、試用版の登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="350c2-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="350c2-129">[アカウント **の設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="350c2-129">Click **Set up account**.</span></span>

   ![Image of_Office 365 E5 試用版登録のセットアップ ページ](../../media/mtp-eval-10.png)

3. <span data-ttu-id="350c2-131">名、名、会社の電話番号、会社名、会社の規模、国または地域を入力します。</span><span class="sxs-lookup"><span data-stu-id="350c2-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![名前、電話Office会社の詳細を求める画像 of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="350c2-133">ここで設定した国または地域によって、365 のデータ センター Officeが決定されます。</span><span class="sxs-lookup"><span data-stu-id="350c2-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="350c2-134">確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。</span><span class="sxs-lookup"><span data-stu-id="350c2-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="350c2-135">[検証 **コードの送信] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="350c2-135">Click **Send Verification Code**.</span></span> 

   ![検証の設定をOfficeする Image of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-12.png)

5. <span data-ttu-id="350c2-137">テナントのカスタム ドメイン名を設定し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="350c2-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 試用版登録セットアップ ページ (カスタム ドメイン名を設定できる)](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="350c2-139">テナントのグローバル管理者になる最初の ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="350c2-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="350c2-140">[名前] **と [パスワード]** を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="350c2-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="350c2-141">**[サインアップ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="350c2-141">Click **Sign up**.</span></span>

   ![ビジネス ID をOfficeできる Image of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-14.png)

7. <span data-ttu-id="350c2-143">[ **セットアップに移動] を** クリックして、Office 365 E5 試用版テナントのプロビジョニングを完了します。</span><span class="sxs-lookup"><span data-stu-id="350c2-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![[Go setup] Officeをクリックするように求める 365 E5 試用版登録セットアップ ページのイメージ](../../media/mtp-eval-15.png)

8. <span data-ttu-id="350c2-145">企業ドメインを 365 テナントOffice接続します。</span><span class="sxs-lookup"><span data-stu-id="350c2-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="350c2-146">[省略可能][ **既に所有しているドメインを接続する] を選択し** 、ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="350c2-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="350c2-147">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="350c2-147">Click **Next**.</span></span>

   ![サインインとメールOfficeカスタマイズする必要がある 365 E5 セットアップ ページの画像](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="350c2-149">TXT レコードまたは MX レコードを追加して、ドメインの所有権を検証します。</span><span class="sxs-lookup"><span data-stu-id="350c2-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="350c2-150">ドメインに TXT レコードまたは MX レコードを追加したら、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="350c2-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![ドメインを確認Office MX レコードの TXT を追加する必要がある Image of_Office 365 E5 セットアップ ページ](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="350c2-152">[省略可能]テナントのユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="350c2-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="350c2-153">[次へ] をクリックすると、この手順を **スキップできます**。</span><span class="sxs-lookup"><span data-stu-id="350c2-153">You can skip this step by clicking **Next**.</span></span>

    ![Image of_Officeユーザーを追加できる 365 E5 セットアップ ページ](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="350c2-155">[省略可能]アプリOfficeダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="350c2-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="350c2-156">[次 **へ] を** クリックして、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="350c2-156">Click **Next** to skip this step.</span></span> 

    ![Image of_Office 365 E5 ページで、アプリをインストールOfficeできます](../../media/mtp-eval-19.png)

12. <span data-ttu-id="350c2-158">[省略可能]電子メール メッセージを移行します。</span><span class="sxs-lookup"><span data-stu-id="350c2-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="350c2-159">繰り返しますが、この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="350c2-159">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5 電子メール メッセージを移行するかどうかを設定できます](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="350c2-161">[オンライン サービス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="350c2-161">Choose online services.</span></span> <span data-ttu-id="350c2-162">**[Exchange] を選択し**、[次へ]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="350c2-162">Select **Exchange** and click **Next**.</span></span> 

    ![オンライン サービスをOfficeできる Image of_Office 365 E5](../../media/mtp-eval-21.png)

14. <span data-ttu-id="350c2-164">ドメインに MX、CNAME、TXT レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="350c2-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="350c2-165">完了したら、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="350c2-165">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 HERE では、DNS レコードを追加できます](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="350c2-167">おめでとうございます、365 テナントのプロビジョニングOffice完了です。</span><span class="sxs-lookup"><span data-stu-id="350c2-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Image of_Office 365 E5 セットアップ完了確認ページ](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="350c2-169">Microsoft 365 試用版サブスクリプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="350c2-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="350c2-170">試用版にサインアップすると、1 か月間 25 のユーザー ライセンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="350c2-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="350c2-171">詳細 [については、「Try or Buy a M365 サブスクリプション」](../../commerce/try-or-buy-microsoft-365.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="350c2-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="350c2-172">[Microsoft 365 管理センターで、[課金](https://admin.microsoft.com/)**]** をクリックし、[サービスの購入]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="350c2-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="350c2-173">[Microsoft **365 E5] を選択し、[** 無料試用版の開始 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="350c2-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![イメージ of_Microsoft 365 E5 無料試用版の開始ページ](../../media/mtp-eval-24.png)

3. <span data-ttu-id="350c2-175">確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。</span><span class="sxs-lookup"><span data-stu-id="350c2-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="350c2-176">決定したら、電話番号を入力し、選択内容に応じて[テキスト] または [電話] を選択します。</span><span class="sxs-lookup"><span data-stu-id="350c2-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 無料試用版ページを開始して、ロボットではないことを証明するコードを送信する連絡先の詳細を求める](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="350c2-178">確認コードを入力し、[無料試用版の **開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="350c2-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 無料試用版ページを開始して、システムが送信した検証コードを入力して、ロボットではないと証明できます](../../media/mtp-eval-26.png)

5. <span data-ttu-id="350c2-180">[ **今すぐ試す** ] をクリックして、Microsoft 365 E5 試用版を確認します。</span><span class="sxs-lookup"><span data-stu-id="350c2-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 無料試用版ページを開始するには、[今すぐ試す] ボタンを起動する必要があります。](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="350c2-182">**[Microsoft 365 管理センター ユーザー] [アクティブ**  >  **ユーザー**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="350c2-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="350c2-183">ユーザー アカウントを選択し、[製品ライセンスの **管理**] を選択し、ライセンスを 365 E5 Office **Microsoft 365 E5 に交換します**。</span><span class="sxs-lookup"><span data-stu-id="350c2-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="350c2-184">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="350c2-184">Click **Save**.</span></span>

   ![[of_Microsoft 365 管理センター] ページで、Microsoft 365 E5 ライセンスを選択できます。](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="350c2-186">グローバル管理者アカウントを再度選択し、[ユーザー名の管理 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="350c2-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![[of_Microsoft 365 管理センター] ページで[アカウント] を選択し、[ユーザー名の管理] を選択できます。](../../media/mtp-eval-29.png)

8. <span data-ttu-id="350c2-188">[省略可能]前 *の手順で* onmicrosoft.com に応じて、ドメインをドメインから独自のドメインに変更します。</span><span class="sxs-lookup"><span data-stu-id="350c2-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="350c2-189">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="350c2-189">Click **Save changes**.</span></span>

   ![ドメインof_Microsoft変更できる 365 管理センター ページのイメージ](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="350c2-191">次の手順</span><span class="sxs-lookup"><span data-stu-id="350c2-191">Next step</span></span>
|[<span data-ttu-id="350c2-192">フェーズ 3: オンボードで&する</span><span class="sxs-lookup"><span data-stu-id="350c2-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="350c2-193">Microsoft 365 Defender 試用版ラボまたはパイロット環境用に各 Microsoft 365 Defender の柱を構成し、エンドポイントをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="350c2-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
