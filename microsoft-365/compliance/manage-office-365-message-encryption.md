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
description: OME (OME) のOffice 365 Message Encryptionしたら、いくつかの方法で展開をカスタマイズする方法について説明します。
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650986"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="e61a5-103">Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="e61a5-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="e61a5-104">OME (OME) のOffice 365 Message Encryptionしたら、いくつかの方法で展開の構成をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="e61a5-105">たとえば、1 回のパス コードを有効にするか、Web 上の [暗号化] Outlookを表示するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="e61a5-106">この記事のタスクでは、方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="e61a5-107">Google、Yahoo、Microsoft アカウントの受信者が、これらのアカウントを使用してポータルにサインインできるかどうかをOffice 365 Message Encryptionする</span><span class="sxs-lookup"><span data-stu-id="e61a5-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e61a5-108">新しい組織の機能をOffice 365 Message Encryption、組織内のユーザーは組織外の受信者にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="e61a5-109">受信者が Google アカウント、Yahoo アカウント、Microsoft アカウントなどのソーシャル *ID* を使用している場合、受信者はソーシャル ID を使用して OME ポータルにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="e61a5-110">必要な場合は、受信者がソーシャル ID を使用して OME ポータルにサインインを許可しない場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="e61a5-111">受信者がソーシャル ID を使用して OME ポータルにサインインできるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="e61a5-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="e61a5-112">[Connect PowerShell をExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e61a5-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e61a5-113">SocialIdSignIn Set-OMEConfigurationを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="e61a5-114">たとえば、ソーシャル ID を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="e61a5-115">ソーシャル ID を有効にするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="e61a5-116">ポータルの 1 回のパス コードの使用Office 365 Message Encryptionする</span><span class="sxs-lookup"><span data-stu-id="e61a5-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e61a5-117">OME で暗号化されたメッセージの受信者が、受信者が使用するアカウントに関係なく、Outlook を使用しない場合、受信者は、メッセージを読み取る期間限定の Web ビュー リンクを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e61a5-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="e61a5-118">このリンクには、1 回のパス コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e61a5-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="e61a5-119">管理者は、受信者がワンタイム パス コードを使用して OME ポータルにサインインできる場合に決定できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="e61a5-120">OME が 1 回のパス コードを生成するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="e61a5-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="e61a5-121">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e61a5-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e61a5-122">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61a5-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e61a5-123">OTPEnabled Set-OMEConfigurationを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="e61a5-124">たとえば、1 回のパス コードを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="e61a5-125">1 回のパス コードを有効にするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="e61a5-126">Web 上の [暗号化] ボタンのOutlook管理する</span><span class="sxs-lookup"><span data-stu-id="e61a5-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="e61a5-127">管理者は、このボタンをエンド ユーザーに表示するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="e61a5-128">Web 上の [暗号化] ボタンが [暗号化] Outlook表示されるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="e61a5-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="e61a5-129">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e61a5-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e61a5-130">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61a5-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e61a5-131">-SimplifiedClientAccessEnabled パラメーターSet-IRMConfigurationを使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="e61a5-132">たとえば、[暗号化] ボタンを **無効にするには、次の操作を** 行います。</span><span class="sxs-lookup"><span data-stu-id="e61a5-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="e61a5-133">[暗号化] ボタン **を有効にするには、次の操作を** 行います。</span><span class="sxs-lookup"><span data-stu-id="e61a5-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="e61a5-134">iOS メール アプリ ユーザーの電子メール メッセージのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="e61a5-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="e61a5-135">iOS メール アプリは、アプリで保護されたメッセージを復号化Office 365 Message Encryption。</span><span class="sxs-lookup"><span data-stu-id="e61a5-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="e61a5-136">管理者はMicrosoft 365、iOS メール アプリに配信されるメッセージに対してサービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="e61a5-137">サービス側の復号化を使用する場合、サービスはメッセージの暗号化解除されたコピーを iOS デバイスに送信します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="e61a5-138">クライアント デバイスは、メッセージの暗号化解除されたコピーを格納します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="e61a5-139">また、iOS メール アプリがユーザーにクライアント側の使用権限を適用しない場合でも、使用権に関する情報も保持されます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e61a5-140">ユーザーは、最初にメッセージをコピーまたは印刷する権限を持っていなくても、コピーまたは印刷できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e61a5-141">ただし、ユーザーがメッセージの転送など、Microsoft 365 メール サーバーを必要とするアクションを完了しようとすると、ユーザーが最初に使用権を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="e61a5-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="e61a5-142">ただし、エンド ユーザーは、iOS メール アプリ内の別のアカウントからメッセージを転送することで、"転送しない" 使用制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="e61a5-143">サービス側でメールの暗号化解除を設定したかどうかに関係なく、暗号化されたメールと権利で保護されたメールへの添付ファイルを iOS メール アプリで表示できません。</span><span class="sxs-lookup"><span data-stu-id="e61a5-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="e61a5-144">暗号化解除されたメッセージを iOS メール アプリ ユーザーに送信しない場合、ユーザーはメッセージを表示する権限を持たなかったというメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="e61a5-145">既定では、サービス側の電子メール メッセージの復号化は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e61a5-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="e61a5-146">クライアント エクスペリエンスの詳細とビューについては、「暗号化されたメッセージをユーザーまたはユーザーに表示する[iPhone」をiPad。](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)</span><span class="sxs-lookup"><span data-stu-id="e61a5-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="e61a5-147">iOS メール アプリのユーザーがユーザーによって保護されたメッセージを表示できるかどうかをOffice 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="e61a5-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="e61a5-148">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e61a5-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e61a5-149">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61a5-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e61a5-150">AllowRMSSupportForUnenlightenedApps パラメーターを使用して、次のコマンドレットを実行します。 Set-ActiveSyncOrganizations</span><span class="sxs-lookup"><span data-stu-id="e61a5-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="e61a5-151">たとえば、iOS メール アプリのような、ライトされていないアプリにメッセージが送信される前にメッセージを復号化するサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="e61a5-152">または、暗号化解除されたメッセージをライト解除されていないアプリに送信しないサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="e61a5-153">個々のメールボックス ポリシー (OWA/ActiveSync) は、これらの設定を上書きします (つまり、-IRMEnabled がそれぞれの OWA メールボックス ポリシーまたは ActiveSync メールボックス ポリシー内で False に設定されている場合、これらの構成は適用されません)。</span><span class="sxs-lookup"><span data-stu-id="e61a5-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="e61a5-154">Web ブラウザーのメール クライアントのメール添付ファイルのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="e61a5-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="e61a5-155">通常、メッセージ暗号化を使用Office 365添付ファイルは自動的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="e61a5-156">管理者は、ユーザーが Web ブラウザーからダウンロードする電子メールの添付ファイルに対して、サービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="e61a5-157">サービス側の復号化を使用すると、サービスはファイルの暗号化解除されたコピーをデバイスに送信します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="e61a5-158">メッセージは引き続き暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-158">The message is still encrypted.</span></span> <span data-ttu-id="e61a5-159">電子メールの添付ファイルは、ブラウザーがユーザーにクライアント側の使用権限を適用しない場合でも、使用権に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e61a5-160">ユーザーは、電子メールの添付ファイルをコピーまたは印刷できます。元の権限を持っていなくても、ユーザーは電子メールの添付ファイルを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e61a5-161">ただし、ユーザーが添付ファイルの転送など、Microsoft 365 メール サーバーを必要とするアクションを完了しようとすると、ユーザーが最初に使用権を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="e61a5-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="e61a5-162">サービス側で添付ファイルの暗号化解除を設定したかどうかに関係なく、ユーザーは iOS メール アプリで暗号化されたメールおよび権利保護されたメールに対する添付ファイルを表示できません。</span><span class="sxs-lookup"><span data-stu-id="e61a5-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="e61a5-163">暗号化解除された電子メールの添付ファイルを許可しない場合(既定)、ユーザーは添付ファイルを表示する権限を持たなかったというメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="e61a5-164">Microsoft 365 オプションを使用して電子メールと電子メール添付ファイルの暗号化を実装する方法の詳細については、「Encrypt-Only の暗号化のみオプション」を[参照してください。](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="e61a5-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="e61a5-165">Web ブラウザーからのダウンロード時に電子メールの添付ファイルが復号化されるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="e61a5-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="e61a5-166">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e61a5-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e61a5-167">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61a5-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e61a5-168">DecryptAttachmentForEncryptOnly パラメーターを使用して、Set-IRMConfigurationコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="e61a5-169">たとえば、ユーザーが Web ブラウザーから電子メール添付ファイルをダウンロードするときにメールの添付ファイルを復号化するサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="e61a5-170">暗号化された電子メールの添付ファイルをダウンロード時にそのまま残すサービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="e61a5-171">すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="e61a5-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="e61a5-172">カスタム ブランド テンプレートを使用すると、受信者に、web 上で Outlook または Outlook を使用する代わりに、OME ポータルで暗号化されたメールを読み取るラッパー メールを強制的に受信できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="e61a5-173">受信者が受信したメールの使い方を制御する場合は、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e61a5-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="e61a5-174">たとえば、外部の受信者が Web ポータルで電子メールを表示する場合は、メールの有効期限を設定し、電子メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="e61a5-175">これらの機能は、OME ポータルを通じてのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="e61a5-176">メール フロー ルールを作成する場合は、[暗号化] オプションと [転送しない] オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e61a5-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="e61a5-177">カスタム テンプレートを使用して、すべての外部受信者に強制的に OME ポータルを使用し、暗号化された電子メールを使用する</span><span class="sxs-lookup"><span data-stu-id="e61a5-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="e61a5-178">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e61a5-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e61a5-179">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61a5-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e61a5-180">次のコマンドレットNew-TransportRule実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="e61a5-181">各部分の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e61a5-181">where:</span></span>

   - <span data-ttu-id="e61a5-182">`mail flow rule name` は、新しいメール フロー ルールに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="e61a5-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="e61a5-183">`option name` は、 `Encrypt` または `Do Not Forward` です。</span><span class="sxs-lookup"><span data-stu-id="e61a5-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="e61a5-184">`template name` は、カスタム ブランド テンプレートを指定した名前です。たとえば `OME Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="e61a5-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="e61a5-185">"OME 構成" テンプレートを使用してすべての外部メールを暗号化し、次のオプションをEncrypt-Onlyします。</span><span class="sxs-lookup"><span data-stu-id="e61a5-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="e61a5-186">"OME 構成" テンプレートを使用してすべての外部メールを暗号化し、[転送しない] オプションを適用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="e61a5-187">電子メール メッセージと OME ポータルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="e61a5-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="e61a5-188">組織の OME をカスタマイズする方法の詳細については、「暗号化されたメッセージに組織のブランドを追加 [する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e61a5-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e61a5-189">OME の新機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="e61a5-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="e61a5-190">この機能が実現しない場合は、OME の新機能を無効にした方が非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="e61a5-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="e61a5-191">最初に、新しい OME 機能を使用して作成したメール フロー ルールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e61a5-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="e61a5-192">メール フロー ルールの削除の詳細については、「メール フロー ルールの [管理」を参照してください](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="e61a5-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="e61a5-193">次に、PowerShell の次の手順Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="e61a5-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e61a5-194">OME の新機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="e61a5-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="e61a5-195">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e61a5-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e61a5-196">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61a5-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e61a5-197">Web 上で [**暗号化]** Outlookを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを使用して Set-IRMConfiguration コマンドレットを実行して無効にします。</span><span class="sxs-lookup"><span data-stu-id="e61a5-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="e61a5-198">それ以外の場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="e61a5-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="e61a5-199">AzureRMSLicensingEnabled パラメーターを false に設定Set-IRMConfigurationコマンドレットを実行して、OME の新機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e61a5-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
