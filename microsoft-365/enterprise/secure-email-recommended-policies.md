---
title: セキュリティで保護された電子メールの推奨されるポリシー - Microsoft 365 Enterprise | Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 101ebbe46b9f49a1a450c4cb22b5d5f67ce1b322
ms.sourcegitcommit: bd487d36b04b8f8caf10900e8c5237f9ccf9e072
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "37654026"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="826b1-103">電子メールをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="826b1-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="826b1-104">この記事では、推奨される id とデバイスアクセスポリシーを実装して、先進認証および条件付きアクセスをサポートする組織の電子メールと電子メールクライアントを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="826b1-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="826b1-105">このガイダンスは、[一般的な id とデバイスのアクセスポリシー](identity-access-policies.md)を基に作成されており、さらにいくつかの推奨事項も含まれています。</span><span class="sxs-lookup"><span data-stu-id="826b1-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="826b1-106">これらの推奨事項は、ニーズの粒度 (**基準**、**機密**、**高規制**) に基づいて適用できる、セキュリティと保護の3つの異なる層に基づいています。</span><span class="sxs-lookup"><span data-stu-id="826b1-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="826b1-107">これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="826b1-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="826b1-108">これらの推奨事項では、ユーザーがモバイルデバイスの iOS および Android 用の Outlook を含むモダンメールクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="826b1-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="826b1-109">IOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="826b1-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="826b1-110">これらのモバイル Outlook アプリは、モバイル使用をサポートし、他の Microsoft クラウドセキュリティ機能と連携するセキュリティ機能を備えた設計も行われています。</span><span class="sxs-lookup"><span data-stu-id="826b1-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="826b1-111">詳細については、「 [iOS および Android 用の OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="826b1-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="updating-common-policies-to-include-email"></a><span data-ttu-id="826b1-112">電子メールを含めるための共通ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="826b1-112">Updating common policies to include email</span></span>

<span data-ttu-id="826b1-113">次の図は、一般的な id およびデバイスアクセスポリシーを示し、電子メールを保護するために更新する必要があるポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="826b1-113">The following diagram illustrates the common identity and device access policies and indicates which policies need to be updated to protect email.</span></span> <span data-ttu-id="826b1-114">ActiveSync クライアントをブロックする Exchange Online の新しいルールの追加に注意してください。</span><span class="sxs-lookup"><span data-stu-id="826b1-114">Note the addition of a new rule for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="826b1-115">これにより、Outlook mobile が強制的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="826b1-115">This forces the use of Outlook mobile.</span></span>

![メールを保護するためのポリシー更新の概要](../images/identity-access-ruleset-mail.png)

<span data-ttu-id="826b1-117">ポリシーの設定時に Exchange Online と Outlook がポリシーのスコープに含まれていた場合は、ActiveSync クライアントをブロックするために新しいポリシーを作成するだけでよいことになります。</span><span class="sxs-lookup"><span data-stu-id="826b1-117">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="826b1-118">次の表に記載されているポリシーを確認し、推奨される追加を行うか、またはこれらが既に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="826b1-118">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="826b1-119">各ルールは、[一般的な id およびデバイスアクセスポリシー](identity-access-policies.md)の記事に記載されている関連する構成手順にリンクします。</span><span class="sxs-lookup"><span data-stu-id="826b1-119">Each rule links to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="826b1-120">保護レベル</span><span class="sxs-lookup"><span data-stu-id="826b1-120">Protection level</span></span>|<span data-ttu-id="826b1-121">ポリシー</span><span class="sxs-lookup"><span data-stu-id="826b1-121">Policies</span></span>|<span data-ttu-id="826b1-122">詳細情報</span><span class="sxs-lookup"><span data-stu-id="826b1-122">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="826b1-123">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="826b1-123">**Baseline**</span></span>|[<span data-ttu-id="826b1-124">サインインリスクが*中*または*高*の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="826b1-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="826b1-125">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="826b1-125">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="826b1-126">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="826b1-126">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="826b1-127">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="826b1-127">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="826b1-128">アプリ保護ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="826b1-128">Define app protection policies</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="826b1-129">Outlook がアプリの一覧に含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="826b1-129">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="826b1-130">各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。</span><span class="sxs-lookup"><span data-stu-id="826b1-130">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="826b1-131">承認済みアプリの要求</span><span class="sxs-lookup"><span data-stu-id="826b1-131">Require approved apps</span></span>](identity-access-policies.md#require-approved-apps)|<span data-ttu-id="826b1-132">クラウドアプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="826b1-132">Include Exchange Online in the list of cloud apps</span></span>|
|        |[<span data-ttu-id="826b1-133">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="826b1-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="826b1-134">クラウドアプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="826b1-134">Include Exchange Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="826b1-135">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="826b1-135">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="826b1-136">この新しいポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="826b1-136">Add this new policy</span></span>| 
|<span data-ttu-id="826b1-137">**機密**</span><span class="sxs-lookup"><span data-stu-id="826b1-137">**Sensitive**</span></span>|[<span data-ttu-id="826b1-138">サインインリスクが*低*、*中*、*高*のときに MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="826b1-138">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="826b1-139">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="826b1-139">Include Exchange Online in the assignment of cloud apps</span></span>|
|         |[<span data-ttu-id="826b1-140">準拠*して*いる pc とモバイルデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="826b1-140">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="826b1-141">クラウドアプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="826b1-141">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="826b1-142">**高度な規制**</span><span class="sxs-lookup"><span data-stu-id="826b1-142">**Highly regulated**</span></span>|[<span data-ttu-id="826b1-143">*常に*MFA が必要</span><span class="sxs-lookup"><span data-stu-id="826b1-143">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="826b1-144">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="826b1-144">Include Exchange Online in the assignment of cloud apps</span></span>|

## <a name="block-activesync-clients"></a><span data-ttu-id="826b1-145">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="826b1-145">Block ActiveSync clients</span></span>

<span data-ttu-id="826b1-146">このポリシーでは、ActiveSync クライアントが他の条件付きアクセスルールをバイパスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="826b1-146">This policy prevents ActiveSync clients from bypassing other conditional access rules.</span></span> <span data-ttu-id="826b1-147">ルール構成は、ActiveSync クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="826b1-147">The rule configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="826b1-148">[承認された**クライアントアプリを必要と**する] を選択すると、このポリシーは ActiveSync クライアントをブロックします。</span><span class="sxs-lookup"><span data-stu-id="826b1-148">By selecting **Require approved client app**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="826b1-149">このポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="826b1-149">To configure this policy:</span></span>

1. <span data-ttu-id="826b1-150">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="826b1-150">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="826b1-151">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="826b1-151">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="826b1-152">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="826b1-152">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="826b1-153">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="826b1-153">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="826b1-154">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="826b1-154">Choose **New policy**.</span></span>

5. <span data-ttu-id="826b1-155">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="826b1-155">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="826b1-156">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="826b1-156">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="826b1-157">**[アプリの選択**] を選択し、[ **Office 365 Exchange Online**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="826b1-157">Choose **Select apps**, select **Office 365 Exchange Online**.</span></span> <span data-ttu-id="826b1-158">**[選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="826b1-158">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="826b1-159">[**条件**] を選択してから、[**クライアントアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="826b1-159">Choose **Conditions**, and then choose **Client apps**.</span></span>

9. <span data-ttu-id="826b1-160">[**構成**] で、[**はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="826b1-160">For **Configure**, select **Yes**.</span></span> <span data-ttu-id="826b1-161">[**モバイルアプリ] と [デスクトップクライアント**] および [ **Exchange ActiveSync クライアント**] のみをチェックします。</span><span class="sxs-lookup"><span data-stu-id="826b1-161">Check only the following: **Mobile apps and desktop clients** and **Exchange ActiveSync clients**.</span></span> <span data-ttu-id="826b1-162">[ **Done**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="826b1-162">Choose **Done**.</span></span>

10. <span data-ttu-id="826b1-163">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="826b1-163">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="826b1-164">[**アクセス許可の付与**] を選択し、[**承認済みクライアントアプリの要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="826b1-164">Choose **Grant access**, select **Require approved client app**.</span></span>  <span data-ttu-id="826b1-165">複数のコントロールの場合は、[選択した**コントロールを必要とする**] を選択し、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="826b1-165">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span>

12. <span data-ttu-id="826b1-166">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="826b1-166">Choose **Create**.</span></span>

## <a name="setup-office-365-message-encryption"></a><span data-ttu-id="826b1-167">Office 365 メッセージの暗号化のセットアップ</span><span class="sxs-lookup"><span data-stu-id="826b1-167">Setup Office 365 message encryption</span></span>

<span data-ttu-id="826b1-168">新しい Office 365 Message Encryption (OME) 機能を使用すると、Azure Information Protection の保護機能を活用できるため、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="826b1-168">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="826b1-169">ユーザーは、Outlook.com、Gmail、その他の電子メールサービスを使用して、他の Office 365 組織および非 Office 365 ユーザーとの保護されたメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="826b1-169">Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="826b1-170">詳細については、「 [Office の新しい365メッセージ暗号化機能をセットアップ](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="826b1-170">For more information, see [Set up new Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span>

## <a name="next-steps"></a><span data-ttu-id="826b1-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="826b1-171">Next steps</span></span>

[<span data-ttu-id="826b1-172">SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項の詳細</span><span class="sxs-lookup"><span data-stu-id="826b1-172">Learn about policy recommendations for securing SharePoint Sites and files</span></span>](sharepoint-file-access-policies.md)
