---
title: Microsoft 365 for business のセットアップを計画する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: ビジネス向け Microsoft 365 への移行に関する要件と考慮事項について説明します。
ms.openlocfilehash: b4d2b5d500b73b62c67d3f8126b6313484e2bc78
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297034"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a><span data-ttu-id="ba50c-103">Microsoft 365 for business のセットアップを計画する</span><span class="sxs-lookup"><span data-stu-id="ba50c-103">Plan your setup of Microsoft 365 for business</span></span>

<span data-ttu-id="ba50c-104">この記事は、Microsoft 365 for business プランを購読しているユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="ba50c-104">This article is for people who have subscribed to a Microsoft 365 for business plan.</span></span>
  
<span data-ttu-id="ba50c-105">組織を Microsoft 365 に移行する前に、満たす必要がある要件、必要な情報、および決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba50c-105">Before moving your organization to Microsoft 365, there are requirements you need to meet, info you need to have on hand, and decisions you have to make.</span></span>


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a><span data-ttu-id="ba50c-106">セットアップ ウィザードを実行する前に必要な情報</span><span class="sxs-lookup"><span data-stu-id="ba50c-106">Info to have on hand before you run the setup wizard</span></span>

<span data-ttu-id="ba50c-107">セットアップ ウィザードを実行し、ドメインを Microsoft 365 に移動する準備ができたら、必要な情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-107">When you're ready to run the setup wizard and move your domain to Microsoft 365, here's the info you'll need to have on hand:</span></span>
  
- <span data-ttu-id="ba50c-108">Microsoft 365 に追加するユーザーの一覧。</span><span class="sxs-lookup"><span data-stu-id="ba50c-108">List of people you want to add to Microsoft 365.</span></span> <span data-ttu-id="ba50c-109">Microsoft 365 に追加済みの場合でも、ドメイン情報を更新する場合は、ここに名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba50c-109">Even if you've already added them to Microsoft 365, if you're updating your domain information, you need to enter their names here.</span></span>

- <span data-ttu-id="ba50c-110">従業員がサインインできるよう、従業員にユーザー ID とパスワードを通知する方法。</span><span class="sxs-lookup"><span data-stu-id="ba50c-110">How you're going to notify your employees of their user ID and password so they can sign in.</span></span> <span data-ttu-id="ba50c-111">情報を使用してそれらを呼び出すつもりですか?</span><span class="sxs-lookup"><span data-stu-id="ba50c-111">Are you going to call them with the info?</span></span> <span data-ttu-id="ba50c-112">または、個人の電子メール アドレスに送信しますか?</span><span class="sxs-lookup"><span data-stu-id="ba50c-112">Or send it to their personal email address?</span></span> <span data-ttu-id="ba50c-113">メールにアクセスできないので、使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ba50c-113">They won't have access to their email, so you can't use that.</span></span>

- <span data-ttu-id="ba50c-114">組織のドメイン名 (contoso.com **など)** を持ち、Microsoft メールの使用を計画している場合は、ドメインが登録されている場所を知り、サインイン情報を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba50c-114">If you have a domain name for your organization (such as contoso.com) **and** you plan on using Microsoft email, you'll need to know where your domain is registered and have sign-in information.</span></span>

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a><span data-ttu-id="ba50c-115">Microsoft 365 セットアップ ウィザードを実行するとどうなるか</span><span class="sxs-lookup"><span data-stu-id="ba50c-115">What happens when you run the Microsoft 365 setup wizard</span></span>

<span data-ttu-id="ba50c-116">セットアップ ウィザードでは、Microsoft 365 アプリをコンピューターにインストールし、ドメインの追加と検証、ユーザーの追加とライセンスの割り当て、ドメインの接続について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-116">The setup wizard walks you through installing the Microsoft 365 apps on your computer, adding and verifying your domain, adding users and assigning licenses to them, and connecting your domain.</span></span>

> [!NOTE]
> <span data-ttu-id="ba50c-117">Microsoft [365](../add-users/assign-admin-roles.md) for business の管理者ロールをウィザードで追加したユーザーに割り当てる必要がある場合は、後で [ユーザー] ページで **行** います。</span><span class="sxs-lookup"><span data-stu-id="ba50c-117">If you need to [Assign admin roles in Microsoft 365 for business](../add-users/assign-admin-roles.md) to the users you add in the wizard, you can do that later on the **Users** page.</span></span> 
  
