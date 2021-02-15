---
title: Office 2010 を Microsoft 365 にアップグレードする - Microsoft 365 管理者
f1.keywords:
- NOCSH
ms.author: kwekua
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
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 組織内のユーザーの最新の Microsoft Office クライアントにOfficeする方法について学習します。
ms.openlocfilehash: 3f8ea0d16e1c27414b5f3e11e842e336fadb3e75
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233320"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="9537e-103">ビジネス ユーザー向け Microsoft 365 を最新のクライアントにOfficeする</span><span class="sxs-lookup"><span data-stu-id="9537e-103">Upgrade your Microsoft 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="9537e-104">Office 2010 がサポート終了に達する</span><span class="sxs-lookup"><span data-stu-id="9537e-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="9537e-105">Office 2010 年 10 月 13 日にサポートが終了しました。</span><span class="sxs-lookup"><span data-stu-id="9537e-105">Office 2010 reached its end of support on October 13, 2020.</span></span> <span data-ttu-id="9537e-106">Microsoft は、次の機能を提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9537e-106">Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="9537e-107">問題に対するテクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="9537e-107">Technical support for issues</span></span>

- <span data-ttu-id="9537e-108">検出された問題のバグ修正</span><span class="sxs-lookup"><span data-stu-id="9537e-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="9537e-109">検出された脆弱性に対するセキュリティ修正プログラム</span><span class="sxs-lookup"><span data-stu-id="9537e-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="9537e-110">詳細 [Office 2010 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/endofsupport/office-2010-end-support-roadmap) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9537e-110">See [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/endofsupport/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="9537e-111">**これが適切なトピックですか?**</span><span class="sxs-lookup"><span data-stu-id="9537e-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="9537e-112">組織の Microsoft 365 for business サブスクリプションの管理者が適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="9537e-112">If you're the admin responsible for the Microsoft 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="9537e-113">管理者は、通常、ユーザーの管理、パスワードのリセット、Officeインストールの管理、ライセンスの追加または削除など、タスクを担当します。</span><span class="sxs-lookup"><span data-stu-id="9537e-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="9537e-114">管理者ではなく[、Microsoft 365 ファミリ](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans)製品をお持ちのお客様は、「Office[](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350)をアップグレードする方法」を参照して、以前の自宅使用バージョンの Office をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="9537e-114">If you're not an admin and you have a [Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) for information about upgrading your older, home use version of Office.</span></span>

## <a name="get-ready-to-upgrade-to-microsoft-365"></a><span data-ttu-id="9537e-115">Microsoft 365 にアップグレードする準備をする</span><span class="sxs-lookup"><span data-stu-id="9537e-115">Get ready to upgrade to Microsoft 365</span></span>

<span data-ttu-id="9537e-116">管理者は、組織内のユーザーがインストールOfficeバージョンを制御します。</span><span class="sxs-lookup"><span data-stu-id="9537e-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="9537e-117">Office 2010、Office 2013、Office 2016 など、以前のバージョンの Office を実行している組織内のユーザーが最新バージョンにアップグレードし、セキュリティと生産性の向上を活用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9537e-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="9537e-118">アップグレード手順</span><span class="sxs-lookup"><span data-stu-id="9537e-118">Upgrade steps</span></span>

