---
title: Microsoft 365 for business ユーザーを最新の Office クライアントにアップグレードする
f1.keywords:
- NOCSH
ms.author: kwekuako
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: ユーザーを最新の Office クライアントにアップグレードする方法について説明します。
ms.openlocfilehash: 148069011784b822c5ce366190afd60bf278772f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627536"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="a359e-103">Microsoft 365 for business ユーザーを最新の Office クライアントにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="a359e-103">Upgrade your Microsoft 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="a359e-104">Office 2010 がサポート終了に到達した</span><span class="sxs-lookup"><span data-stu-id="a359e-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="a359e-105">Office 2010 は、2020年10月13日にサポート終了日に到達します。</span><span class="sxs-lookup"><span data-stu-id="a359e-105">Office 2010 will reach its end of support on October 13, 2020.</span></span> <span data-ttu-id="a359e-106">Office 2010 がサポートの終了に達すると、Microsoft は次のものを提供しなくなります。</span><span class="sxs-lookup"><span data-stu-id="a359e-106">When Office 2010 reaches its end of support, Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="a359e-107">問題のテクニカルサポート</span><span class="sxs-lookup"><span data-stu-id="a359e-107">Technical support for issues</span></span>

- <span data-ttu-id="a359e-108">検出された問題に対するバグ修正</span><span class="sxs-lookup"><span data-stu-id="a359e-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="a359e-109">検出された脆弱性に対するセキュリティ修正プログラム</span><span class="sxs-lookup"><span data-stu-id="a359e-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="a359e-110">詳細については、「 [Office 2010 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-110">See [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="a359e-111">**これは適切なトピックですか。**</span><span class="sxs-lookup"><span data-stu-id="a359e-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="a359e-112">お客様が組織の Microsoft 365 for business サブスクリプションを担当する管理者である場合は、適切な場所に配置されています。</span><span class="sxs-lookup"><span data-stu-id="a359e-112">If you're the admin responsible for the Microsoft 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="a359e-113">通常、管理者は、ユーザーの管理、パスワードのリセット、Office のインストールの管理、ライセンスの追加または削除などのタスクを担当します。</span><span class="sxs-lookup"><span data-stu-id="a359e-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="a359e-114">管理者ではなく、 [Microsoft 365 ファミリ](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans)製品を使用している場合は、「office をアップグレードする方法について」を参照してください。以前のバージョンの office をアップグレードする方法については、「office の[アップグレード方法](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-114">If you're not an admin and you have a [Microsoft 365 Family](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) for information about upgrading your older, home use version of Office.</span></span>

## <a name="get-ready-to-upgrade"></a><span data-ttu-id="a359e-115">アップグレードの準備をする</span><span class="sxs-lookup"><span data-stu-id="a359e-115">Get ready to upgrade</span></span>

<span data-ttu-id="a359e-116">管理者は、組織内のどのバージョンの Office ユーザーがインストールできるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a359e-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="a359e-117">Office 2010、Office 2013、または Office 2016 を最新バージョンにアップグレードするなど、以前のバージョンの Office を実行している組織内のユーザーが、セキュリティと生産性の向上を活かすことができるようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a359e-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="a359e-118">アップグレード手順</span><span class="sxs-lookup"><span data-stu-id="a359e-118">Upgrade steps</span></span>

<span data-ttu-id="a359e-p104">以下は、ユーザーが最新の Office デスクトップ クライアントにアップグレードするときのプロセスできます。アップグレード プロセスを開始する前に一読することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a359e-p104">The steps below will guide you through the process of upgrading your users to the latest Office desktop client. We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="a359e-121">手順 1 - システム要件の確認</span><span class="sxs-lookup"><span data-stu-id="a359e-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="a359e-122">Office の[システム要件をチェック](https://products.office.com/office-system-requirements)して、デバイスが最新バージョンの office と互換性があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-122">[Check the system requirements](https://products.office.com/office-system-requirements) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="a359e-123">たとえば、Windows XP または Windows Vista を実行しているコンピューターに新しいバージョンの Office をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a359e-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="a359e-124">組織内のユーザーが Pc またはラップトップで以前のバージョンの Windows を実行している場合は、Windows 10 にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a359e-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="a359e-125">Windows 7 のサポートが終了しました。</span><span class="sxs-lookup"><span data-stu-id="a359e-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="a359e-126">詳細については、「 [2020 年1月の Windows 7 のサポート」](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="a359e-127">オペレーティングシステムをアップグレードできるかどうかを確認するには、 [Windows 10 のシステム要件](https://www.microsoft.com/windows/windows-10-specifications)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="a359e-128">アプリケーションの互換性の確認</span><span class="sxs-lookup"><span data-stu-id="a359e-128">Check application compatibility</span></span>

<span data-ttu-id="a359e-129">アップグレードを成功させるためには、VBA スクリプト、マクロ、サードパーティ アドイン、複雑な文書とスプレッドシートなど、Office のアプリケーションと最新版の Office との間に互換性があることを確認することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="a359e-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="a359e-130">たとえば、現在インストールしている Office でサードパーティ アドインを利用している場合、最新版の Office に対応していることをメーカーにご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a359e-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="a359e-131">手順 2 - 既存のサブスクリプション プランの確認</span><span class="sxs-lookup"><span data-stu-id="a359e-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="a359e-132">一部の Microsoft 365 プランには、デスクトップ版の完全な Office は含まれていません。また、アップグレードの手順は、プランに Office が含まれていない場合には異なります。</span><span class="sxs-lookup"><span data-stu-id="a359e-132">Some Microsoft 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="a359e-133">必要なサブスクリプションプランがわからない場合</span><span class="sxs-lookup"><span data-stu-id="a359e-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="a359e-134">所有して[いる Microsoft 365 for business サブスクリプションを](../admin-overview/what-subscription-do-i-have.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-134">See [What Microsoft 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="a359e-135">既存のプランに Office が含まれる場合、「[手順 3 - Office をアンインストールする](#step-3---uninstall-office)」に移動してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="a359e-136">既存のプランに Office が含まれていない場合、下のオプションから選択してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="a359e-137">Office が含まれていないプランのアップグレード オプション</span><span class="sxs-lookup"><span data-stu-id="a359e-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="a359e-138">**オプション 1: Office サブスクリプションを切り替える**</span><span class="sxs-lookup"><span data-stu-id="a359e-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="a359e-139">Office を含むサブスクリプションに切り替えてください。</span><span class="sxs-lookup"><span data-stu-id="a359e-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="a359e-140">「[別の Microsoft 365 for business プランへの切り替え」を](../../commerce/subscriptions/switch-to-a-different-plan.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-140">See [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="a359e-141">**オプション 2: 個人または1回の Office の購入を購入するか、ボリュームライセンスを使用して Office を購入する**</span><span class="sxs-lookup"><span data-stu-id="a359e-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="a359e-142">Office の個別の1回の購入を購入します。</span><span class="sxs-lookup"><span data-stu-id="a359e-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="a359e-143">「 [Office Home &amp; Business](https://products.office.com/home-and-business)または[office Professional](https://products.office.com/professional) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-143">See [Office Home &amp; Business](https://products.office.com/home-and-business) or [Office Professional](https://products.office.com/professional)</span></span>

     <span data-ttu-id="a359e-144">OR</span><span class="sxs-lookup"><span data-stu-id="a359e-144">OR</span></span>

 - <span data-ttu-id="a359e-145">ボリュームライセンスを使用して、Office の複数のコピーを購入します。</span><span class="sxs-lookup"><span data-stu-id="a359e-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="a359e-146">「[ボリューム ライセンスで提供されるスイート製品の比較](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a359e-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="a359e-147">手順 3 - Office をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="a359e-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="a359e-148">Office の最新バージョンをインストールする前に、以前のバージョンの Office をすべてアンインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a359e-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="a359e-149">ただし、Office のアップグレードに関する注意事項を変更した場合は、次のような状況で、アンインストール後に Office を再インストールできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="a359e-150">サードパーティのアドインを使用している場合は、最新バージョンの Office で動作する更新プログラムがあるかどうかを製造元に問い合わせて確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a359e-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="a359e-151">アンインストールするバージョンの Office を選択します</span><span class="sxs-lookup"><span data-stu-id="a359e-151">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="a359e-152">PC から</span><span class="sxs-lookup"><span data-stu-id="a359e-152">From a PC</span></span>](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [<span data-ttu-id="a359e-153">Mac から</span><span class="sxs-lookup"><span data-stu-id="a359e-153">From a Mac</span></span>](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="a359e-154">以前のバージョンの Office をアンインストール後に再インストールできない既知の問題</span><span class="sxs-lookup"><span data-stu-id="a359e-154">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="a359e-155">**ボリュームライセンスを使用した Office**これらのボリュームライセンスバージョンの Office のソースファイルにアクセスできなくなった場合は、再インストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a359e-155">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="a359e-156">**コンピューターにプレインストールされている Office**ディスクまたはプロダクトキーがない場合 (Office がある場合)、再インストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a359e-156">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="a359e-157">**サポートされていないサブスクリプション**Office のコピーが、Office 365 Small Business Premium または Office 365 の中規模企業など、廃止されたサブスクリプションを通じて取得した場合、サブスクリプションに付属のプロダクトキーを使用していない限り、以前のバージョンの Office をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a359e-157">**Non-supported subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="a359e-p112">以前のバージョンの Office と最新版を共存させる場合、「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx)」で、共存が可能なバージョンの一覧をご確認いただけます。たとえば、サードパーティ アドインをインストールして以前のバージョンの Office で使用しているとき、アドインと最新版の Office の間に互換性があるかどうかがわからない場合は、共存インストールが正しい選択となることがあります。</span><span class="sxs-lookup"><span data-stu-id="a359e-p112">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx). A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="a359e-160">手順 4 - Office ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a359e-160">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="a359e-161">まだインストールしていない場合は、Office をインストールする必要がある組織内のユーザーにライセンスを割り当てます。詳細については、「 [Microsoft 365 for business でユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-161">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="a359e-162">手順 5 - Office をインストールする</span><span class="sxs-lookup"><span data-stu-id="a359e-162">Step 5 - Install Office</span></span>

<span data-ttu-id="a359e-163">アップグレードするユーザーにライセンスがあることを確認したら、最後に Office をインストールするには、「 [PC または Mac に office をダウンロードしてインストールまたは再](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)インストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-163">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).</span></span>
  
> [!TIP]
> <span data-ttu-id="a359e-164">ユーザーに Office をインストールさせたくない場合は、「 [Manage software download settings In office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a359e-164">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="a359e-165">Office[展開ツール](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool)を使用して office ソフトウェアをローカルネットワークにダウンロードし、通常使用するソフトウェア展開方法を使用して office を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="a359e-165">You can use the [Office Deployment Tool](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>
