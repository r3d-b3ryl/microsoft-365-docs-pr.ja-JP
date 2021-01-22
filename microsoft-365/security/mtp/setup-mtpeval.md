---
title: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップする
description: Microsoft 365 セキュリティ センターにアクセスし、Microsoft 365 Defender 試用版ラボ環境をセットアップする
keywords: Microsoft Threat Protection 試用版のセットアップ, Microsoft Threat Protection パイロット セットアップ, Microsoft Threat Protection, Microsoft Threat Protection 評価ラボのセットアップ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932984"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="243ef-104">Microsoft 365 Defender 試用版ラボ環境をセットアップする</span><span class="sxs-lookup"><span data-stu-id="243ef-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="243ef-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="243ef-105">**Applies to:**</span></span>
- <span data-ttu-id="243ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="243ef-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="243ef-107">Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成して展開するには、次の 3 段階のプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="243ef-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="243ef-108">[![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="243ef-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="243ef-109">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="243ef-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![フェーズ 2: セットアップ](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="243ef-111">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="243ef-111">Phase 2: Set up</span></span> |<span data-ttu-id="243ef-112">[![フェーズ 3: オンボーディング](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="243ef-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="243ef-113">フェーズ 3: オンボーディング</span><span class="sxs-lookup"><span data-stu-id="243ef-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="243ef-114">[![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="243ef-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="243ef-115">パイロット プレイブックに戻る</span><span class="sxs-lookup"><span data-stu-id="243ef-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="243ef-116">*ここにいます。*</span><span class="sxs-lookup"><span data-stu-id="243ef-116">*You are here!*</span></span>  | | |


<span data-ttu-id="243ef-117">現在セットアップ フェーズ中です。</span><span class="sxs-lookup"><span data-stu-id="243ef-117">You're currently in the set up phase.</span></span> <span data-ttu-id="243ef-118">最初の手順を実行して Microsoft 365 セキュリティ センターにアクセスし、試用版ラボまたはパイロット環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="243ef-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="243ef-119">Office 365 または Azure Active Directory サブスクリプションにサインアップして、Microsoft 365 E5 ライセンスへのサインアップに使用できる *.onmicrosoft.com* テナントを生成します。</span><span class="sxs-lookup"><span data-stu-id="243ef-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="243ef-120">既存の Office 365 または Azure Active Directory サブスクリプションがある場合は、Office 365 E5 試用版またはパイロット テナント作成手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="243ef-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="243ef-121">このフェーズでは、次のガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="243ef-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="243ef-122">Office 365 E5 試用版テナントを作成する</span><span class="sxs-lookup"><span data-stu-id="243ef-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="243ef-123">Microsoft 365 試用版サブスクリプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="243ef-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="243ef-124">Office 365 E5 試用版テナントを作成する</span><span class="sxs-lookup"><span data-stu-id="243ef-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="243ef-125">既存の Office 365 または Azure Active Directory サブスクリプションがある場合は、Office 365 E5 試用版テナントの作成手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="243ef-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="243ef-126">[Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)製品ポータルに移動し、[無料試用版]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="243ef-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="243ef-128">メール アドレス (個人または企業) を入力して、試用版の登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="243ef-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="243ef-129">[アカウント **の設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="243ef-129">Click **Set up account**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)

3. <span data-ttu-id="243ef-131">名、名、名、会社の電話番号、会社名、会社の規模、国または地域を入力します。</span><span class="sxs-lookup"><span data-stu-id="243ef-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![名前、電話Office会社の詳細を求める_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="243ef-133">ここで設定する国または地域によって、Office 365 がホストされるデータ センターの地域が決なります。</span><span class="sxs-lookup"><span data-stu-id="243ef-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="243ef-134">確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。</span><span class="sxs-lookup"><span data-stu-id="243ef-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="243ef-135">[確認 **コードの送信] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="243ef-135">Click **Send Verification Code**.</span></span> 

   ![検証のOfficeを求める_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-12.png)

5. <span data-ttu-id="243ef-137">テナントのカスタム ドメイン名を設定し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="243ef-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![カスタム ドメイン名Office設定できる_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="243ef-139">テナントのグローバル管理者になる最初の ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="243ef-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="243ef-140">名前と **パスワードを** 入力 **します**。</span><span class="sxs-lookup"><span data-stu-id="243ef-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="243ef-141">**[サインアップ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243ef-141">Click **Sign up**.</span></span>

   ![ビジネス ID をOfficeできる_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-14.png)

7. <span data-ttu-id="243ef-143">[ **セットアップに移動] を** クリックして、Office 365 E5 試用版テナントのプロビジョニングを完了します。</span><span class="sxs-lookup"><span data-stu-id="243ef-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![[Go Setup] Officeをクリックするように求める 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-15.png)

