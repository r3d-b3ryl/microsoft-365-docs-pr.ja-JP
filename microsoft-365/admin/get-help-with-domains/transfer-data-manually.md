---
title: 2つのアカウント間でデータを手動で転送する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: プランまたは会社名を変更したとき、または複数のサブスクリプションを1つに結合したときに、2つの Microsoft 365 アカウント間でデータを手動で転送する方法について説明します。
ms.openlocfilehash: b7b0bb9c9b95b31d98040ae90632ef87a7fb0e3b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645145"
---
# <a name="transfer-data-manually-between-two-accounts"></a><span data-ttu-id="aa6ba-103">2つのアカウント間でデータを手動で転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-103">Transfer data manually between two accounts</span></span>

<span data-ttu-id="aa6ba-104">Sleeves をロールアップし、予定表の時間をブロックするように準備します。2つの Microsoft 365 アカウント間でデータを転送することは、手動で複雑で時間のかかるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-104">Prepare to roll up your sleeves and block out a chunk of time on your calendar: transferring data between two Microsoft 365 accounts is a manual, complicated, and time-consuming process.</span></span> <span data-ttu-id="aa6ba-105">これは、自動化またはサポートされているプロセスではありません。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-105">This is not an automated or supported process.</span></span> <span data-ttu-id="aa6ba-106">開始します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-106">We'll get you started.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="aa6ba-107">電子メール、Skype for Business、および Microsoft 365 でホストされているパブリック web サイトが機能しないプロセスの間に、ダウンタイムが発生します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-107">There will be down time during the process where email, Skype for Business and a public website hosted on Microsoft 365 won't work.</span></span> <span data-ttu-id="aa6ba-108">ユーザーには新しいユーザー名とパスワードが提供され、ユーザーは Outlook を再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-108">Users will get new user names and passwords, and they'll need to reset up Outlook.</span></span>

<span data-ttu-id="aa6ba-109">**次のいずれかが当てはまる場合は、この記事の手順を使用して手動でデータを転送するしかありません。**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-109">**Only transfer data manually using the instructions in this topic if one of the following applies:**</span></span>
  
- <span data-ttu-id="aa6ba-110">異なるサービス ファミリのプランに変更する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-110">You need to change to a plan in a different service family.</span></span>

- <span data-ttu-id="aa6ba-111">会社名が変わったため、新しいサブスクリプションを作成し、異なる初期ドメイン名を使用するのでデータを移行する場合。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-111">Your company name changed, and you decided to create a new subscription and migrate your data because you want to use different initial domain names.</span></span>

- <span data-ttu-id="aa6ba-112">複数のサブスクリプションを 1 つの新しいサブスクリプションにまとめる必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-112">You need to combine multiple subscriptions into one new one.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa6ba-113">[サブスクリプション プランを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md) 必要があり、プラン切り替えウィザードを使用できる場合、またはプラン切り替えウィザードを使用できない場合でも同じサブスクリプション ファミリの新しいサブスクリプション プランに転送する必要がある場合は、手動でデータを転送する必要はないため、ダウンタイムは発生しません。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-113">If you need to [change your subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md) and can use the Switch plans wizard, or if you need to transfer to a new subscription plan in the same subscription family even when the Switch plans wizard doesn't work, you don't need to manually transfer your data, and there is no down time.</span></span>

