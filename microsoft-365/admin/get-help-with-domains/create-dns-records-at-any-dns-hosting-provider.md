---
title: DNS レコードを追加して自分のドメインを接続する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: ドメインを確認して、レジストラーのアカウントの DNS レコードを更新することで、任意の DNS ホスティング プロバイダーでドメインを Microsoft 365 に接続します。
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
ms.openlocfilehash: 4b4c09ce6a4161c713490daef46157b5555e124b
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393921"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="d2bd9-103">DNS レコードを追加して自分のドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="d2bd9-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="d2bd9-104">サードパーティのホスティング プロバイダーからドメインを購入した場合は、レジストラーのアカウントの DNS レコードを更新することで、それを Microsoft 365 に接続できます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="d2bd9-105">これらの手順を完了すると、お客様のドメインは、ドメインを購入したホストには登録されたままとなりますが、Microsoft 365 では、メール アドレス (user@yourdomain.com など) やその他のサービスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="d2bd9-106">ドメインを追加しない場合、組織内のユーザーは、メール アドレスに onmicrosoft.com ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="d2bd9-107">ユーザーを追加する前にドメインを追加することが重要です。それにより、ユーザーを再度セットアップする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="d2bd9-108">探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.yml) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="d2bd9-109">手順 1: TXT または MX レコードを追加してドメインの所有を確認する </span><span class="sxs-lookup"><span data-stu-id="d2bd9-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="d2bd9-110">推奨: TXT レコードで確認する</span><span class="sxs-lookup"><span data-stu-id="d2bd9-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="d2bd9-111">まず、Microsoft 365 に追加するドメインを所有していることを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="d2bd9-112">[Microsoft 365 管理センター](https://admin.microsoft.com/) にサインインし、[**すべて表示**] > [**設定**] > [**ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="d2bd9-113">新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="d2bd9-114">プロバイダーの DNS マネージャーのページに移動し、管理センターで示された TXT レコードをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="d2bd9-115">このレコードを追加しても、既存のメールやその他のサービスには影響はありません。このレコードは、お客様のドメインが Microsoft 365 に接続された後、安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="d2bd9-116">例:</span><span class="sxs-lookup"><span data-stu-id="d2bd9-116">Example:</span></span>
- <span data-ttu-id="d2bd9-117">TXT 名: `@`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-117">TXT Name: `@`</span></span>
- <span data-ttu-id="d2bd9-118">TXT 値: MS=ms######## (管理センターの固有 ID)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="d2bd9-119">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="d2bd9-120">レコードを保存し、管理センターに戻り、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="d2bd9-121">レコードの変更には通常 15 分ほどかかりますが、登録には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="d2bd9-122">少し時間をかけて、変更内容が反映されるように何度か試してください。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="d2bd9-123">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="d2bd9-124">MX レコードで確認する</span><span class="sxs-lookup"><span data-stu-id="d2bd9-124">Verify with an MX record</span></span>

<span data-ttu-id="d2bd9-125">レジストラーが TXT レコードの追加をサポートしていない場合は、MX レコードを追加することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="d2bd9-126">[Microsoft 365 管理センター](https://admin.microsoft.com/) にサインインし、[**すべて表示**] > [**設定**] > [**ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="d2bd9-127">新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="d2bd9-128">プロバイダーの DNS マネージャーのページに移動し、管理センターで示された MX レコードをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="d2bd9-129">この MX レコードの **優先度** は、ドメインのすべての既存の MX レコードで最高でなくてはなりません。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="d2bd9-130">それ以外の場合、メールの送受信が妨げられます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="d2bd9-131">ドメイン確認が完了したら、すぐにこのレコードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="d2bd9-132">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="d2bd9-133">Record Type: `MX`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-133">Record Type: `MX`</span></span>
- <span data-ttu-id="d2bd9-134">Priority: 使用可能な最高の値を設定します。通常は `0` です。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="d2bd9-135">Host Name: `@`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-135">Host Name: `@`</span></span>
- <span data-ttu-id="d2bd9-136">Points to address: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="d2bd9-137">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="d2bd9-138">Microsoft で正しい MX レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="d2bd9-139">手順 2: DNS レコードを追加して Microsoft サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="d2bd9-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="d2bd9-140">新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="d2bd9-141">有効にするサービスに応じて、いくつかの異なる種類の DNS レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="d2bd9-142">メール用の MX レコードを追加する (Outlook、Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="d2bd9-143">**開始する前に:** ユーザーがお客様のドメインのメールを既に所有している場合は (user@yourdomain.com など)、MX レコードをセットアップする前に管理センターでアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="d2bd9-144">こうすることで、引き続きメールを受信できます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="d2bd9-145">ドメインの MX レコードを更新すると、お客様のドメインを使用するユーザーのすべての新しいメールが、Microsoft 365 に届くようになります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="d2bd9-146">[メールと連絡先を Microsoft 365 に移行すること](../setup/migrate-email-and-contacts-admin.md)を決定しない限り、既に所有しているメールは現在のメール ホストに保持されます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="d2bd9-147">MX レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="d2bd9-148">ホスティング プロバイダーの Web サイトで、新しい MX レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="d2bd9-149">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="d2bd9-150">Record Type: `MX`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-150">Record Type: `MX`</span></span>
- <span data-ttu-id="d2bd9-151">Priority: 使用可能な最高の値を設定します。通常は `0` です。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="d2bd9-152">Host Name: `@`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-152">Host Name: `@`</span></span>
- <span data-ttu-id="d2bd9-153">Points to address: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="d2bd9-154">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="d2bd9-155">レコードを保存して、他の MX レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="d2bd9-156">CNAME レコードを追加して他のサービスに接続する (Teams、Exchange Online、AAD、MDM)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="d2bd9-157">CNAME レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="d2bd9-158">ホスティング プロバイダーの Web サイトで、接続するサービスごとに CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="d2bd9-159">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="d2bd9-160">Record Type: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="d2bd9-161">Host: 管理センターからコピーした値をここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="d2bd9-162">Points to address: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="d2bd9-163">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="d2bd9-164">SPF TXT レコードを追加または編集して迷惑メールの防止に役立てる (Outlook、Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="d2bd9-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="d2bd9-165">**開始する前に:** 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="d2bd9-166">代わりに、ホスティング プロバイダーの Web サイトの現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが *1 つ* の SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="d2bd9-167">ホスティング プロバイダーの Web サイトで、既存の SPF レコードを編集するか、SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="d2bd9-168">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="d2bd9-169">Record Type: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="d2bd9-170">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-170">Host: `@`</span></span>
- <span data-ttu-id="d2bd9-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="d2bd9-172">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="d2bd9-173">レコードを保存します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-173">Save the record.</span></span>

<span data-ttu-id="d2bd9-174">SPF レコードを検証するには、[SPF 検証ツール](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-174">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="d2bd9-p109">SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Microsoft 365 用に構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-p109">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="d2bd9-177">使用を開始する場合は、「[DKIM を使用して、Microsoft 365 のドメインから送信される送信電子メールを検証する](../../security/office-365-security/use-dkim-to-validate-outbound-email.md)」、「[DMARC を使用して Microsoft 365 のメールを検証する](../../security/office-365-security/use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="d2bd9-178">コミュニケーション サービス用の SRV レコードを追加する (Teams、Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="d2bd9-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="d2bd9-179">ホスティング プロバイダーの Web サイトで、接続するサービスごとに SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="d2bd9-180">フィールドが次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="d2bd9-181">Record Type: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="d2bd9-182">名前: `@`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-182">Name: `@`</span></span>
- <span data-ttu-id="d2bd9-183">Target: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="d2bd9-184">Protocol: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="d2bd9-185">Service: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="d2bd9-186">優先度: `100`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-186">Priority: `100`</span></span>
- <span data-ttu-id="d2bd9-187">Weight: `1`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-187">Weight: `1`</span></span>
- <span data-ttu-id="d2bd9-188">Port: 管理センターから値をコピーし、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="d2bd9-189">TTL: `3600‎` (またはプロバイダーの既定値)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="d2bd9-190">レコードを保存します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="d2bd9-191">SRV レコードのフィールドの制限と回避策</span><span class="sxs-lookup"><span data-stu-id="d2bd9-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="d2bd9-192">一部のホスティング プロバイダーは、SRV レコード内のフィールド値を制限します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="d2bd9-193">これらの制限の一般的な回避策をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="d2bd9-194">名前</span><span class="sxs-lookup"><span data-stu-id="d2bd9-194">Name</span></span>
<span data-ttu-id="d2bd9-195">ホスティング プロバイダーが、このフィールドに **@** の設定を許可しない場合は、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="d2bd9-196">この方法は、ホスティング プロバイダーが Service 値と Protocol 値のフィールドを個別に用意している場合に *のみ* 使用します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="d2bd9-197">それ以外の場合は、下の Service と Protocol に関する注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="d2bd9-198">Service と Protocol</span><span class="sxs-lookup"><span data-stu-id="d2bd9-198">Service and Protocol</span></span>
<span data-ttu-id="d2bd9-199">ホスティング プロバイダーが SRV レコードにこれらのフィールドを用意していない場合は、**Service** 値と **Protocol** 値をレコードの **Name** フィールドに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="d2bd9-200">(注: ホスティング プロバイダーによっては、**Name** フィールドが **Host**、**Hostname**、**Subdomain** など、他の名称になっている場合があります)。これらの値を追加するには、値をドットで区切って単一の文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="d2bd9-201">例: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="d2bd9-202">Priority、Weight、Port</span><span class="sxs-lookup"><span data-stu-id="d2bd9-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="d2bd9-203">ホスティング プロバイダーが SRV レコードにこれらのフィールドを用意していない場合は、レコードの **Target** フィールドにそれらの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="d2bd9-204">(注: ホスティング プロバイダーによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="d2bd9-205">これらの値を追加するには、値をスペースで区切って単一の文字列を作成します。*末尾にドットを付加することもあります* (不明な場合は、プロバイダーに問い合わせてください)。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="d2bd9-206">値は、Priority、Weight、Port、Target の順で含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2bd9-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="d2bd9-207">例 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="d2bd9-208">例 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="d2bd9-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>

## <a name="related-content"></a><span data-ttu-id="d2bd9-209">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d2bd9-209">Related content</span></span>

<span data-ttu-id="d2bd9-210">[任意のドメイン レジストラーで Microsoft 365 をセットアップするためにネームサーバーを変更する](change-nameservers-at-any-domain-registrar.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-210">[Change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="d2bd9-211">[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-211">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="d2bd9-212">[ドメインの管理](index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="d2bd9-212">[Manage domains](index.yml) (link page)</span></span>