<span data-ttu-id="9537e-p104">以下は、ユーザーが最新の Office デスクトップ クライアントにアップグレードするときのプロセスできます。アップグレード プロセスを開始する前に一読することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9537e-p104">The steps below will guide you through the process of upgrading your users to the latest Office desktop client. We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="9537e-121">手順 1 - システム要件の確認</span><span class="sxs-lookup"><span data-stu-id="9537e-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="9537e-122">[デバイスが最新バージョン](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) の Office互換性を持つかどうかを確認するには、デバイスのシステム要件を確認Office。</span><span class="sxs-lookup"><span data-stu-id="9537e-122">[Check the system requirements](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="9537e-123">たとえば、新しいバージョンのOffice Windows XP または Windows Vista を実行しているコンピューターにインストールできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9537e-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="9537e-124">組織内のユーザーが PC またはノート PC で以前のバージョンの Windows を実行している場合は、Windows 10 にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9537e-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="9537e-125">Windows 7 のサポートが終了しました。</span><span class="sxs-lookup"><span data-stu-id="9537e-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="9537e-126">詳 [しくは、2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 年 1 月に終了する Windows 7 のサポートをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9537e-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="9537e-127">オペレーティング システムを [アップグレードできる場合は、Windows 10](https://www.microsoft.com/windows/windows-10-specifications) のシステム要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9537e-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="9537e-128">アプリケーションの互換性の確認</span><span class="sxs-lookup"><span data-stu-id="9537e-128">Check application compatibility</span></span>

<span data-ttu-id="9537e-129">アップグレードを成功させるためには、VBA スクリプト、マクロ、サードパーティ アドイン、複雑な文書とスプレッドシートなど、Office のアプリケーションと最新版の Office との間に互換性があることを確認することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9537e-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="9537e-130">たとえば、現在インストールしている Office でサードパーティ アドインを利用している場合、最新版の Office に対応していることをメーカーにご確認ください。</span><span class="sxs-lookup"><span data-stu-id="9537e-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="9537e-131">手順 2 - 既存のサブスクリプション プランの確認</span><span class="sxs-lookup"><span data-stu-id="9537e-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="9537e-132">一部の Microsoft 365 プランにはデスクトップ版の Office が含まれますが、プランに Office が含されていない場合は、アップグレードの手順が異なります。</span><span class="sxs-lookup"><span data-stu-id="9537e-132">Some Microsoft 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="9537e-133">使用しているサブスクリプション プランが分からないか。</span><span class="sxs-lookup"><span data-stu-id="9537e-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="9537e-134">Microsoft [365 for Business サブスクリプションの内容を確認する](../admin-overview/what-subscription-do-i-have.md)</span><span class="sxs-lookup"><span data-stu-id="9537e-134">See [What Microsoft 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="9537e-135">既存のプランに Office が含まれる場合、「[手順 3 - Office をアンインストールする](#step-3---uninstall-office)」に移動してください。</span><span class="sxs-lookup"><span data-stu-id="9537e-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="9537e-136">既存のプランに Office が含まれていない場合、下のオプションから選択してください。</span><span class="sxs-lookup"><span data-stu-id="9537e-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="9537e-137">Office が含まれていないプランのアップグレード オプション</span><span class="sxs-lookup"><span data-stu-id="9537e-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="9537e-138">**オプション 1: サブスクリプションOffice切り替える**</span><span class="sxs-lookup"><span data-stu-id="9537e-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="9537e-139">Office を含むサブスクリプションに切り替えてください。</span><span class="sxs-lookup"><span data-stu-id="9537e-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="9537e-140">「 [別のビジネス向け Microsoft 365 プランに切り替える」を参照してください](../../commerce/subscriptions/switch-to-a-different-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="9537e-140">See [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="9537e-141">**オプション 2: ボリューム ライセンスを通じて、1 回の個別Office購入Office購入する**</span><span class="sxs-lookup"><span data-stu-id="9537e-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="9537e-142">アプリの個別の 1 回の購入Office。</span><span class="sxs-lookup"><span data-stu-id="9537e-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="9537e-143">「Office [Home &amp; Business](https://products.office.com/home-and-business) または [Office Professional」を参照](https://products.office.com/professional)</span><span class="sxs-lookup"><span data-stu-id="9537e-143">See [Office Home &amp; Business](https://products.office.com/home-and-business) or [Office Professional](https://products.office.com/professional)</span></span>

     <span data-ttu-id="9537e-144">または</span><span class="sxs-lookup"><span data-stu-id="9537e-144">OR</span></span>

 - <span data-ttu-id="9537e-145">ボリューム ライセンスで複数のOfficeを購入します。</span><span class="sxs-lookup"><span data-stu-id="9537e-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="9537e-146">「[ボリューム ライセンスで提供されるスイート製品の比較](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9537e-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="9537e-147">手順 3 - Office をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="9537e-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="9537e-148">最新バージョンの Office をインストールする前に、すべての古いバージョンのファイルをアンインストールすることをお勧Office。</span><span class="sxs-lookup"><span data-stu-id="9537e-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="9537e-149">ただし、Office のアップグレードに関する考え方が変わる場合は、アンインストール後にOfficeを再インストールできない場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9537e-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="9537e-150">サード パーティ製アドインがある場合は、製造元に問い合わせ、最新バージョンの Office で動作する更新プログラムがインストールされていないか確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9537e-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

> [!TIP]
> <span data-ttu-id="9537e-151">Office のアンインストール中に問題が発生した場合は、Microsoft サポート/回復アシスタント ツールを使用して Office の削除を支援できます [:Microsoft](https://go.microsoft.com/fwlink/?LinkID=2155008)サポート/回復アシスタントをダウンロードして実行します。</span><span class="sxs-lookup"><span data-stu-id="9537e-151">If you run into issues while uninstalling Office, you can use the Microsoft Support and Recovery Assistant tool to help you remove Office: [Download and run the Microsoft Support and Recovery Assistant](https://go.microsoft.com/fwlink/?LinkID=2155008).</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="9537e-152">アンインストールするバージョンの Office を選択します</span><span class="sxs-lookup"><span data-stu-id="9537e-152">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="9537e-153">PC から</span><span class="sxs-lookup"><span data-stu-id="9537e-153">From a PC</span></span>](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [<span data-ttu-id="9537e-154">Mac から</span><span class="sxs-lookup"><span data-stu-id="9537e-154">From a Mac</span></span>](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="9537e-155">以前のバージョンの Office をアンインストール後に再インストールできない既知の問題</span><span class="sxs-lookup"><span data-stu-id="9537e-155">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="9537e-156">**Officeライセンスを通じてライセンスを取得する** これらのボリューム ライセンス バージョンの Office のソース ファイルにアクセスできなくなった場合は、再インストールを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9537e-156">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="9537e-157">**Officeコンピューターにプレインストールされている場合** ディスクまたはプロダクト キーがなくなった場合 (Officeにインストールされている場合)、再インストールは行えなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9537e-157">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="9537e-158">**サポートされていないサブスクリプション** Office のコピーが、Office 365 Small Business Premium や Office 365 Mid-size Business などの廃止されたサブスクリプションを通じて取得された場合、サブスクリプションに付けられているプロダクト キーがない限り、古いバージョンの Office をインストールできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9537e-158">**Non-supported subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="9537e-p112">以前のバージョンの Office と最新版を共存させる場合、「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)」で、共存が可能なバージョンの一覧をご確認いただけます。たとえば、サードパーティ アドインをインストールして以前のバージョンの Office で使用しているとき、アドインと最新版の Office の間に互換性があるかどうかがわからない場合は、共存インストールが正しい選択となることがあります。</span><span class="sxs-lookup"><span data-stu-id="9537e-p112">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="9537e-161">手順 4 - Office ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9537e-161">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="9537e-162">まだライセンスを割り当てていない場合は、Office をインストールする必要がある組織内のユーザーにライセンスを割り当てる方法について詳しくは [、「Microsoft 365 for business](../manage/assign-licenses-to-users.md)でライセンスをユーザーに割り当てる」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9537e-162">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="9537e-163">手順 5 - Office をインストールする</span><span class="sxs-lookup"><span data-stu-id="9537e-163">Step 5 - Install Office</span></span>

<span data-ttu-id="9537e-164">すべてのライセンスを持つユーザーをアップグレードすることを確認した後、最後の手順として、ユーザーに Office をインストールします [。「PC](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)または Mac に Office をダウンロードしてインストールまたは再インストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9537e-164">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span>
  
> [!TIP]
> <span data-ttu-id="9537e-165">ユーザーが自分でインストールする必要Office、Office [365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)でソフトウェアダウンロード設定を管理するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9537e-165">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="9537e-166">[Office](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool)展開ツールを使用して Office ソフトウェアをローカル ネットワークにダウンロードし、通常使用するソフトウェア展開方法を使用して Office を展開できます。</span><span class="sxs-lookup"><span data-stu-id="9537e-166">You can use the [Office Deployment Tool](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>