|<span data-ttu-id="aa6ba-114">**タスク**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-114">**Tasks**</span></span>|<span data-ttu-id="aa6ba-115">**手順**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-115">**Steps**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa6ba-116">新たに希望するプランを購入します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-116">Purchase the plan you want to move to.</span></span>  <br/> |<span data-ttu-id="aa6ba-p103">サインアップするときは、初期ドメイン名 ( *yourcompany*  .onmicrosoft.com、  *yourcompany*  -public.sharepoint.com、  *yourcompany*  .sharepoint.com) で使用する会社名を指定します。既存のサブスクリプションとは異なる  *yourcompany*  名を使用する必要があります。  </span><span class="sxs-lookup"><span data-stu-id="aa6ba-p103">When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com. You need to use a different  *yourcompany*  name than you did for any existing subscriptions.  </span></span><br/> <span data-ttu-id="aa6ba-119">> [!NOTE]>  通常、  *yourcompany*  を使用する初期ドメイン名をシステムから解放するには、サブスクリプションを取り消してから数か月以上かかります。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-119">> [!NOTE]>  It typically takes a minimum of several months after cancelling a subscription to release the initial domain names that use  *yourcompany*  from our systems.</span></span> <span data-ttu-id="aa6ba-120">古い Microsoft 365 サブスクリプションからすべてのデータを保存することを計画している場合でも、そのサブスクリプションを取り消すと、古い  *会社*  の値を新しいサブスクリプションですぐに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-120">Even if you plan to save all your data from your old Microsoft 365 subscription, and cancel that subscription, the old  *yourcompany*  value is not immediately available for use in a new subscription.</span></span>           |
|<span data-ttu-id="aa6ba-121">古い Microsoft 365 サブスクリプションからカスタムドメインを削除します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-121">Remove your custom domain from your old Microsoft 365 subscription.</span></span>  <br/> | <span data-ttu-id="aa6ba-122">[ドメインを削除する前に必要な手順](remove-a-domain.md) に従って、ユーザーのメール アドレスからドメイン名を削除し、メールの DNS レコードとカスタム ドメインの Lync を削除します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-122">Follow the [required steps before you remove a domain](remove-a-domain.md) to remove the domain name from user email addresses and remove DNS records for email and Lync for the custom domain.</span></span> <span data-ttu-id="aa6ba-123">Microsoft 365 でパブリック web サイトをホストしている場合は、それを指す CNAME レコードも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-123">If you host your public website on Microsoft 365, you'll also need to remove the CNAME record that points to it.</span></span>  <br/> <span data-ttu-id="aa6ba-p106">> [!IMPORTANT]>  このカスタム ドメインにメールをルーティングする MX レコードを削除すると、新しいアカウントにドメインを追加し、新しい MX レコードをセットアップして、ユーザーを設定するまで、メールは機能しなくなります。Lync の DNS レコードを削除すると、Lync は動作を停止します。また、パブリック Web サイトを指し示している CNAME レコードを削除した後は、Web サイトは使用できなくなります。           [ドメインを削除します](remove-a-domain.md) 。  </span><span class="sxs-lookup"><span data-stu-id="aa6ba-p106">> [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users. When you remove the DNS records for Lync, Lync will stop working. And after you remove the CNAME record that points to your public website, it will not be available.           [Remove the domain](remove-a-domain.md) .  </span></span><br/> |
|<span data-ttu-id="aa6ba-128">新しいサブスクリプションのカスタム ドメインをセットアップして、ユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-128">Set up your custom domain for your new subscription, and set up your users.</span></span>  <br/> | <span data-ttu-id="aa6ba-129">カスタム ドメインに必要な DNS レコードの作成など、新しいサブスクリプションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-129">Set up your new subscription, including creating the required DNS records for your custom domain.</span></span>  <br/>  <span data-ttu-id="aa6ba-130">カスタム ドメインでのメール アドレスを指定して、ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-130">Create your users, with email addresses on your custom domain.</span></span>  <br/> |
|<span data-ttu-id="aa6ba-131">古いサブスクリプションから新しいサブスクリプションにデータを転送します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-131">Transfer data from your old subscription to your new subscription.</span></span>  <br/> | <span data-ttu-id="aa6ba-132">別のブラウザー ウィンドウで両方のアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-132">Sign in to both accounts in separate browser windows:</span></span>  <br/>  <span data-ttu-id="aa6ba-133">ブラウザーのアイコンを右クリックして、2つのプライベートブラウザーウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-133">Right-click your browser icon, and open two private browser windows.</span></span> <span data-ttu-id="aa6ba-134">2 つのウィンドウで異なる資格情報を使用して、両方のアカウントにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-134">You can use different credentials in the two windows to sign in on both accounts.</span></span>  <br/> [<span data-ttu-id="aa6ba-135">サブスクリプション間で管理の設定を転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-135">Transfer administrative settings between subscriptions</span></span>](#email) <br/> [<span data-ttu-id="aa6ba-136">チーム サイトの構造とデータを転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-136">Transfer team site structure and data</span></span>](#transfer-team-site-structure-and-data) <br/> [<span data-ttu-id="aa6ba-137">サブスクリプション間でパブリック Web サイトを転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-137">Transfer a public website between subscriptions</span></span>](#transfer-a-public-website-between-subscriptions) <br/> [<span data-ttu-id="aa6ba-138">サブスクリプション間で管理の設定を転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-138">Transfer administrative settings between subscriptions</span></span>](#email) <br/> |
|<span data-ttu-id="aa6ba-139">Microsoft 365 の Microsoft サポートに連絡して、実行しているプランのサブスクリプションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-139">Cancel the subscription for the plan you're done with by calling Microsoft Support for Microsoft 365.</span></span>  <br/> | <span data-ttu-id="aa6ba-140">新しいサブスクリプションが動作していて、すべてのデータが転送されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-140">Verify that your new subscription is working and all data has been transferred.</span></span>  <br/>  <span data-ttu-id="aa6ba-141">[カスタマーサポートに連絡](../contact-support-for-business-products.md) して、古いサブスクリプションを解約してください。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-141">[Contact customer support](../contact-support-for-business-products.md) to cancel your old subscription.</span></span>  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a><span data-ttu-id="aa6ba-142">サブスクリプション間で管理の設定を転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-142">Transfer administrative settings between subscriptions</span></span>

<span data-ttu-id="aa6ba-143">各アカウントで次のページに移動し、古いアカウントの設定に基づいて新しいアカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-143">Go to the following pages on each account, and set up the new account based on the old account's settings.</span></span>
  
<span data-ttu-id="aa6ba-144">Microsoft 365 から Microsoft 365 中規模企業または Microsoft 365 Enterprise にデータを転送する場合、管理ページの構造は異なります。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-144">If you are transferring data from Microsoft 365 to Microsoft 365 Midsize Business or Microsoft 365 Enterprise, the admin pages are structured differently.</span></span> <span data-ttu-id="aa6ba-145">[「Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)」を参照し、次の場所に移動して、管理設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-145">Watch a [Video: Introducing Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/), and go to the following places to look at admin settings.</span></span>
  
<span data-ttu-id="aa6ba-146">Microsoft 365 Enterprise および Microsoft 365 中規模企業の場合:</span><span class="sxs-lookup"><span data-stu-id="aa6ba-146">For Microsoft 365 Enterprise and Microsoft 365 Midsize Business:</span></span>
  
|<span data-ttu-id="aa6ba-147">**場所**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-147">**Location**</span></span>|<span data-ttu-id="aa6ba-148">**目的**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-148">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa6ba-149">**管理者** \>**Microsoft 365** \>**サービス設定**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-149">**Admin** \> **Microsoft 365** \> **Service settings**</span></span> <br/> |<span data-ttu-id="aa6ba-150">メール、サイト、Lync、ユーザーソフトウェア、パスワード、コミュニティ、rights management、およびモバイルの設定については、各タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-150">Select each tab for settings for mail, sites, Lync, user software, passwords, community, rights management, and mobile.</span></span>  <br/> |
|<span data-ttu-id="aa6ba-151">[ **管理者**] \> [ **Exchange**]</span><span class="sxs-lookup"><span data-stu-id="aa6ba-151">**Admin** \> **Exchange**</span></span> <br/> | <span data-ttu-id="aa6ba-152">Exchange Online の設定</span><span class="sxs-lookup"><span data-stu-id="aa6ba-152">Exchange Online settings</span></span>  <br/> |
|<span data-ttu-id="aa6ba-153">[ **管理者**] \> [ **SharePoint**]</span><span class="sxs-lookup"><span data-stu-id="aa6ba-153">**Admin** \> **SharePoint**</span></span> <br/> | <span data-ttu-id="aa6ba-154">SharePoint Online の設定</span><span class="sxs-lookup"><span data-stu-id="aa6ba-154">SharePoint Online settings</span></span>  <br/> |
|<span data-ttu-id="aa6ba-155">**管理者** \>**Skype For business**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-155">**Admin** \> **Skype for Business**</span></span> <br/> |<span data-ttu-id="aa6ba-156">その他の Skype for Business の設定</span><span class="sxs-lookup"><span data-stu-id="aa6ba-156">Additional Skype for Business settings</span></span>  <br/> |

<span data-ttu-id="aa6ba-157">Microsoft 365 Small Business の場合</span><span class="sxs-lookup"><span data-stu-id="aa6ba-157">For Microsoft 365 Small Business</span></span>
  
|<span data-ttu-id="aa6ba-158">**場所**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-158">**Location**</span></span>|<span data-ttu-id="aa6ba-159">**目的**</span><span class="sxs-lookup"><span data-stu-id="aa6ba-159">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa6ba-160">[ **管理者**] \> [ **組織全体の設定を管理**]</span><span class="sxs-lookup"><span data-stu-id="aa6ba-160">**Admin** \> **Manage organization-wide settings**</span></span> <br/> |<span data-ttu-id="aa6ba-161">管理の設定</span><span class="sxs-lookup"><span data-stu-id="aa6ba-161">Administrative settings</span></span>  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a><span data-ttu-id="aa6ba-162">サブスクリプション間でパブリック Web サイトを転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-162">Transfer a public website between subscriptions</span></span>

<span data-ttu-id="aa6ba-163">Microsoft 365 でホストされているパブリック web サイトがある場合は、それを保存して、新しいサブスクリプションで再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-163">If you have a public website hosted on Microsoft 365, you need to save it and re-create it on your new subscription.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa6ba-p109">パブリック Web サイトが DNS ホスティング プロバイダーでホストされている場合は、変更する必要はありません。移行による影響はありません。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-p109">If your public website is hosted at a DNS hosting provider, no changes are required. It will not be affected by your transition.</span></span>
  
<span data-ttu-id="aa6ba-166">ドキュメント ライブラリやリスト コンテンツを SharePoint Online 環境からファイル共有やローカル コンピューターに保存するには、「[SharePoint Online コンテンツの手動移行に関する情報](https://go.microsoft.com/fwlink/p/?LinkId=402910)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-166">To save a document library or list content from a SharePoint Online environment to file shares or to a local computer, see [Manual migration of SharePoint Online content](https://go.microsoft.com/fwlink/p/?LinkId=402910).</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa6ba-167">パブリック サイト移行アプリでは、データを別のサブスクリプションに転送できません。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-167">The Public site migration app can't transfer data to a different subscription.</span></span>
  
## <a name="transfer-team-site-structure-and-data"></a><span data-ttu-id="aa6ba-168">チーム サイトの構造とデータを転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-168">Transfer team site structure and data</span></span>

<span data-ttu-id="aa6ba-169">チーム サイトのデータを保存または転送するには複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-169">There are several ways to save or transfer team site data:</span></span>
  
- <span data-ttu-id="aa6ba-170">古いサイトをテンプレートとして保存し、新しいサイトにテンプレートをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-170">You can save the old site as a template and import the template into the new site.</span></span>

- <span data-ttu-id="aa6ba-171">ドキュメントを転送するには、最初に新しいサイトで階層を手動で再作成します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-171">To transfer documents, first manually recreate your hierarchy on the new site.</span></span> <span data-ttu-id="aa6ba-172">その後は、両方の SharePoint チーム サイトを同時に開き、両方のドキュメント ライブラリをエクスプローラーで開いて、ドキュメントをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-172">Then you can open both SharePoint team sites at the same time, open both document libraries with Windows Explorer, and copy and paste the documents.</span></span> <span data-ttu-id="aa6ba-173">「[ビデオ: [エクスプローラーで開く] を使用してライブラリ ファイルをコピーまたは移動する](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-173">See [Video: Copy or move library files by using Open with Explorer](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).</span></span>

- <span data-ttu-id="aa6ba-174">リスト データを転送するには、[リスト テンプレート](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)を保存し、保存したテンプレートを使用して新しいサイトにリストを再作成します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-174">To transfer list data, save a [list template](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393), and use the saved template to re-create the list on the new site.</span></span>

- <span data-ttu-id="aa6ba-175">SharePoint Online 環境 (OneDrive for Business またはチームサイト) からファイル共有またはローカルコンピューターにドキュメントライブラリまたはリストのコンテンツを保存するには、「 [Sharepoint online コンテンツの手動での移行に関する情報](https://support.microsoft.com/kb/2783484)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-175">To save a document library or list content from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Information about manual migration of SharePoint Online content](https://support.microsoft.com/kb/2783484).</span></span>

## <a name="transfer-users-data-between-subscriptions"></a><span data-ttu-id="aa6ba-176">サブスクリプション間でユーザーのデータを転送する</span><span class="sxs-lookup"><span data-stu-id="aa6ba-176">Transfer users' data between subscriptions</span></span>

### <a name="email"></a><span data-ttu-id="aa6ba-177">電子メール:</span><span class="sxs-lookup"><span data-stu-id="aa6ba-177">Email:</span></span>

<span data-ttu-id="aa6ba-p111">新しいサブスクリプションを設定した後、[メール、連絡先、タスク、および予定表の情報を移動する](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc)ようにユーザーに依頼します。古いメールには、sue@contoso.onmicrosoft.com などの初期ユーザー名を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-p111">Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription. They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.</span></span>
  
### <a name="onedrive-for-business-data"></a><span data-ttu-id="aa6ba-180">OneDrive For Business データ:</span><span class="sxs-lookup"><span data-stu-id="aa6ba-180">OneDrive For Business data:</span></span>

<span data-ttu-id="aa6ba-181">ユーザーに [OneDrive For business のコンテンツを自分のコンピューターに](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)コピー/同期させ、新しいサブスクリプションに追加してもらいます。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-181">Ask users to Copy/Sync [OneDrive for Business content to their computer](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd), and then add it back to their new subscription.</span></span>

### <a name="onenote"></a><span data-ttu-id="aa6ba-182">OneNote</span><span class="sxs-lookup"><span data-stu-id="aa6ba-182">OneNote</span></span> 

<span data-ttu-id="aa6ba-183">ユーザーに [OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) をバックアップして、 [バックアップから](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) 新しいサブスクリプションにメモを復元するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="aa6ba-183">Ask users to [Back up OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) and to [Restore notes from a backup](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) to their new subscriptions.</span></span>