8. <span data-ttu-id="243ef-145">企業ドメインを Office 365 テナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="243ef-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="243ef-146">[省略可能]Choose **Connect a domain you already own** and type in your domain name.</span><span class="sxs-lookup"><span data-stu-id="243ef-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="243ef-147">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243ef-147">Click **Next**.</span></span>

   ![サインインとメールOfficeカスタマイズする必要がある_Office 365 E5 セットアップ ページの画像](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="243ef-149">TXT レコードまたは MX レコードを追加して、ドメインの所有権を検証します。</span><span class="sxs-lookup"><span data-stu-id="243ef-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="243ef-150">ドメインに TXT レコードまたは MX レコードを追加したら、[確認] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="243ef-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![ドメインを確認Office MX レコードの TXT を追加する必要がある_Office 365 E5 セットアップ ページの画像](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="243ef-152">[省略可能]テナント用にさらにユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="243ef-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="243ef-153">You can skip this step by clicking **Next**.</span><span class="sxs-lookup"><span data-stu-id="243ef-153">You can skip this step by clicking **Next**.</span></span>

    ![ユーザーを追加Officeできる_Office 365 E5 セットアップ ページの画像](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="243ef-155">[省略可能]アプリOfficeダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="243ef-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="243ef-156">[ **次へ] を** クリックしてこの手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="243ef-156">Click **Next** to skip this step.</span></span> 

    ![アプリをOfficeできる_Office 365 E5 ページOffice画像](../../media/mtp-eval-19.png)

12. <span data-ttu-id="243ef-158">[省略可能]電子メール メッセージを移行します。</span><span class="sxs-lookup"><span data-stu-id="243ef-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="243ef-159">繰り返しになりますが、この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="243ef-159">Again, you can skip this step.</span></span>

    ![電子メール Officeするかどうかを設定できる_Office 365 E5 の画像](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="243ef-161">オンライン サービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="243ef-161">Choose online services.</span></span> <span data-ttu-id="243ef-162">**[Exchange] を選択し**、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="243ef-162">Select **Exchange** and click **Next**.</span></span> 

    ![オンライン サービスをOfficeできる_Office 365 E5 の画像](../../media/mtp-eval-21.png)

14. <span data-ttu-id="243ef-164">MX、CNAME、TXT レコードをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="243ef-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="243ef-165">完了したら、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="243ef-165">When completed, select **Verify**.</span></span>

    ![DNS レコードを追加Office_Office 365 E5 の画像](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="243ef-167">これで完了です。365 テナントのプロビジョニングOffice完了です。</span><span class="sxs-lookup"><span data-stu-id="243ef-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="243ef-169">Microsoft 365 試用版サブスクリプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="243ef-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="243ef-170">試用版にサインアップすると、1 か月間使用できる 25 のユーザー ライセンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="243ef-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="243ef-171">詳細 [については、「M365 サブスクリプションを試用または購入する](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="243ef-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="243ef-172">[Microsoft 365 管理センターで、[](https://admin.microsoft.com/)**課金]** をクリックし、[サービスの購入]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="243ef-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="243ef-173">**Microsoft 365 E5 を選択し、[** 無料試用版の開始]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="243ef-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)

3. <span data-ttu-id="243ef-175">確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。</span><span class="sxs-lookup"><span data-stu-id="243ef-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="243ef-176">決定したら、電話番号を入力し、選択内容に応じて[自分にテキスト] または [電話] を選択します。</span><span class="sxs-lookup"><span data-stu-id="243ef-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="243ef-178">確認コードを入力し、[無料試用版 **の開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="243ef-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="243ef-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span><span class="sxs-lookup"><span data-stu-id="243ef-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="243ef-182">Go to the **Microsoft 365 Admin Center** Users  >  **Active**  >  **users**.</span><span class="sxs-lookup"><span data-stu-id="243ef-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="243ef-183">ユーザー アカウントを選択し、[製品ライセンスの管理] を選択し、ライセンスを Office 365 E5 から **Microsoft 365 E5 に交換します**。</span><span class="sxs-lookup"><span data-stu-id="243ef-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="243ef-184">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243ef-184">Click **Save**.</span></span>

   ![[Of_Microsoft 365 管理センター] ページで Microsoft 365 E5 ライセンスを選択できる画像](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="243ef-186">グローバル管理者アカウントを再び選択し、[ユーザー名の管理] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="243ef-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)

8. <span data-ttu-id="243ef-188">[省略可能]前の手順で *onmicrosoft.com* に応じて、ドメインをドメインから独自のドメインに変更します。</span><span class="sxs-lookup"><span data-stu-id="243ef-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="243ef-189">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243ef-189">Click **Save changes**.</span></span>

   ![ドメインof_Microsoft変更できる [365 管理センター] ページの画像](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="243ef-191">次の手順</span><span class="sxs-lookup"><span data-stu-id="243ef-191">Next step</span></span>
|[<span data-ttu-id="243ef-192">フェーズ 3: オンボードの&する</span><span class="sxs-lookup"><span data-stu-id="243ef-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="243ef-193">Microsoft 365 Defender 試用版ラボまたはパイロット環境用に各 Microsoft 365 Defender の柱を構成し、エンドポイントをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="243ef-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