<span data-ttu-id="ba50c-118">セットアップ ウィザードを完了しない場合は、管理センターのセットアップからいつでもセットアップ [タスクを完了](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **できます**。</span><span class="sxs-lookup"><span data-stu-id="ba50c-118">If you don't complete the setup wizard, you can complete setup tasks at any time from [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) > **Setup**.</span></span> <span data-ttu-id="ba50c-119">ここから、別のメール サービスからメールと連絡先を移行したり、管理者アカウントのドメインを変更したり、請求情報を管理したり、ユーザーを追加または削除したり、パスワードをリセットしたり、その他のビジネス機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-119">From here you can migrate email and contacts from another email service, change the domain of your admin account, manage your billing information, add or remove users, reset passwords, and do other business functions.</span></span> <span data-ttu-id="ba50c-120">セットアップ ウィザードとセットアップ ページの違いの詳細については[、「Microsoft 365](o365-setup-wizard-and-setup-page.md)セットアップ ウィザードとセットアップ ページの違い」を参照してください。 </span><span class="sxs-lookup"><span data-stu-id="ba50c-120">For more information about the differences between the setup wizard and the **Setup** page, see [Differences between the Microsoft 365 setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

<span data-ttu-id="ba50c-p104">お困りの場合は、Microsoft にご連絡ください。[お役に立つことができれば幸いです。](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="ba50c-p104">If you get stuck at any point, call us. [We're here to help!](../../business-video/get-help-support.md)</span></span>
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a><span data-ttu-id="ba50c-123">セットアップ ウィザードを使用しない場合 Active Directory 同期とハイブリッド環境</span><span class="sxs-lookup"><span data-stu-id="ba50c-123">When not to use the setup wizard: Active Directory synchronization and hybrid environments</span></span>

<span data-ttu-id="ba50c-124">データまたはユーザーをオンプレミス環境から移行するか、ディレクトリ同期を含むハイブリッド システムをセットアップするシナリオが複数存在します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-124">There are a couple of scenarios that include either migrating data or users from on-premises environments or setting up a hybrid system that includes directory synchronization.</span></span> <span data-ttu-id="ba50c-125">いずれかのカテゴリに入っている場合は、次の記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ba50c-125">If you're in either category, follow the instructions in these articles:</span></span>
  
- <span data-ttu-id="ba50c-126">オンプレミスの Active Directory とのディレクトリ同期を設定するには、「Microsoft 365 のディレクトリ同期をセットアップする」を参照し [、Microsoft 365](../../enterprise/set-up-directory-synchronization.md)の異なる ID モデルを理解するには [、「Microsoft 365 IDENTITY](../../enterprise/about-microsoft-365-identity.md)と Azure Active Directory について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-126">To set up directory synchronization with your on-premises Active Directory, see [Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md), and to understand the different identity models in Microsoft 365, read [Understanding Microsoft 365 identity and Azure Active Directory](../../enterprise/about-microsoft-365-identity.md).</span></span>

- <span data-ttu-id="ba50c-127">Exchange ハイブリッドを設定するには、ハイブリッド Exchange を設定する (DNS レコードの設定を含む) 異なるいくつかの方法のすべてについて説明した「[Exchange Server 展開アシスタント](/exchange/exchange-deployment-assistant)」の詳しい手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-127">To set-up an Exchange hybrid, the full set of instructions that guide you through all the different ways of setting up a hybrid exchange (including setting up DNS records) can be found here: [Exchange Server Deployment Assistant](/exchange/exchange-deployment-assistant)</span></span>

- <span data-ttu-id="ba50c-128">SharePoint ハイブリッド、特にハイブリッド検索機能とサイト機能を設定するには、「[SharePoint のハイブリッド検索](/SharePoint/hybrid/hybrid-search-in-sharepoint)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-128">To set up a SharePoint hybrid, particularly hybrid search and site features, see [Hybrid Search in SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint).</span></span>

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a><span data-ttu-id="ba50c-129">Microsoft 365 に一度または複数の段階で移動する</span><span class="sxs-lookup"><span data-stu-id="ba50c-129">Move to Microsoft 365 all at once or in stages</span></span>

- <span data-ttu-id="ba50c-130">**組織を Microsoft 365 に一度に移動しますか?**</span><span class="sxs-lookup"><span data-stu-id="ba50c-130">**Do you want to move your organization to Microsoft 365 all at once?**</span></span> <span data-ttu-id="ba50c-131">その場合は、ドメインを Microsoft 365 に簡単に移動する予定です。</span><span class="sxs-lookup"><span data-stu-id="ba50c-131">If so, then plan to move your domain to Microsoft 365 right away.</span></span> <span data-ttu-id="ba50c-132">まず、Microsoft 365 セットアップ ウィザードを実行します。ドメインのセットアップを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-132">Start by running the Microsoft 365 setup wizard; it will prompt you to set up your domain.</span></span>

- <span data-ttu-id="ba50c-133">**Microsoft 365 に徐々に移行しますか?**</span><span class="sxs-lookup"><span data-stu-id="ba50c-133">**Do you want to move to Microsoft 365 gradually?**</span></span> <span data-ttu-id="ba50c-134">ステージで Microsoft 365 に移行する場合は、Microsoft 365 セットアップ ウィザードの実行をスキップし、次の順序で Microsoft 365 機能の採用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-134">If you want to move to Microsoft 365 in stages, then skip running the Microsoft 365 setup wizard and consider adopting Microsoft 365 features in the following order:</span></span>

    1. <span data-ttu-id="ba50c-135">[Microsoft 365 に従業員を追加して](../add-users/add-users.md) 、ユーザーがアプリをダウンロードしてインストールOfficeします。</span><span class="sxs-lookup"><span data-stu-id="ba50c-135">[Add your employees to Microsoft 365](../add-users/add-users.md) so they can download and install the Office apps.</span></span>

    2. <span data-ttu-id="ba50c-136">コンピューターやデバイスで Word、Excel、および PowerPoint を使用するために、[Office アプリをダウンロードして、インストール](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-136">[Download and install the Office apps](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) to use Word, Excel, and PowerPoint on your computer and devices.</span></span>

    3. <span data-ttu-id="ba50c-137">[会議に使用する Microsoft Teams](#plan-for-teams) をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ba50c-137">[Set up Microsoft Teams](#plan-for-teams) to use for your meetings.</span></span>

    4. <span data-ttu-id="ba50c-138">[コンテンツを Microsoft 365 クラウド](set-up-file-storage-and-sharing.md) ストレージ (OneDrive または SharePoint チーム サイト) に移動します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-138">[Move your content to Microsoft 365 cloud storage](set-up-file-storage-and-sharing.md) (OneDrive or SharePoint team sites).</span></span>

    5. <span data-ttu-id="ba50c-139">準備ができたら、管理センターで左側の[](https://go.microsoft.com/fwlink/p/?linkid=2024339)ナビゲーション ウィンドウで[セットアップ] を選択し、[セットアップ] ページを使用してドメインとメール[を移動します](add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-139">When you're ready, in the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left navigation pane, and use the **Setup** page to [move your domain and email](add-domain.md).</span></span>

## <a name="check-that-your-devices-meet-system-requirements"></a><span data-ttu-id="ba50c-140">デバイスがシステム要件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="ba50c-140">Check that your devices meet system requirements</span></span>

<span data-ttu-id="ba50c-141">組織内の各ユーザーは、Office 2016 スイートのアプリ (Word、Excel、PowerPoint など) を最大 5 台の PC と Mac にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-141">Each person in your organization can install the Office 2016 suite of apps (Word, Excel, PowerPoint, and so on) on up to five PCs and Macs.</span></span> <span data-ttu-id="ba50c-142">法人向け [Office 2016 スイート](https://go.microsoft.com/fwlink/?LinkId=534827)をインストールするためのオペレーティング システムおよびコンピューターの要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-142">See the operating system and computer requirements for installing [Office 2016 suites](https://go.microsoft.com/fwlink/?LinkId=534827) for business.</span></span>
  
<span data-ttu-id="ba50c-143">モバイル アプリは、iOS、Android、および Windows デバイスにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-143">Mobile apps can be installed on iOS, Android, and Windows devices.</span></span> <span data-ttu-id="ba50c-144">モバイル デバイスとブラウザーのサポートについては、「[Office のシステム要件](https://go.microsoft.com/fwlink/?LinkId=534827)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-144">You can find information on mobile device and browser support in [System requirements for Office](https://go.microsoft.com/fwlink/?LinkId=534827).</span></span>
  
## <a name="plan-for-email"></a><span data-ttu-id="ba50c-145">メールの計画</span><span class="sxs-lookup"><span data-stu-id="ba50c-145">Plan for email</span></span>

<span data-ttu-id="ba50c-146">既存のメール サービスから Microsoft 365 への移行を計画している場合は、通常、切り替えに 2 日かかる。</span><span class="sxs-lookup"><span data-stu-id="ba50c-146">If you're planning to move from an existing email service to Microsoft 365, it usually takes two days to make the switch.</span></span>
  
### <a name="plan-for-email-downtime"></a><span data-ttu-id="ba50c-147">メールのダウンタイムの計画</span><span class="sxs-lookup"><span data-stu-id="ba50c-147">Plan for email downtime</span></span>
  
<span data-ttu-id="ba50c-148">メールに Microsoft 365 を使用する場合:</span><span class="sxs-lookup"><span data-stu-id="ba50c-148">If you're going to use Microsoft 365 for your email:</span></span>
  
- <span data-ttu-id="ba50c-149">ビジネス用メール アドレス *(rob \@ contoso.com* など) を別のメール サービスから Microsoft 365 に移動するには、新しい Microsoft 365 メールボックスにメールを配信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba50c-149">To move your business email address (such as *rob\@contoso.com*) from another email service to Microsoft 365, you need to direct your mail to be delivered to your new Microsoft 365 mailbox.</span></span> <span data-ttu-id="ba50c-150">これを行うには、[セットアップ]ページで [ユーザーのデータを移行する] を選択します。ここでは、ドメイン ホストで行う必要がある更新プログラムについて、手順に従って説明します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-150">You do this by selecting **Migrate your users' data** on the **Setup** page, where we guide you through the updates you need to make at your domain host, step by step.</span></span>

- <span data-ttu-id="ba50c-151">ドメイン ホストの更新後、変更は通常 1、2 時間で有効になります。</span><span class="sxs-lookup"><span data-stu-id="ba50c-151">After you update your domain host, the changes typically take effect in just an hour or two.</span></span> <span data-ttu-id="ba50c-152">ただし、変更がインターネット上で更新されるのに最大で 72 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba50c-152">But be aware that it can sometimes take up to 72 hours for the changes to update across the internet.</span></span>

- <span data-ttu-id="ba50c-153">電子メールのダウンタイムが発生する可能性がある場合は、メールの受信が少ない夜間または週末に Microsoft メールに切り替える予定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ba50c-153">Because you might have email downtime, we recommend you plan to switch to Microsoft email during an evening or weekend when you receive fewer emails.</span></span>

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a><span data-ttu-id="ba50c-154">既存のメール、連絡先、予定表の移行の計画</span><span class="sxs-lookup"><span data-stu-id="ba50c-154">Plan to move your existing email, contacts, and calendar</span></span>
  
<span data-ttu-id="ba50c-155">メール アカウントに Microsoft 365 を使用する場合は、既存のメール、連絡先、予定表を持参できます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-155">If you're going to use Microsoft 365 for your email account, you can bring your existing email, contacts, and calendar with you.</span></span> <span data-ttu-id="ba50c-156">[ **セットアップ]** ページは、ほとんどのシナリオで既存のメールと連絡先を移動するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-156">The **Setup** page helps you move your existing email and contacts for most scenarios.</span></span> <span data-ttu-id="ba50c-157">また、1 つまたは複数のメールボックスを移行するためのステップ バイ ステップ ガイドも用意しています。</span><span class="sxs-lookup"><span data-stu-id="ba50c-157">We also have step-by-step guides to move one or many mailboxes.</span></span>
  
|<span data-ttu-id="ba50c-158">**メールボックスの数**</span><span class="sxs-lookup"><span data-stu-id="ba50c-158">**How many mailboxes?**</span></span>|<span data-ttu-id="ba50c-159">**推奨事項**</span><span class="sxs-lookup"><span data-stu-id="ba50c-159">**Recommendation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba50c-160">少数</span><span class="sxs-lookup"><span data-stu-id="ba50c-160">Just a few</span></span>  <br/> |<span data-ttu-id="ba50c-161">[セットアップ] ページを使用してメールボックスを移行しない場合は、メールボックスの所有者が自分の電子メールと連絡先を移行できます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-161">If you don't want to use the **Setup** page to migrate the mailboxes, you can let mailbox owners migrate their own email and contacts.</span></span> <span data-ttu-id="ba50c-162">「 [メールと連絡先を Microsoft 365 for business に移行する」を参照してください](migrate-email-and-contacts-admin.md)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-162">See [Migrate email and contacts to Microsoft 365 for business](migrate-email-and-contacts-admin.md).</span></span>  <br/> |
|<span data-ttu-id="ba50c-163">やや少数</span><span class="sxs-lookup"><span data-stu-id="ba50c-163">Several</span></span>  <br/> |<span data-ttu-id="ba50c-164">Gmail から移行する場合は、「G Suite メールボックスを [Microsoft 365 に移行する」を参照してください](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-164">If you're migrating from Gmail, see [Migrate G Suite mailboxes to Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).</span></span>  <br/> <span data-ttu-id="ba50c-165">Exchange を含む別の電子メール プロバイダーから移行する場合は、「複数の電子メール アカウントを [Microsoft 365](/Exchange/mailbox-migration/mailbox-migration)に移行する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-165">If you're migrating from another email provider, including Exchange, see [Ways to migrate multiple email accounts to Microsoft 365](/Exchange/mailbox-migration/mailbox-migration).</span></span>  <br/> |

## <a name="plan-for-file-storage-and-migration"></a><span data-ttu-id="ba50c-166">ファイル ストレージと移行の計画</span><span class="sxs-lookup"><span data-stu-id="ba50c-166">Plan for file storage and migration</span></span>

<span data-ttu-id="ba50c-167">Microsoft 365 は、個人、小規模組織、および企業向けクラウド ストレージを提供します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-167">Microsoft 365 provides cloud storage for individuals, small organizations, and enterprises.</span></span> <span data-ttu-id="ba50c-168">保存場所のガイダンスについては [、「Microsoft 365](../../business-video/store-files.md)でドキュメントを保存できる場所」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-168">For guidance about what to store where, see [Where you can store documents in Microsoft 365](../../business-video/store-files.md).</span></span>
  
- <span data-ttu-id="ba50c-169">**何百ものファイルを** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) または [SharePoint チーム サイトに移動できます](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-169">**You can move hundreds of files** to [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) or to a [SharePoint team site](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242).</span></span> <span data-ttu-id="ba50c-170">一度に 100 個のファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-170">You can upload 100 files at a time.</span></span> <span data-ttu-id="ba50c-171">ただし、ファイルの既定の最大サイズである 2 GB を超えるファイルはアップロードしないでください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-171">Avoid uploading files larger than 2GB, which is the maximum file size by default.</span></span>
  
- <span data-ttu-id="ba50c-172">**数千のファイルを** Microsoft 365 ストレージに移動する場合は [、SharePoint Online の制限を確認してください](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-172">**If you want to move several thousand files** to Microsoft 365 storage, review the [SharePoint Online Limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).</span></span> <span data-ttu-id="ba50c-173">移行ツールを使用するか、または移行を支援する[パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ba50c-173">We recommend that you use a migration tool or consider hiring a [partner](https://go.microsoft.com/fwlink/?linkid=391089) to help you with the migration.</span></span> <span data-ttu-id="ba50c-174">大量のファイルを移行する方法については、「[SharePoint Online および OneDrive 移行ユーザー ガイド](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-174">For information about how to migrate a large number of files, see [SharePoint Online and OneDrive Migration User Guide](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).</span></span>
  
## <a name="plan-for-teams"></a><span data-ttu-id="ba50c-175">Teams の計画</span><span class="sxs-lookup"><span data-stu-id="ba50c-175">Plan for Teams</span></span>

<span data-ttu-id="ba50c-176">Microsoft Teams を使用して、サブスクリプションに参加している組織内の他のユーザーに通話を行います。</span><span class="sxs-lookup"><span data-stu-id="ba50c-176">You can use Microsoft Teams to make calls to other people in your organization who are on your subscription.</span></span> <span data-ttu-id="ba50c-177">たとえば、組織に 10 人のユーザーがある場合は、特別なセットアップを行わずに Teams を使用して互いに通話と IM を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-177">For example, if your organization has 10 people, you can call and IM each other using Teams without any special setup.</span></span> <span data-ttu-id="ba50c-178">詳細については、「Microsoft Teams の使用 [を開始する」を参照してください](/MicrosoftTeams/get-started-with-teams-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-178">For more information, see [Get started with Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start).</span></span>

<span data-ttu-id="ba50c-179">大規模な組織の場合、または Skype for Business、オンプレミス、またはハイブリッド展開から始める場合は [、「How to roll out Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba50c-179">For larger organizations or if you're starting from Skype for Business, on-premises, or hybrid deployments, see [How to roll out Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams).</span></span>
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a><span data-ttu-id="ba50c-180">Active Directory やその他のソフトウェアとの統合の計画</span><span class="sxs-lookup"><span data-stu-id="ba50c-180">Plan for integration with Active Directory or other software</span></span>

- <span data-ttu-id="ba50c-181">**オンプレミスの Active Directory と統合しますか?**</span><span class="sxs-lookup"><span data-stu-id="ba50c-181">**Do you want to integrate with your on-premises Active Directory?**</span></span> <span data-ttu-id="ba50c-182">Azure Active Directory Connect を使用して、オンプレミスの Active Directory を Microsoft 365 と統合できます。</span><span class="sxs-lookup"><span data-stu-id="ba50c-182">You can integrate your on-premises Active Directory with Microsoft 365 by using Azure Active Directory Connect.</span></span> <span data-ttu-id="ba50c-183">手順については [、「Microsoft 365 のディレクトリ同期をセットアップする」を参照してください](../../enterprise/set-up-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-183">For instructions, see [Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md).</span></span>
  
- <span data-ttu-id="ba50c-184">**Microsoft 365 と他の会社製のソフトウェアを統合しますか?**</span><span class="sxs-lookup"><span data-stu-id="ba50c-184">**Do you want to integrate Microsoft 365 with software made by other companies?**</span></span> <span data-ttu-id="ba50c-185">Microsoft 365 を組織内の他のソフトウェアと統合する必要がある場合は、[](https://go.microsoft.com/fwlink/?linkid=391089)展開に役立つパートナーを採用することを検討することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ba50c-185">If you need to integrate Microsoft 365 with other software in your organization, we recommend you consider [hiring a partner](https://go.microsoft.com/fwlink/?linkid=391089) to help you with your deployment.</span></span>
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a><span data-ttu-id="ba50c-186">Microsoft 365 のセットアップを支援するユーザーが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="ba50c-186">Do you want someone to help you set up Microsoft 365?</span></span>

- <span data-ttu-id="ba50c-187">**従業員が 50 名未満の場合:**</span><span class="sxs-lookup"><span data-stu-id="ba50c-187">**If you have fewer than 50 employees:**</span></span>

  - <span data-ttu-id="ba50c-188">**ヘルプを求め、お電話します**。</span><span class="sxs-lookup"><span data-stu-id="ba50c-188">**Ask for help and we'll call you**.</span></span> <span data-ttu-id="ba50c-189">Microsoft 365 を購入した後、管理センターにアクセスできます (セットアップを実行してアクセスする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="ba50c-189">After you buy Microsoft 365, you can access the admin center (you don't need to run setup to get to it).</span></span> <span data-ttu-id="ba50c-190">管理センターの下部で、[ヘルプが必要] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="ba50c-190">At the bottom of the admin center, select **Need help?**</span></span> <span data-ttu-id="ba50c-191">問題を説明し、お客様に電話します。</span><span class="sxs-lookup"><span data-stu-id="ba50c-191">Describe your problem, and we'll call you.</span></span> 
  - <span data-ttu-id="ba50c-192">**ご質問 [がある場合は、Microsoft 365 for Business サポート](../../business-video/get-help-support.md) にお問い合わせください**。</span><span class="sxs-lookup"><span data-stu-id="ba50c-192">**Call [Microsoft 365 for Business Support](../../business-video/get-help-support.md) with your questions**.</span></span> <span data-ttu-id="ba50c-193">We're here to help!</span><span class="sxs-lookup"><span data-stu-id="ba50c-193">We're here to help!</span></span> 
  - <span data-ttu-id="ba50c-194">**[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用をご検討ください** 。</span><span class="sxs-lookup"><span data-stu-id="ba50c-194">**Consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089)**.</span></span> <span data-ttu-id="ba50c-195">時間が短い場合や、高度な要件 (何千ものファイルを Microsoft 365 クラウド ストレージに移動する、他のソフトウェアと統合するなど) がある場合は、経験豊富なパートナーが大きな助けになります。</span><span class="sxs-lookup"><span data-stu-id="ba50c-195">If you're short on time, or have advanced requirements (like moving thousands of files to Microsoft 365 cloud storage or integrating with other software), an experienced partner can be a big help.</span></span> 

- <span data-ttu-id="ba50c-196">**50 名以上の従業員がいる場合** 、 [FastTrack オンボーディング センター](https://go.microsoft.com/fwlink/?LinkId=517115)が展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ba50c-196">**If you have more than 50 employees**, the [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) is available to help you with your deployment.</span></span>