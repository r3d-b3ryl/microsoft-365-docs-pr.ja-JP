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
- AdminTemplateSet
search.appverid:
- MET150
description: デバイスをリモートでワイプするなどのアクションを実行して、ユーザーのモバイル デバイスをセキュリティで保護および管理するための基本モビリティとセキュリティを設定します。
ms.openlocfilehash: d878569c691fc25c8c91c5a5a29215e6284a5d71
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393285"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="334d5-103">基本的なモビリティとセキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="334d5-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="334d5-104">Microsoft 365 用の組み込みの Basic Mobility and Security は、iPhone、iPad、Android、携帯電話などのユーザーのモバイル デバイスをセキュリティで保護および管理Windowsします。</span><span class="sxs-lookup"><span data-stu-id="334d5-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="334d5-105">デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。</span><span class="sxs-lookup"><span data-stu-id="334d5-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="334d5-106">不明な点がある場合は、</span><span class="sxs-lookup"><span data-stu-id="334d5-106">Have questions?</span></span> <span data-ttu-id="334d5-107">一般的な質問に対処するためのよく寄せられる質問については、「Basic Mobility and Security に関するよく寄せられる質問 [(FAQ)」を参照してください](frequently-asked-questions.yml)。</span><span class="sxs-lookup"><span data-stu-id="334d5-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.yml).</span></span> <span data-ttu-id="334d5-108">委任された管理者アカウントを使用して Basic Mobility and Security を管理できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="334d5-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="334d5-109">詳細については、「パートナー: [委任された管理を提供する」を参照してください](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。</span><span class="sxs-lookup"><span data-stu-id="334d5-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="334d5-110">デバイス管理は、セキュリティ & コンプライアンス センターの一部なので、Basic Mobility and Security セットアップを開始するには、そこに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off Basic Mobility and Security setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="334d5-111">Basic Mobility and Security サービスをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="334d5-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="334d5-112">グローバル管理者アカウントMicrosoft 365にサインインします。</span><span class="sxs-lookup"><span data-stu-id="334d5-112">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="334d5-113">[基本モビリティと [セキュリティのアクティブ化] に移動します](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="334d5-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>

   <span data-ttu-id="334d5-114">Basic Mobility and Security をアクティブ化するには、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="334d5-115">完了すると、次に実行する手順を説明するメールが届きます。</span><span class="sxs-lookup"><span data-stu-id="334d5-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="334d5-116">モバイル デバイス管理のセットアップ</span><span class="sxs-lookup"><span data-stu-id="334d5-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="334d5-117">サービスの準備ができたら、次の手順を実行してセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="334d5-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a><span data-ttu-id="334d5-118">手順 1: (必須) 基本モビリティとセキュリティのドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="334d5-118">Step 1: (Required) Configure domains for Basic Mobility and Security</span></span>

<span data-ttu-id="334d5-119">カスタム ドメインを Microsoft 365 に関連付けなかったり、Windows デバイスを管理していない場合は、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="334d5-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="334d5-120">それ以外の場合は、DNS ホストでドメインの DNS レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="334d5-121">レコードを既に追加している場合は、Microsoft 365を使用してドメインを設定する一環として、すべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="334d5-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="334d5-122">レコードを追加すると、カスタム ドメインを使用する電子メール アドレスを使用して Windows デバイスにサインインする組織内の Microsoft 365 ユーザーが、Basic Mobility and Security に登録するためにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="334d5-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="334d5-123">レコードのセットアップに関するヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="334d5-123">Need help setting up the records?</span></span> <span data-ttu-id="334d5-124">ドメイン レジストラーを検索し、レジストラー名を選択して、「ドメインに接続するための DNS レコードの追加」のリストで DNS レコードを作成するための詳細なヘルプに [移動します](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="334d5-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="334d5-125">これらの手順を使用して、「登録を簡単にする」で説明されている CNAME[レコードWindows作成Azure AD Premium。](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)</span><span class="sxs-lookup"><span data-stu-id="334d5-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="334d5-126">2 つの CNAME レコードを追加したら、セキュリティ & コンプライアンス センターに戻り、[データ損失防止デバイスの管理] に移動して次の手順  >     を完了します。</span><span class="sxs-lookup"><span data-stu-id="334d5-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="334d5-127">手順 2: (必須) iOS デバイス用の APNs 証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="334d5-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="334d5-128">iOS デバイス (iPad iPhone など) を管理するには、APNs 証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="334d5-129">グローバル管理者アカウントMicrosoft 365にサインインします。</span><span class="sxs-lookup"><span data-stu-id="334d5-129">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="334d5-130">ブラウザーの種類:  [https://protection.office.com](https://protection.office.com/) です。</span><span class="sxs-lookup"><span data-stu-id="334d5-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="334d5-131">[ **データ損失防止デバイス**   >  **の管理] を** 選択し **、[iOS デバイスの APNs 証明書] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="334d5-131">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="334d5-132">[Apple プッシュ通知証明書] ページ設定[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="334d5-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="334d5-133">[CSR **ファイルをダウンロードする**] を選択し、覚えているコンピューターのどこかに証明書署名要求   を保存します。</span><span class="sxs-lookup"><span data-stu-id="334d5-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="334d5-134">[次 **へ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="334d5-134">Select **Next**.</span></span>

6. <span data-ttu-id="334d5-135">[APNs 証明書の作成] ページで、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="334d5-135">On the Create an APNs certificate page:</span></span>

   - <span data-ttu-id="334d5-136">[Apple APNS ポータル] を選択して、Apple プッシュ証明書ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="334d5-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
   - <span data-ttu-id="334d5-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="334d5-137">Sign in with an Apple ID.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="334d5-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="334d5-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

   - <span data-ttu-id="334d5-140">[証明書の作成] を選択し、利用規約に同意します。</span><span class="sxs-lookup"><span data-stu-id="334d5-140">Select Create a Certificate and accept the Terms of Use.</span></span>
   - <span data-ttu-id="334d5-141">コンピューターにダウンロードした証明書署名要求を [証明書] から参照Microsoft 365し、[アップロード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="334d5-141">Browse to the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
   - <span data-ttu-id="334d5-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span><span class="sxs-lookup"><span data-stu-id="334d5-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

     > [!TIP]
     > <span data-ttu-id="334d5-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="334d5-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="334d5-144">[次へ] に戻Microsoft 365し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="334d5-144">Go back to Microsoft 365 and select **Next**.</span></span>

8. <span data-ttu-id="334d5-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="334d5-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="334d5-146">[完了  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="334d5-146">Select  **Finish**.</span></span>

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="334d5-147">手順 3: (推奨) 多要素認証のセットアップ</span><span class="sxs-lookup"><span data-stu-id="334d5-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="334d5-148">MFA は、2 番目の形式の認証をMicrosoft 365、モバイル デバイスの登録に必要なサインインをセキュリティで保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="334d5-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="334d5-149">ユーザーは、仕事用アカウントのパスワードを正しく入力した後、モバイル デバイスで電話、テキスト メッセージ、アプリ通知を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="334d5-150">この 2 番目の形式の認証が完了した後にのみ、デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="334d5-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="334d5-151">ユーザー デバイスが Basic Mobility and Security に登録された後、ユーザーは自分の仕事用アカウントMicrosoft 365リソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="334d5-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="334d5-152">Azure ADポータルで MFA を有効にする方法については、「多要素認証のセットアップ [」を参照してください](../security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="334d5-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="334d5-153">MFA を設定した後、セキュリティ & コンプライアンス センターに戻り、[データ \*\*\*\* 損失防止デバイス管理デバイス ポリシー] に移動して、次   >     >  \*\*\*\*   の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="334d5-153">After you set up MFA, go back to the Security & Compliance Center and navigate to  **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="334d5-154">手順 4: (推奨) デバイス セキュリティ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="334d5-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="334d5-155">次の手順では、デバイス セキュリティ ポリシーを作成して展開し、組織のデータを保護Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="334d5-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="334d5-156">たとえば、ユーザーがデバイスを紛失した場合は、5 分間の非アクティブ状態の後にデバイスをロックし、3 回サインインが失敗した後にデバイスをワイプするポリシーを作成することで、データ損失を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="334d5-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="334d5-157">グローバル管理者アカウントMicrosoft 365にサインインします。</span><span class="sxs-lookup"><span data-stu-id="334d5-157">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="334d5-158">[モバイル [デバイス管理のアクティブ化] を選択します](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="334d5-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="334d5-159">サービスがアクティブ化されている場合は、代わりにライセンス認証手順に[デバイスの管理] へのリンク [が表示されます](https://admin.microsoft.com/adminportal/home#/MifoDevices)   。</span><span class="sxs-lookup"><span data-stu-id="334d5-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>

3. <span data-ttu-id="334d5-160">[デバイス ポリシー **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="334d5-160">Go to **Device policies**.</span></span>

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティポリシーとモビリティ ポリシー設定":::

4. <span data-ttu-id="334d5-162">「Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成」の手順に従って、組織に適したデバイス セキュリティ ポリシーを作成して [展開します](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="334d5-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

> [!TIP]
>
> - <span data-ttu-id="334d5-163">新しいポリシーを作成する場合は、ユーザー デバイスがポリシーに準拠していないアクセスを許可し、ポリシー違反を報告するポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="334d5-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="334d5-164">これにより、ポリシーの影響を受け取るモバイル デバイスの数を確認し、ポリシーへのアクセスをブロックMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="334d5-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365.</span></span>
>
> - <span data-ttu-id="334d5-165">組織内のすべてのユーザーに新しいポリシーを展開する前に、少人数のユーザーが使用するデバイスでテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="334d5-165">Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span>
>
> - <span data-ttu-id="334d5-166">また、ポリシーを展開する前に、Basic Mobility and Security にデバイスを登録する場合の潜在的な影響を組織に知らせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-166">Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="334d5-167">ポリシーの設定方法によっては、ポリシーに準拠していないデバイス (非準拠デバイス) がポリシーへのアクセスをブロックMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="334d5-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="334d5-168">非準拠のデバイスには、アプリ、写真、その他の個人情報がインストールされている場合もあります。デバイスがワイプされた場合、登録されているデバイス上で削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="334d5-169">詳細については、「Basic [Mobility and Security でモバイル デバイスをワイプする」を参照してください](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="334d5-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="334d5-170">ユーザーがデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="334d5-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="334d5-171">モバイル デバイス管理ポリシーを作成して展開した後、デバイス ポリシーが適用される組織内のライセンスを取得した Microsoft 365 ユーザーは、次回モバイル デバイスから Microsoft 365 にサインインすると、登録メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="334d5-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="334d5-172">電子メールとドキュメントにアクセスする前に、登録とライセンス認証Microsoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="334d5-173">詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="334d5-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="334d5-174">ユーザーの優先言語が登録プロセスでサポートされていない場合、ユーザーは別の言語でモバイル デバイスの登録通知と手順を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="334d5-175">モバイル デバイスでの登録プロセスで現在Microsoft 365サポートされている言語は一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="334d5-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="334d5-176">Android または iOS デバイスを使用しているユーザーは、登録プロセスのポータル サイトアプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="334d5-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-content"></a><span data-ttu-id="334d5-177">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="334d5-177">Related content</span></span>

<span data-ttu-id="334d5-178">[基本モビリティとセキュリティの機能](capabilities.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="334d5-178">[Capabilities of Basic Mobility and Security](capabilities.md) (article)</span></span>\
<span data-ttu-id="334d5-179">[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="334d5-179">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>