---
title: 基本的なモビリティとセキュリティの設定
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: ユーザーのモバイルデバイスをセキュリティで保護して管理するための基本的なモビリティとセキュリティを設定します。
ms.openlocfilehash: cb010668d95e51edfbc913caa308ddd830d674e2
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430226"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="624c9-103">基本的なモビリティとセキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="624c9-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="624c9-104">Microsoft 365 の組み込みの基本的なモビリティとセキュリティにより、iPhones、Ipad、Androids、Windows phone などのユーザーのモバイルデバイスをセキュリティで保護し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="624c9-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="624c9-105">デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。</span><span class="sxs-lookup"><span data-stu-id="624c9-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="624c9-106">質問がおありですか?</span><span class="sxs-lookup"><span data-stu-id="624c9-106">Have questions?</span></span> <span data-ttu-id="624c9-107">よく寄せられる質問については、「 [基本的なモビリティおよびセキュリティに関する faq (faq)](frequently-asked-questions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="624c9-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.md).</span></span> <span data-ttu-id="624c9-108">委任された管理者アカウントを使用して、基本的なモビリティとセキュリティを管理することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="624c9-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="624c9-109">詳細については、「 [パートナー: 代理管理を提案](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="624c9-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="624c9-110">デバイス管理はセキュリティ & コンプライアンスセンターの一部であるため、MDM セットアップを開始するには、このページに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off MDM setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="624c9-111">基本的なモビリティおよびセキュリティサービスをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="624c9-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="624c9-112">グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="624c9-112">Sign in to Microsoft 365 with your global admin account.</span></span>
    

2. <span data-ttu-id="624c9-113">[ [基本的なモビリティとセキュリティをアクティブ](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)にする] に移動します。</span><span class="sxs-lookup"><span data-stu-id="624c9-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>
    
    <span data-ttu-id="624c9-114">基本的なモビリティとセキュリティをアクティブにするには、しばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="624c9-115">完了すると、次の手順について説明する電子メールが届きます。</span><span class="sxs-lookup"><span data-stu-id="624c9-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="624c9-116">モバイルデバイス管理の設定</span><span class="sxs-lookup"><span data-stu-id="624c9-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="624c9-117">サービスの準備ができたら、次の手順を実行してセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="624c9-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-mdm"></a><span data-ttu-id="624c9-118">手順 1: (必須) MDM のドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="624c9-118">Step 1: (Required) Configure domains for MDM</span></span>

<span data-ttu-id="624c9-119">Microsoft 365 に関連付けられたカスタムドメインがない場合、または Windows デバイスを管理していない場合は、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="624c9-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="624c9-120">それ以外の場合は、DNS ホストでドメインの DNS レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="624c9-121">Microsoft 365 を使用したドメインのセットアップの一環としてレコードを既に追加している場合は、すべての設定が完了しています。</span><span class="sxs-lookup"><span data-stu-id="624c9-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="624c9-122">レコードを追加すると、組織内の Microsoft 365 ユーザーが、カスタムドメインを使用する電子メールアドレスを使用して Windows デバイスにサインインすると、基本的なモビリティとセキュリティに登録されます。</span><span class="sxs-lookup"><span data-stu-id="624c9-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="624c9-123">レコードの設定に関するヘルプが必要な場合</span><span class="sxs-lookup"><span data-stu-id="624c9-123">Need help setting up the records?</span></span> <span data-ttu-id="624c9-124">ドメインレジストラーを見つけて、dns レコードを追加するための手順を、「 [ドメインを接続するために dns レコードを追加する](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」に記載されている一覧に表示されるように、レジストラー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="624c9-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="624c9-125">これらの手順を使用して、「 [AZURE AD Premium を使用しない Windows 登録を簡素化](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)する」で説明されている CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="624c9-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="624c9-126">2つの CNAME レコードを追加したら、セキュリティ & コンプライアンスセンターに戻り、[**データ損失防止**デバイスの管理] に移動して  >  **Device management**   次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="624c9-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="624c9-127">手順 2: (必須) iOS デバイス用の APNs 証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="624c9-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="624c9-128">IPad や iPhones などの iOS デバイスを管理するには、APNs 証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="624c9-129">グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="624c9-129">Sign in to  Microsoft 365 with your global admin account.</span></span>   

2. <span data-ttu-id="624c9-130">ブラウザーで、次のように入力  [https://protection.office.com](https://protection.office.com/) します。</span><span class="sxs-lookup"><span data-stu-id="624c9-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>  

3. <span data-ttu-id="624c9-131">[ **データ損失防止**   >  **デバイス管理**] を選択し、 **iOS デバイス用の APNs 証明書**を選択します。</span><span class="sxs-lookup"><span data-stu-id="624c9-131">Select **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>   

4. <span data-ttu-id="624c9-132">[Apple プッシュ通知の証明書の設定] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624c9-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>  

5. <span data-ttu-id="624c9-133">[ **CSR ファイルをダウンロード**   し、証明書の署名要求をコンピューターのどこかに保存する] を選択して、覚えておきます。</span><span class="sxs-lookup"><span data-stu-id="624c9-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="624c9-134">[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="624c9-134">Select **Next**.</span></span>
    
6. <span data-ttu-id="624c9-135">[APNs 証明書の作成] ページで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="624c9-135">On the Create an APNs certificate page:</span></span>
    
    - <span data-ttu-id="624c9-136">Apple APNS Portal を選択して、Apple プッシュ証明書ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="624c9-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    - <span data-ttu-id="624c9-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="624c9-137">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="624c9-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="624c9-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    - <span data-ttu-id="624c9-140">[証明書を作成し、使用条件に同意します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="624c9-140">Select Create a Certificate and accept the Terms of Use.</span></span>
    
    - <span data-ttu-id="624c9-141">Browseto は、Microsoft 365 および Selectuの Ad からコンピューターにダウンロードした証明書の署名要求を確認します。</span><span class="sxs-lookup"><span data-stu-id="624c9-141">Browseto the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
    
    - <span data-ttu-id="624c9-142">コンピューターへの Apple プッシュ証明書ポータルによって作成された APN 証明書をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="624c9-142">Downloadthe APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

    >[!TIP]
    ><span data-ttu-id="624c9-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="624c9-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="624c9-144">Microsoft 365 に戻って、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="624c9-144">Go back to Microsoft 365 and select **Next**.</span></span>   

8. <span data-ttu-id="624c9-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="624c9-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>   

9. <span data-ttu-id="624c9-146">[  **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="624c9-146">Select  **Finish**.</span></span>  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="624c9-147">手順 3: (推奨) 多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="624c9-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="624c9-148">MFA は、2番目の形式の認証を必要とすることで、モバイルデバイスの登録用に Microsoft 365 へのサインインをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="624c9-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="624c9-149">ユーザーは、職場のアカウントパスワードを正しく入力した後に、モバイルデバイスでの電話、テキストメッセージ、アプリの通知を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="624c9-150">この2番目の形式の認証が完了した後にのみ、デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="624c9-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="624c9-151">ユーザーデバイスが基本的なモビリティとセキュリティに登録されると、ユーザーは職場アカウントのみを使用して Microsoft 365 リソースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="624c9-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="624c9-152">Azure AD ポータルで MFA を有効にする方法については、「 [多要素認証をセットアップ](https://go.microsoft.com/fwlink/p/?LinkId=519255)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="624c9-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>

<span data-ttu-id="624c9-153">MFA を設定したら、セキュリティ & コンプライアンスセンターに戻り、[ **データ損失防止**の   >  **デバイス管理**デバイスポリシー] に移動して   >  **Device policies**   次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="624c9-153">After you set up MFA, go back to the Security & Compliance Center and navigate to **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="624c9-154">手順 4: (推奨) デバイスセキュリティポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="624c9-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="624c9-155">次の手順では、Microsoft 365 組織のデータを保護するために、デバイスのセキュリティポリシーを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="624c9-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="624c9-156">たとえば、ユーザーがデバイスを失った場合のデータ損失を防止するには、5分間非アクティブなデバイスをロックするポリシーを作成し、3回のサインインに失敗した後でデバイスをワイプします。</span><span class="sxs-lookup"><span data-stu-id="624c9-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="624c9-157">グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="624c9-157">Sign in to Microsoft 365 with your global admin account.</span></span> 

2. <span data-ttu-id="624c9-158">[ [モバイルデバイス管理のアクティブ化](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="624c9-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="624c9-159">サービスがアクティブになっている場合は、代わりにアクティブ化の手順で [デバイスを管理](https://admin.microsoft.com/adminportal/home#/MifoDevices)するためのリンクが表示され   ます。</span><span class="sxs-lookup"><span data-stu-id="624c9-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>
    
3. <span data-ttu-id="624c9-160">[ **デバイスポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="624c9-160">Go to **Device policies**.</span></span>

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティとモビリティのポリシー設定":::

4. <span data-ttu-id="624c9-162">「 [Basic Mobility And security でのデバイスセキュリティポリシーの作成](create-device-security-policies.md)」の手順に従って、組織に適したデバイスセキュリティポリシーを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="624c9-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

>[!TIP]
    - <span data-ttu-id="624c9-163">新しいポリシーを作成するときに、ユーザーデバイスがポリシーに準拠していない場合にアクセスを許可し、ポリシー違反を報告するようにポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="624c9-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="624c9-164">これにより、Microsoft 365 へのアクセスをブロックすることなく、ポリシーによって影響を受けるモバイルデバイスの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="624c9-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365 .</span></span><br/><span data-ttu-id="624c9-165">-組織内のすべてのユーザーに新しいポリシーを展開する前に、少数のユーザーによって使用されているデバイスでテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="624c9-165">- Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span><br/><span data-ttu-id="624c9-166">また、ポリシーを展開する前に、基本的なモビリティとセキュリティでデバイスを登録することによる潜在的な影響を組織に知らせます。</span><span class="sxs-lookup"><span data-stu-id="624c9-166">- Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="624c9-167">ポリシーの設定方法によっては、ポリシーに準拠していないデバイス (準拠していないデバイス) が Microsoft 365 へのアクセスをブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="624c9-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="624c9-168">準拠していないデバイスには、デバイスがワイプされている場合に、登録済みデバイス上にインストールされているアプリ、写真、その他の個人情報が含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="624c9-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="624c9-169">詳細については、「 [Basic Mobility And Security でモバイルデバイスをワイプする](wipe-mobile-device.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="624c9-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>
    
## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="624c9-170">ユーザーが自分のデバイスを登録していることを確認する</span><span class="sxs-lookup"><span data-stu-id="624c9-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="624c9-171">モバイルデバイス管理ポリシーを作成して展開した後、デバイスポリシーが適用する、組織内のライセンスが付与された各 Microsoft 365 ユーザーは、モバイルデバイスから Microsoft 365 に次回サインインしたときに登録メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="624c9-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="624c9-172">Microsoft 365 の電子メールとドキュメントにアクセスする前に、登録とライセンス認証の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="624c9-173">詳細については、「 [Basic Mobility And Security を使用してモバイルデバイスを登録する](enroll-your-mobile-device.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="624c9-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="624c9-174">登録プロセスでユーザーの優先言語がサポートされていない場合、ユーザーは自分のモバイルデバイスで登録通知と手順を別の言語で受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="624c9-175">Microsoft 365 でサポートされている言語の中には、現在、モバイルデバイスでの登録プロセスがサポートされていないものがあります。</span><span class="sxs-lookup"><span data-stu-id="624c9-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="624c9-176">Android または iOS デバイスを使用しているユーザーは、登録プロセスの一環として、ポータルサイトアプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="624c9-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="624c9-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="624c9-177">Related Topics</span></span>

[<span data-ttu-id="624c9-178">基本的なモビリティとセキュリティの機能</span><span class="sxs-lookup"><span data-stu-id="624c9-178">Capabilities of Basic Mobility and Security</span></span>](capabilities.md)<br/>
[<span data-ttu-id="624c9-179">基本的なモビリティとセキュリティでデバイスのセキュリティポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="624c9-179">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)