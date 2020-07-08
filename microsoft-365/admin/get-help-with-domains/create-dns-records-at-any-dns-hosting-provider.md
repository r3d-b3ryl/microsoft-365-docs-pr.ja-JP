---
title: DNS レコードを追加して自分のドメインを接続する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: 任意の DNS ホスティング プロバイダーで Microsoft 365 用のドメインを確認し、DNS レコードを作成する方法について説明します。
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: d3a9e3787afc30b33122edf91c1cf9e3dd84b847
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049668"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="20a60-103">DNS レコードを追加して自分のドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="20a60-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="20a60-104">サードパーティのホスティング プロバイダーからドメインを購入した場合は、レジストラーのアカウントの DNS レコードを更新することで、それを Microsoft 365 に接続できます。</span><span class="sxs-lookup"><span data-stu-id="20a60-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="20a60-105">これらの手順を完了すると、お客様のドメインは、ドメインを購入したホストには登録されたままとなりますが、Microsoft 365 では、メール アドレス (user@yourdomain.com など) やその他のサービスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="20a60-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for you email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="20a60-106">ドメインを追加しない場合、組織内のユーザーは、メール アドレスに onmicrosoft.com ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="20a60-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="20a60-107">ユーザーを追加する前にドメインを追加することが重要です。それにより、ユーザーを再度セットアップする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="20a60-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="20a60-108">探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.md) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="20a60-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-record-to-verify-you-own-the-domain"></a><span data-ttu-id="20a60-109">手順 1: TXT レコードを追加してドメインの所有を確認する </span><span class="sxs-lookup"><span data-stu-id="20a60-109">Step 1: Add a TXT record to verify you own the domain</span></span>

<span data-ttu-id="20a60-110">まず、Microsoft 365 に追加するドメインを所有していることを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a60-110">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="20a60-111">[Microsoft 365 管理センター](https://admin.microsoft.com/) にサインインし、[**すべて表示**] > [**設定**] > [**ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20a60-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="20a60-112">新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。</span><span class="sxs-lookup"><span data-stu-id="20a60-112">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="20a60-113">プロバイダーの DNS マネージャーのページに移動し、管理センターで示された TXT レコードをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="20a60-113">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="20a60-114">このレコードを追加しても、既存のメールやその他のサービスには影響はありません。このレコードは、お客様のドメインが Microsoft 365 に接続された後、安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="20a60-114">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="20a60-115">例:</span><span class="sxs-lookup"><span data-stu-id="20a60-115">Example:</span></span>
- <span data-ttu-id="20a60-116">TXT 名: `@`</span><span class="sxs-lookup"><span data-stu-id="20a60-116">TXT Name: `@`</span></span>
- <span data-ttu-id="20a60-117">TXT 値: MS=ms######## (管理センターの固有 ID)</span><span class="sxs-lookup"><span data-stu-id="20a60-117">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="20a60-118">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="20a60-118">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="20a60-119">レコードを保存し、管理センターに戻り、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20a60-119">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="20a60-120">レコードの変更には通常 15 分ほどかかりますが、登録には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="20a60-120">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="20a60-121">少し時間をかけて、変更内容が反映されるように何度か試してください。</span><span class="sxs-lookup"><span data-stu-id="20a60-121">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="20a60-122">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="20a60-122">When Microsoft finds the correct TXT record, your domain is verified.</span></span>


## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="20a60-123">手順 2: DNS レコードを追加して Microsoft サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="20a60-123">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="20a60-124">新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。</span><span class="sxs-lookup"><span data-stu-id="20a60-124">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="20a60-125">有効にするサービスに応じて、いくつかの異なる種類の DNS レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="20a60-125">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="20a60-126">メール用の MX レコードを追加する (Outlook、Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="20a60-126">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="20a60-127">**開始する前に:** ユーザーがお客様のドメインのメールを既に所有している場合は (user@yourdomain.com など)、MX レコードをセットアップする前に管理センターでアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="20a60-127">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="20a60-128">こうすることで、引き続きメールを受信できます。</span><span class="sxs-lookup"><span data-stu-id="20a60-128">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="20a60-129">ドメインの MX レコードを更新すると、お客様のドメインを使用するユーザーのすべての新しいメールが、Microsoft 365 に届くようになります。</span><span class="sxs-lookup"><span data-stu-id="20a60-129">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="20a60-130">[メールと連絡先を Microsoft 365 に移行すること](../setup/migrate-email-and-contacts-admin.md)を決定しない限り、既に所有しているメールは現在のメール ホストに保持されます。</span><span class="sxs-lookup"><span data-stu-id="20a60-130">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="20a60-131">MX レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。</span><span class="sxs-lookup"><span data-stu-id="20a60-131">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="20a60-132">ホスティング プロバイダーの Web サイトで、新しい MX レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="20a60-132">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="20a60-133">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20a60-133">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="20a60-134">Record Type: `MX`</span><span class="sxs-lookup"><span data-stu-id="20a60-134">Record Type: `MX`</span></span>
- <span data-ttu-id="20a60-135">Priority: 使用可能な最高の値を設定します。通常は `0` です。</span><span class="sxs-lookup"><span data-stu-id="20a60-135">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="20a60-136">Host Name: `@`</span><span class="sxs-lookup"><span data-stu-id="20a60-136">Host Name: `@`</span></span>
- <span data-ttu-id="20a60-137">Points to address: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20a60-137">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="20a60-138">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="20a60-138">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="20a60-139">レコードを保存して、他の MX レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="20a60-139">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="20a60-140">CNAME レコードを追加して他のサービスに接続する (Teams、Exchange Online、AAD、MDM)</span><span class="sxs-lookup"><span data-stu-id="20a60-140">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="20a60-141">CNAME レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。</span><span class="sxs-lookup"><span data-stu-id="20a60-141">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="20a60-142">ホスティング プロバイダーの Web サイトで、接続するサービスごとに CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="20a60-142">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="20a60-143">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20a60-143">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="20a60-144">Record Type: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="20a60-144">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="20a60-145">Host: 管理センターからコピーした値をここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20a60-145">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="20a60-146">Points to address: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20a60-146">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="20a60-147">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="20a60-147">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="20a60-148">SPF TXT レコードを追加または編集して迷惑メールの防止に役立てる (Outlook、Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="20a60-148">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="20a60-149">**開始する前に:** 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="20a60-149">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="20a60-150">代わりに、ホスティング プロバイダーの Web サイトの現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが *1 つ* の SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="20a60-150">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="20a60-151">ホスティング プロバイダーの Web サイトで、既存の SPF レコードを編集するか、SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="20a60-151">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="20a60-152">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20a60-152">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="20a60-153">Record Type: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="20a60-153">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="20a60-154">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="20a60-154">Host: `@`</span></span>
- <span data-ttu-id="20a60-155">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="20a60-155">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="20a60-156">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="20a60-156">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="20a60-157">レコードを保存します。</span><span class="sxs-lookup"><span data-stu-id="20a60-157">Save the record.</span></span>

<span data-ttu-id="20a60-158">SPF レコードを検証するには、[SPF 検証ツール](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="20a60-158">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="20a60-159">SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。</span><span class="sxs-lookup"><span data-stu-id="20a60-159">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="20a60-160">これらから保護するために、SPF をセットアップした後、Microsoft 365 のために DKIM と DMARC も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a60-160">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="20a60-161">使用を開始する場合は、「[DKIM を使用して、Microsoft 365 のドメインから送信される送信電子メールを検証する](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)」、「[DMARC を使用して Microsoft 365 のメールを検証する](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20a60-161">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="20a60-162">コミュニケーション サービス用の SRV レコードを追加する (Teams、Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="20a60-162">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="20a60-163">ホスティング プロバイダーの Web サイトで、接続するサービスごとに SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="20a60-163">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="20a60-164">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20a60-164">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="20a60-165">Record Type: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="20a60-165">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="20a60-166">名前: `@`</span><span class="sxs-lookup"><span data-stu-id="20a60-166">Name: `@`</span></span>
- <span data-ttu-id="20a60-167">Target: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20a60-167">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="20a60-168">Protocol: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20a60-168">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="20a60-169">Service: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20a60-169">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="20a60-170">優先度: `100`</span><span class="sxs-lookup"><span data-stu-id="20a60-170">Priority: `100`</span></span>
- <span data-ttu-id="20a60-171">Weight: `1`</span><span class="sxs-lookup"><span data-stu-id="20a60-171">Weight: `1`</span></span>
- <span data-ttu-id="20a60-172">Port: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20a60-172">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="20a60-173">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="20a60-173">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="20a60-174">レコードを保存します。</span><span class="sxs-lookup"><span data-stu-id="20a60-174">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="20a60-175">SRV レコードのフィールドの制限と回避策</span><span class="sxs-lookup"><span data-stu-id="20a60-175">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="20a60-176">一部のホスティング プロバイダーは、SRV レコード内のフィールド値を制限します。</span><span class="sxs-lookup"><span data-stu-id="20a60-176">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="20a60-177">これらの制限の一般的な回避策をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="20a60-177">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="20a60-178">名前</span><span class="sxs-lookup"><span data-stu-id="20a60-178">Name</span></span>
<span data-ttu-id="20a60-179">ホスティング プロバイダーが、このフィールドに **@** の設定を許可しない場合は、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="20a60-179">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="20a60-180">この方法は、ホスティング プロバイダーが Service 値と Protocol 値のフィールドを個別に用意している場合に*のみ*使用します。</span><span class="sxs-lookup"><span data-stu-id="20a60-180">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="20a60-181">それ以外の場合は、下の Service と Protocol に関する注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20a60-181">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="20a60-182">Service と Protocol</span><span class="sxs-lookup"><span data-stu-id="20a60-182">Service and Protocol</span></span>
<span data-ttu-id="20a60-183">ホスティング プロバイダーが SRV レコードにこれらのフィールドを用意していない場合は、**Service** 値と **Protocol** 値をレコードの **Name** フィールドに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a60-183">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="20a60-184">(注: ホスティング プロバイダーによっては、**Name** フィールドが **Host**、**Hostname**、**Subdomain** など、他の名称になっている場合があります)。これらの値を追加するには、値をドットで区切って単一の文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="20a60-184">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="20a60-185">例: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="20a60-185">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="20a60-186">Priority、Weight、Port</span><span class="sxs-lookup"><span data-stu-id="20a60-186">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="20a60-187">ホスティング プロバイダーが SRV レコードにこれらのフィールドを用意していない場合は、レコードの **Target** フィールドにそれらの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a60-187">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="20a60-188">(注: ホスティング プロバイダーによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。</span><span class="sxs-lookup"><span data-stu-id="20a60-188">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="20a60-189">これらの値を追加するには、値をスペースで区切って単一の文字列を作成します。*末尾にドットを付加することもあります* (不明な場合は、プロバイダーに問い合わせてください)。</span><span class="sxs-lookup"><span data-stu-id="20a60-189">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="20a60-190">値は、Priority、Weight、Port、Target の順で含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a60-190">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="20a60-191">例 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="20a60-191">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="20a60-192">例 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="20a60-192">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
