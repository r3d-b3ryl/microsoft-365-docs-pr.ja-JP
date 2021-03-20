---
title: Office 365 Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 365 Message Encryption (OME) Office設定が完了したら、いくつかの方法で展開をカスタマイズする方法について説明します。
ms.openlocfilehash: 06e9d22d51c05fe9f7bc4c1a014607feafbf2dba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908187"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="a5e9d-103">Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="a5e9d-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="a5e9d-104">365 Message Encryption (OME) Office設定が完了したら、いくつかの方法で展開の構成をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="a5e9d-105">たとえば、ワンタイム パス コードを有効にするか、Outlook on the  Web で [暗号化] ボタンを表示するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="a5e9d-106">この記事のタスクでは、方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="a5e9d-107">Google、Yahoo、Microsoft アカウントの受信者が、これらのアカウントを使用して 365 メッセージ暗号化ポータルにサインインOffice管理する</span><span class="sxs-lookup"><span data-stu-id="a5e9d-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="a5e9d-108">365 メッセージ暗号化Officeを設定すると、組織内のユーザーは組織外の受信者にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="a5e9d-109">受信者が Google アカウント、Yahoo アカウント、Microsoft アカウントなどのソーシャル *ID* を使用している場合、受信者はソーシャル ID を使用して OME ポータルにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="a5e9d-110">必要な場合は、受信者がソーシャル ID を使用して OME ポータルにサインインを許可しない場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="a5e9d-111">受信者がソーシャル ID を使用して OME ポータルにサインインできるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="a5e9d-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="a5e9d-112">[リモート PowerShell を使用して Exchange Online に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5e9d-113">SocialIdSignIn Set-OMEConfigurationを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="a5e9d-114">たとえば、ソーシャル ID を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="a5e9d-115">ソーシャル ID を有効にするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="a5e9d-116">365 メッセージ暗号化ポータルの 1 回Officeコードの使用を管理する</span><span class="sxs-lookup"><span data-stu-id="a5e9d-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="a5e9d-117">OME で暗号化されたメッセージの受信者が Outlook を使用しない場合、受信者が使用するアカウントに関係なく、受信者は、メッセージを読み取る期間限定の Web ビュー リンクを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="a5e9d-118">このリンクには、1 回のパス コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="a5e9d-119">管理者は、受信者がワンタイム パス コードを使用して OME ポータルにサインインできる場合に決定できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="a5e9d-120">OME が 1 回のパス コードを生成するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="a5e9d-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="a5e9d-121">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a5e9d-122">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5e9d-123">OTPEnabled Set-OMEConfigurationを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="a5e9d-124">たとえば、1 回のパス コードを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="a5e9d-125">1 回のパス コードを有効にするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="a5e9d-126">Outlook on the web の [暗号化] ボタンの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="a5e9d-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="a5e9d-127">管理者は、このボタンをエンド ユーザーに表示するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="a5e9d-128">Outlook on the web に [暗号化] ボタンが表示されるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="a5e9d-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="a5e9d-129">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a5e9d-130">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5e9d-131">-SimplifiedClientAccessEnabled パラメーターSet-IRMConfigurationを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="a5e9d-132">たとえば、[暗号化] ボタンを **無効にするには、次の操作を** 行います。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="a5e9d-133">[暗号化] ボタン **を有効にするには、次の操作を** 行います。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="a5e9d-134">iOS メール アプリ ユーザーの電子メール メッセージのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="a5e9d-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="a5e9d-135">iOS メール アプリは、365 メッセージ暗号化で保護されたOffice復号化できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="a5e9d-136">Microsoft 365 管理者は、iOS メール アプリに配信されるメッセージに対してサービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="a5e9d-137">サービス側の復号化を使用する場合、サービスはメッセージの暗号化解除されたコピーを iOS デバイスに送信します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="a5e9d-138">クライアント デバイスは、メッセージの暗号化解除されたコピーを格納します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="a5e9d-139">また、iOS メール アプリがユーザーにクライアント側の使用権限を適用しない場合でも、使用権に関する情報も保持されます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="a5e9d-140">ユーザーは、最初にメッセージをコピーまたは印刷する権限を持っていなくても、コピーまたは印刷できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="a5e9d-141">ただし、ユーザーがメッセージの転送など、Microsoft 365 メール サーバーを必要とするアクションを完了しようとすると、ユーザーが最初に使用権を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="a5e9d-142">ただし、エンド ユーザーは、iOS メール アプリ内の別のアカウントからメッセージを転送することで、"転送しない" 使用制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="a5e9d-143">サービス側でメールの暗号化解除を設定したかどうかに関係なく、暗号化されたメールと権利で保護されたメールへの添付ファイルを iOS メール アプリで表示できません。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="a5e9d-144">暗号化解除されたメッセージを iOS メール アプリ ユーザーに送信しない場合、ユーザーはメッセージを表示する権限を持たなかったというメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="a5e9d-145">既定では、サービス側の電子メール メッセージの復号化は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="a5e9d-146">クライアント エクスペリエンスの詳細とビューについては、「iPhone または iPad で暗号化されたメッセージを表示する [」を参照してください](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="a5e9d-147">iOS メール アプリのユーザーが 365 Message Encryption で保護されたOffice管理するには</span><span class="sxs-lookup"><span data-stu-id="a5e9d-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="a5e9d-148">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a5e9d-149">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5e9d-150">AllowRMSSupportForUnenlightenedApps パラメーターを使用して、次のコマンドレットを実行します。 Set-ActiveSyncOrganizations</span><span class="sxs-lookup"><span data-stu-id="a5e9d-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="a5e9d-151">たとえば、iOS メール アプリのような、ライトされていないアプリにメッセージが送信される前にメッセージを復号化するサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="a5e9d-152">または、暗号化解除されたメッセージをライト解除されていないアプリに送信しないサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="a5e9d-153">個々のメールボックス ポリシー (OWA/ActiveSync) は、これらの設定を上書きします (つまり、-IRMEnabled がそれぞれの OWA メールボックス ポリシーまたは ActiveSync メールボックス ポリシー内で False に設定されている場合、これらの構成は適用されません)。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="a5e9d-154">Web ブラウザーのメール クライアントのメール添付ファイルのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="a5e9d-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="a5e9d-155">通常、365 メッセージOffice使用すると、添付ファイルは自動的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="a5e9d-156">管理者は、ユーザーが Web ブラウザーからダウンロードする電子メールの添付ファイルに対して、サービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="a5e9d-157">サービス側の復号化を使用すると、サービスはファイルの暗号化解除されたコピーをデバイスに送信します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="a5e9d-158">メッセージは引き続き暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-158">The message is still encrypted.</span></span> <span data-ttu-id="a5e9d-159">電子メールの添付ファイルは、ブラウザーがユーザーにクライアント側の使用権限を適用しない場合でも、使用権に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="a5e9d-160">ユーザーは、電子メールの添付ファイルをコピーまたは印刷できます。元の権限を持っていなくても、ユーザーは電子メールの添付ファイルを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="a5e9d-161">ただし、ユーザーが Microsoft 365 メール サーバーを必要とするアクション (添付ファイルの転送など) を完了しようとすると、ユーザーが最初に使用権を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="a5e9d-162">サービス側で添付ファイルの暗号化解除を設定したかどうかに関係なく、ユーザーは iOS メール アプリで暗号化されたメールおよび権利保護されたメールに対する添付ファイルを表示できません。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="a5e9d-163">暗号化解除された電子メールの添付ファイルを許可しない場合(既定)、ユーザーは添付ファイルを表示する権限を持たなかったというメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="a5e9d-164">Microsoft 365 が Encrypt-Only オプションを使用して電子メールと電子メール添付ファイルの暗号化を実装する方法の詳細については、「電子メールの暗号化のみオプション」を [参照してください。](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="a5e9d-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="a5e9d-165">Web ブラウザーからのダウンロード時に電子メールの添付ファイルが復号化されるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="a5e9d-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="a5e9d-166">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a5e9d-167">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5e9d-168">DecryptAttachmentForEncryptOnly パラメーターを使用して、Set-IRMConfigurationコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="a5e9d-169">たとえば、ユーザーが Web ブラウザーから電子メール添付ファイルをダウンロードするときにメールの添付ファイルを復号化するサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="a5e9d-170">暗号化された電子メールの添付ファイルをダウンロード時にそのまま残すサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="a5e9d-171">すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="a5e9d-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="a5e9d-172">カスタム ブランド テンプレートを使用すると、Outlook または Outlook on the web を使用する代わりに、受信者に OME ポータルで暗号化されたメールを読み取るメールを送信するラッパー メールを強制的に受信できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="a5e9d-173">受信者が受信したメールの使い方を制御する場合は、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="a5e9d-174">たとえば、外部の受信者が Web ポータルで電子メールを表示する場合は、メールの有効期限を設定し、電子メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="a5e9d-175">これらの機能は、OME ポータルを通じてのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="a5e9d-176">メール フロー ルールを作成する場合は、[暗号化] オプションと [転送しない] オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="a5e9d-177">カスタム テンプレートを使用して、すべての外部受信者に強制的に OME ポータルを使用し、暗号化された電子メールを使用する</span><span class="sxs-lookup"><span data-stu-id="a5e9d-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="a5e9d-178">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a5e9d-179">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5e9d-180">次のコマンドレットNew-TransportRule実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="a5e9d-181">各部分の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-181">where:</span></span>

   - <span data-ttu-id="a5e9d-182">`mail flow rule name` は、新しいメール フロー ルールに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="a5e9d-183">`option name` は、 `Encrypt` または `Do Not Forward` です。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="a5e9d-184">`template name` は、カスタム ブランド テンプレートを指定した名前です。たとえば `OME Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="a5e9d-185">"OME 構成" テンプレートを使用してすべての外部メールを暗号化し、次のオプションをEncrypt-Onlyします。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="a5e9d-186">"OME 構成" テンプレートを使用してすべての外部メールを暗号化し、[転送しない] オプションを適用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="a5e9d-187">電子メール メッセージと OME ポータルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a5e9d-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="a5e9d-188">組織の OME をカスタマイズする方法の詳細については、「暗号化されたメッセージに組織のブランドを追加 [する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="a5e9d-189">OME の新機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="a5e9d-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="a5e9d-190">この機能が実現しない場合は、OME の新機能を無効にした方が非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="a5e9d-191">最初に、新しい OME 機能を使用して作成したメール フロー ルールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="a5e9d-192">メール フロー ルールの削除の詳細については、「メール フロー ルールの [管理」を参照してください](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="a5e9d-193">次に、Exchange Online PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="a5e9d-194">OME の新機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="a5e9d-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="a5e9d-195">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a5e9d-196">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5e9d-197">Outlook on the web で **[** 暗号化] ボタンを有効にした場合は、簡略化されたClientAccessEnabled パラメーターを使用して Set-IRMConfiguration コマンドレットを実行して無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="a5e9d-198">それ以外の場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="a5e9d-199">AzureRMSLicensingEnabled パラメーターを false に設定Set-IRMConfigurationコマンドレットを実行して、OME の新機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5e9d-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```