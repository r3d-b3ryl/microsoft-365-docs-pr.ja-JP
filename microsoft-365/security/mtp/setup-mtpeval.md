---
title: Microsoft の脅威保護のテスト環境をセットアップする
description: Microsoft 365 セキュリティセンターにアクセスして、Microsoft の脅威保護のテスト環境をセットアップする
keywords: Microsoft Threat Protection 試用版のセットアップ、microsoft threat protection、Microsoft Threat Protection 評価ラボのセットアップの試行
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
ms.openlocfilehash: 6cba773d0c4bea259db151d5a8f1d8e03954a045
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717297"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="da3d8-104">Microsoft の脅威保護のテスト環境をセットアップする</span><span class="sxs-lookup"><span data-stu-id="da3d8-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="da3d8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="da3d8-105">**Applies to:**</span></span>
- <span data-ttu-id="da3d8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="da3d8-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="da3d8-107">Microsoft の脅威保護の試用ラボ環境を作成して展開することは、3つのフェーズのプロセスです。</span><span class="sxs-lookup"><span data-stu-id="da3d8-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護評価ラボの準備" />
      <br/><span data-ttu-id="da3d8-109">フェーズ 1: 準備</a></span><span class="sxs-lookup"><span data-stu-id="da3d8-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護評価ラボをセットアップする" />
      <br/><span data-ttu-id="da3d8-111">フェーズ 2: セットアップ</a></span><span class="sxs-lookup"><span data-stu-id="da3d8-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Microsoft の脅威保護のテスト環境とエンドポイントの各 Microsoft 脅威保護の柱を構成する" />
      <br/><span data-ttu-id="da3d8-113">フェーズ 3: 構成 & オンボード</a></span><span class="sxs-lookup"><span data-stu-id="da3d8-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="da3d8-114">現在、セットアップ段階になっています。</span><span class="sxs-lookup"><span data-stu-id="da3d8-114">You are currently in the set up phase.</span></span> <span data-ttu-id="da3d8-115">最初の手順を実行して、Microsoft 365 セキュリティセンターにアクセスし、試用ラボ環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="da3d8-116">Microsoft 365 E5 ライセンスにサインアップするために使用できる onmicrosoft.com テナントを生成するには、Office 365 または Azure Active Directory サブスクリプションにサインアップし*ます。*</span><span class="sxs-lookup"><span data-stu-id="da3d8-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="da3d8-117">既存の Office 365 または Azure Active Directory サブスクリプションを既にお持ちの場合は、「Office 365 E5 試用版テナントの作成」の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="da3d8-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="da3d8-118">このフェーズでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="da3d8-119">Office 365 E5 試用版テナントを作成する</span><span class="sxs-lookup"><span data-stu-id="da3d8-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="da3d8-120">Microsoft 365 試用版サブスクリプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="da3d8-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="da3d8-121">Office 365 E5 試用版テナントを作成する</span><span class="sxs-lookup"><span data-stu-id="da3d8-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="da3d8-122">既存の Office 365 または Azure Active Directory サブスクリプションを既にお持ちの場合は、「Office 365 E5 試用版テナントの作成」の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="da3d8-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="da3d8-123">[Office 365 E5 product ポータル](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)に移動し、**無料試用版**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="da3d8-124">![イメージ of_Office 365 E5 無料試用版ページ](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-124">![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="da3d8-125">メールアドレス (個人または企業) を入力して、試用版の登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="da3d8-126">[**アカウントの設定] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-126">Click **Set up account**.</span></span>
<span data-ttu-id="da3d8-127">![Image of_Office 365 E5 試用版登録の設定ページ](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-127">![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="da3d8-128">名、姓、勤務先電話番号、会社名、会社のサイズ、国または地域を入力します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Image of_Office 365 E5 試用版登録のセットアップページで、名前、電話番号、および会社の詳細を確認するページが表示されます。](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="da3d8-130">ここで設定した国または地域によって、Office 365 がホストされるデータセンターの地域が決まります。</span><span class="sxs-lookup"><span data-stu-id="da3d8-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="da3d8-131">検証の設定: テキストメッセージまたは呼び出しを使用して選択します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="da3d8-132">[**送信確認コード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="da3d8-133">![イメージ of_Office 365 E5 試用版の登録のセットアップページ確認の設定](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-133">![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="da3d8-134">テナントのカスタムドメイン名を設定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="da3d8-135">![イメージ of_Office 365 E5 試用版登録のセットアップページ。カスタムドメイン名を設定できます。](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-135">![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="da3d8-136">最初の id を設定します。これはテナントの全体管理者になります。</span><span class="sxs-lookup"><span data-stu-id="da3d8-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="da3d8-137">**名前**と**パスワード**を入力します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="da3d8-138">**[サインアップ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-138">Click **Sign up**.</span></span>
<span data-ttu-id="da3d8-139">![画像 of_Office 365 E5 試用版登録のセットアップページ。ビジネス id を設定できます。](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-139">![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)</span></span> <br>

7. <span data-ttu-id="da3d8-140">[**セットアップに移動**] をクリックして、Office 365 E5 試用版テナントのプロビジョニングを完了します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="da3d8-141">![Office のイメージ 365 E5 試用版の登録のセットアップページ [セットアップの開始] ボタンをクリックするように求める](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-141">![Image of Office 365 E5 trial registration setup page prompting to click Go Setup button](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="da3d8-142">会社のドメインを Office 365 テナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="da3d8-143">オプション[**既に所有**しているドメインを接続する] を選択し、ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="da3d8-144">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-144">Click **Next**.</span></span>
<br><span data-ttu-id="da3d8-145">![画像 of_Office 365 E5 セットアップページで、サインインとメールをカスタマイズする必要があります。](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-145">![Image of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="da3d8-146">ドメインの所有権を検証するには、TXT または MX レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da3d8-146">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="da3d8-147">ドメインに TXT または MX レコードを追加したら、[**検証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="da3d8-148">![イメージ of_Office 365 E5 セットアップページ。ドメインを確認するために MX レコードの TXT を追加する必要があります。](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-148">![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="da3d8-149">オプションテナントの追加のユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="da3d8-150">[**次へ**] をクリックすると、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="da3d8-150">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="da3d8-151">![[イメージ of_Office 365 E5 セットアップ] ページで、さらにユーザーを追加できます。](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-151">![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="da3d8-152">オプションOffice アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="da3d8-153">[**次へ**] をクリックして、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-153">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="da3d8-154">![Office アプリをインストールできる Image of_Office 365 E5 ページ](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-154">![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="da3d8-155">オプション電子メールメッセージを移行します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="da3d8-156">この手順を省略してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="da3d8-156">Again, you can skip this step.</span></span>
<br><span data-ttu-id="da3d8-157">![画像 of_Office 365 E5 電子メールメッセージを移行するかどうかを設定するには](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-157">![Image of_Office 365 E5 where you can set whether to migrate email messages or not](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="da3d8-158">[オンラインサービス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-158">Choose online services.</span></span> <span data-ttu-id="da3d8-159">[ **Exchange** ] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-159">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="da3d8-160">![画像 of_Office 365 E5 オンラインサービスを選択できます。](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-160">![Image of_Office 365 E5 where you can choose your online services](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="da3d8-161">MX、CNAME、および TXT レコードをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-161">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="da3d8-162">完了したら、[**検証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-162">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="da3d8-163">![Image of_Office 365 E5 ここに DNS レコードを追加できます。](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-163">![Image of_Office 365 E5 here you can add your DNS records](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="da3d8-164">おめでとうございます。 Office 365 テナントのプロビジョニングが完了しました。</span><span class="sxs-lookup"><span data-stu-id="da3d8-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="da3d8-165">![Image of_Office 365 E5 セットアップ完了確認ページ](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-165">![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="da3d8-166">Microsoft 365 試用版サブスクリプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="da3d8-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="da3d8-167">試用版にサインアップすると、1か月に使用する25ユーザーライセンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="da3d8-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="da3d8-168">詳細について[は、「Try Or Buy a M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da3d8-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="da3d8-169">[Microsoft 365 管理センター](https://admin.microsoft.com/)で、[**課金**] をクリックしてから [**購入サービス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="da3d8-170">[ **Microsoft 365 E5** ] を選択し、[**無料試用版の開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="da3d8-171">![Image of_Microsoft 365 E5 無料試用版ページ](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-171">![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="da3d8-172">検証の設定: テキストメッセージまたは呼び出しを使用して選択します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="da3d8-173">決定したら、電話番号を入力し、選択した内容に応じて [**自分のテキスト**を表示] または [**呼び出し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="da3d8-174">![Image of_Microsoft 365 E5 無料試用版ページを開き、ロボットではないことを証明するコードを送信するための連絡先の詳細を確認します。](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-174">![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="da3d8-175">確認コードを入力して、[**無料試用版の開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-175">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="da3d8-176">![Image of_Microsoft 365 E5 Start free 試用版のページでは、システムが送信した検証コードに記入して、ロボットではないことを証明することができます。](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-176">![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="da3d8-177">[**今すぐ試行**] をクリックして、Microsoft 365 E5 試用版を確認します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="da3d8-178">![Image of_Microsoft 365 E5 [無料試用版の開始] ページで、[今すぐ試行] ボタンを開始する必要があります。](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-178">![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="da3d8-179">**Microsoft 365 管理センター**  >  **ユーザー**の  >  **アクティブユーザー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="da3d8-180">ユーザーアカウントを選択し、[**製品ライセンスの管理**] を選択してから、ライセンスを Office 365 E5 から**Microsoft 365 e5**にスワップします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="da3d8-181">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-181">Click **Save**.</span></span>
<span data-ttu-id="da3d8-182">![Image of_Microsoft 365 管理センター] ページで、Microsoft 365 E5 ライセンスを選択できます。](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-182">![Image of_Microsoft 365 Admin Center page where you can select Microsoft 365 E5 license](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="da3d8-183">グローバル管理者アカウントをもう一度選択し、[**ユーザー名の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-183">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="da3d8-184">![Image of_Microsoft 365 管理センターページでは、アカウントを選択してから、ユーザー名を管理することができます。](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-184">![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="da3d8-185">オプション前の手順で選択した内容に応じて、ドメインを*onmicrosoft.com*から独自のドメインに変更します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="da3d8-186">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da3d8-186">Click **Save changes**.</span></span>
<br><span data-ttu-id="da3d8-187">![イメージ of_Microsoft 365 管理センターページで、ドメインの設定を変更することができます。](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-187">![Image of_Microsoft 365 Admin Center page where you can change your domain preference](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="da3d8-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="da3d8-188">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="da3d8-189">![フェーズ 3: 構成 & オンボード](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="da3d8-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="da3d8-190">フェーズ 3: 構成 & オンボード</span><span class="sxs-lookup"><span data-stu-id="da3d8-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="da3d8-191">Microsoft の脅威保護評価ラボとエンドポイントをオンボードにするために、Microsoft の各脅威保護の柱を構成します。</span><span class="sxs-lookup"><span data-stu-id="da3d8-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection evaluation lab and onboard your endpoints.</span></span>
