---
title: 試用版ラボまたはMicrosoft 365 Defender環境をセットアップする
description: セキュリティ Microsoft 365にアクセスし、試用版ラボ環境Microsoft 365 Defenderセットアップする
keywords: Microsoft 365 Defenderセットアップ、パイロットMicrosoft 365 Defender、評価ラボのMicrosoft 365 Defender、Microsoft 365 Defender試す
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454735"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="3f152-104">ラボ環境でMicrosoft 365 Defender試用版をセットアップする</span><span class="sxs-lookup"><span data-stu-id="3f152-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3f152-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3f152-105">**Applies to:**</span></span>
- <span data-ttu-id="3f152-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f152-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="3f152-107">このトピックでは、専用のラボ環境をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f152-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="3f152-108">実稼働環境での試用版のセットアップの詳細については、新しい評価とパイロット ガイド[をMicrosoft 365 Defender](eval-overview.md)してください。</span><span class="sxs-lookup"><span data-stu-id="3f152-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="3f152-109">試用版テナントOffice 365 E5作成する</span><span class="sxs-lookup"><span data-stu-id="3f152-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="3f152-110">既存のサブスクリプションまたはサブスクリプションが既Office 365場合Azure Active Directory試用版テナントの作成手順Office 365 E5スキップできます。</span><span class="sxs-lookup"><span data-stu-id="3f152-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="3f152-111">[製品ポータル] に [Office 365 E5し、[](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)無料試用版]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f152-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Image of_Office 365 E5 無料試用版ページ](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="3f152-113">電子メール アドレス (個人または企業) を入力して、試用版の登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="3f152-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="3f152-114">[アカウント **の設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3f152-114">Click **Set up account**.</span></span>

   ![Image of_Office 365 E5 試用版登録のセットアップ ページ](../../media/mtp-eval-10.png)

3. <span data-ttu-id="3f152-116">名、名、会社の電話番号、会社名、会社の規模、国または地域を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f152-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![名前、電話Office会社の詳細を求める画像 of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="3f152-118">ここで設定した国または地域によって、ホストされるデータ センター Office 365決定されます。</span><span class="sxs-lookup"><span data-stu-id="3f152-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="3f152-119">確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f152-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="3f152-120">[検証 **コードの送信] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3f152-120">Click **Send Verification Code**.</span></span> 

   ![検証の設定をOfficeする Image of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-12.png)

5. <span data-ttu-id="3f152-122">テナントのカスタム ドメイン名を設定し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3f152-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 試用版登録セットアップ ページ (カスタム ドメイン名を設定できる)](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="3f152-124">テナントのグローバル管理者になる最初の ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="3f152-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="3f152-125">[名前] **と [パスワード]** を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="3f152-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="3f152-126">[**サインアップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f152-126">Click **Sign up**.</span></span>

   ![ビジネス ID をOfficeできる Image of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-14.png)

7. <span data-ttu-id="3f152-128">[**セットアップに移動] を** クリックして、Office 365 E5プロビジョニングを完了します。</span><span class="sxs-lookup"><span data-stu-id="3f152-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![[Go setup] Office 365 E5をクリックするように求める試用版登録セットアップ ページのイメージ](../../media/mtp-eval-15.png)

8. <span data-ttu-id="3f152-130">ConnectドメインをテナントにOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="3f152-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="3f152-131">[省略可能]**[Connect所有しているドメインを選択し、** ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f152-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="3f152-132">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f152-132">Click **Next**.</span></span>

   ![サインインとメールOfficeカスタマイズする必要がある 365 E5 セットアップ ページの画像](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="3f152-134">TXT レコードまたは MX レコードを追加して、ドメインの所有権を検証します。</span><span class="sxs-lookup"><span data-stu-id="3f152-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="3f152-135">ドメインに TXT レコードまたは MX レコードを追加したら、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f152-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![ドメインを確認Office MX レコードの TXT を追加する必要がある Image of_Office 365 E5 セットアップ ページ](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="3f152-137">[省略可能]テナントのユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f152-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="3f152-138">[次へ] をクリックすると、この手順を **スキップできます**。</span><span class="sxs-lookup"><span data-stu-id="3f152-138">You can skip this step by clicking **Next**.</span></span>

    ![Image of_Officeユーザーを追加できる 365 E5 セットアップ ページ](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="3f152-140">[省略可能]アプリOfficeダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3f152-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="3f152-141">[次 **へ] を** クリックして、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="3f152-141">Click **Next** to skip this step.</span></span> 

    ![Image of_Office 365 E5 ページで、アプリをインストールOfficeできます](../../media/mtp-eval-19.png)

12. <span data-ttu-id="3f152-143">[省略可能]電子メール メッセージを移行します。</span><span class="sxs-lookup"><span data-stu-id="3f152-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="3f152-144">繰り返しますが、この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="3f152-144">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5 電子メール メッセージを移行するかどうかを設定できます](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="3f152-146">[オンライン サービス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f152-146">Choose online services.</span></span> <span data-ttu-id="3f152-147">[次 **Exchange] を** 選択し、[次へ]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3f152-147">Select **Exchange** and click **Next**.</span></span> 

    ![オンライン サービスをOfficeできる Image of_Office 365 E5](../../media/mtp-eval-21.png)

14. <span data-ttu-id="3f152-149">ドメインに MX、CNAME、TXT レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f152-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="3f152-150">完了したら、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3f152-150">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 HERE では、DNS レコードを追加できます](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="3f152-152">おめでとうございます、テナントのプロビジョニングOffice 365完了です。</span><span class="sxs-lookup"><span data-stu-id="3f152-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Image of_Office 365 E5 セットアップ完了確認ページ](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="3f152-154">試用版サブスクリプションMicrosoft 365有効にする</span><span class="sxs-lookup"><span data-stu-id="3f152-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="3f152-155">試用版にサインアップすると、1 か月間 25 のユーザー ライセンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f152-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="3f152-156">詳細 [については、「Try or Buy a M365 サブスクリプション」](../../commerce/try-or-buy-microsoft-365.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f152-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="3f152-157">[[Microsoft 365 管理センター] で、[](https://admin.microsoft.com/)課金]**をクリック** し、[サービスの購入]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3f152-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="3f152-158">[無料 **Microsoft 365 E5] を** 選択し、[無料試用版の **開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3f152-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![イメージ of_Microsoft 365 E5 無料試用版の開始ページ](../../media/mtp-eval-24.png)

3. <span data-ttu-id="3f152-160">確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f152-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="3f152-161">決定したら、電話番号を入力し、選択内容に応じて[テキスト] または [電話] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f152-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 無料試用版ページを開始して、ロボットではないことを証明するコードを送信する連絡先の詳細を求める](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="3f152-163">確認コードを入力し、[無料試用版の **開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3f152-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 無料試用版ページを開始して、システムが送信した検証コードを入力して、ロボットではないと証明できます](../../media/mtp-eval-26.png)

5. <span data-ttu-id="3f152-165">[**今すぐ試す**] をクリックして、Microsoft 365 E5確認します。</span><span class="sxs-lookup"><span data-stu-id="3f152-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 無料試用版ページを開始するには、[今すぐ試す] ボタンを起動する必要があります。](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="3f152-167">[センター ユーザー]**の [Microsoft 365 管理アクティブ**  >  **ユーザー]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3f152-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="3f152-168">ユーザー アカウントを選択し、[製品ライセンス **の管理]** を選択し、ライセンスを [ライセンス] から [Office 365 E5 Microsoft 365 E5。 </span><span class="sxs-lookup"><span data-stu-id="3f152-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="3f152-169">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f152-169">Click **Save**.</span></span>

   ![イメージ of_Microsoft 365 管理センター ページで、ライセンスを選択Microsoft 365 E5できます。](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="3f152-171">グローバル管理者アカウントを再度選択し、[ユーザー名の管理 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3f152-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![[of_Microsoft 365 管理センター] ページで[アカウント] を選択し、[ユーザー名の管理] を選択できます。](../../media/mtp-eval-29.png)

8. <span data-ttu-id="3f152-173">[省略可能]前 *の手順で* onmicrosoft.com に応じて、ドメインをドメインから独自のドメインに変更します。</span><span class="sxs-lookup"><span data-stu-id="3f152-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="3f152-174">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f152-174">Click **Save changes**.</span></span>

   ![ドメインof_Microsoft変更できる 365 管理センター ページのイメージ](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="3f152-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="3f152-176">Next step</span></span>
|[<span data-ttu-id="3f152-177">フェーズ 3: オンボードで&する</span><span class="sxs-lookup"><span data-stu-id="3f152-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="3f152-178">お客様のMicrosoft 365 Defenderラボまたはパイロット環境Microsoft 365 Defender、エンドポイントをオンボードする場合は、各デバイスの柱を構成します。</span><span class="sxs-lookup"><span data-stu-id="3f152-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
