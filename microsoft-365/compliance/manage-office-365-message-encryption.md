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
description: Office 365 Message Encryption (OME) の設定を終了したら、いくつかの方法で展開をカスタマイズする方法について説明します。
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815434"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="9faaf-103">Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="9faaf-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="9faaf-104">Office 365 Message Encryption (OME) の設定を終了すると、いくつかの方法で展開の構成をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="9faaf-105">たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web の [**暗号化**] ボタンを表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="9faaf-106">この記事のタスクでは、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="9faaf-107">Google、Yahoo、Microsoft アカウントの受信者がこれらのアカウントを使用して Office 365 メッセージ暗号化ポータルにサインインできるかどうかを管理する</span><span class="sxs-lookup"><span data-stu-id="9faaf-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="9faaf-108">新しい Office 365 メッセージ暗号化機能をセットアップすると、組織内のユーザーは組織外の受信者にメッセージを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9faaf-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="9faaf-109">受信者が Google account、Yahoo アカウント、Microsoft アカウントなどの*ソーシャル id*を使用している場合、受信者はソーシャル ID で OME ポータルにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="9faaf-110">必要に応じて、受信者がソーシャル Id を使用して OME ポータルにサインインすることを許可しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="9faaf-111">受信者がソーシャル Id を使用して OME ポータルにサインインできるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="9faaf-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="9faaf-112">[リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-112">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="9faaf-113">次のように、指定された引数を指定して、OMEConfiguration/コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="9faaf-114">たとえば、ソーシャル Id を無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="9faaf-115">ソーシャル Id を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="9faaf-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="9faaf-116">Office 365 メッセージ暗号化ポータルの1回限りのパスコードの使用を管理する</span><span class="sxs-lookup"><span data-stu-id="9faaf-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="9faaf-117">OME によって暗号化されたメッセージの受信者が Outlook を使用していない場合は、受信者によって使用されるアカウントに関係なく、受信者は、メッセージを読むことができる限られた時間の web 表示リンクを受信します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="9faaf-118">このリンクには、1回限りのパスコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9faaf-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="9faaf-119">管理者は、受信者がワンタイムパスコードを使用して OME ポータルにサインインできるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="9faaf-120">OME がワンタイムパスコードを生成するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="9faaf-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="9faaf-121">組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9faaf-122">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-122">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9faaf-123">OTPEnabled パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="9faaf-124">たとえば、ワンタイムパスコードを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="9faaf-125">1回限りのパスコードを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="9faaf-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="9faaf-126">Outlook on the web で [暗号化] ボタンの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="9faaf-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="9faaf-127">管理者は、このボタンをエンドユーザーに表示するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="9faaf-128">Outlook on the web に [暗号化] ボタンを表示するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="9faaf-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="9faaf-129">組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9faaf-130">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-130">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9faaf-131">SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="9faaf-132">たとえば、[**暗号化**] ボタンを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="9faaf-133">[**暗号化**] ボタンを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="9faaf-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="9faaf-134">IOS メールアプリユーザーの電子メールメッセージのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="9faaf-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="9faaf-135">IOS メールアプリは、Office 365 メッセージの暗号化で保護されたメッセージを解読できません。</span><span class="sxs-lookup"><span data-stu-id="9faaf-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="9faaf-136">Microsoft 365 管理者は、iOS メールアプリに配信されるメッセージに対してサービス側の復号化を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="9faaf-137">サービス側の復号化を使用することを選択すると、サービスは、復号化されたメッセージのコピーを iOS デバイスに送信します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="9faaf-138">クライアントデバイスは、復号化されたメッセージのコピーを格納します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="9faaf-139">また、iOS メールアプリでユーザーにクライアント側の使用権限が適用されない場合でも、メッセージは使用権限に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="9faaf-140">ユーザーは、メッセージをコピーまたは印刷する権限を持っていない場合でも、メッセージをコピーまたは印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="9faaf-141">ただし、ユーザーが Microsoft 365 メールサーバーを必要とする操作 (メッセージの転送など) を完了しようとしても、そのユーザーの使用権限が最初に付与されていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="9faaf-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="9faaf-142">ただし、エンドユーザーは、iOS メールアプリ内の別のアカウントからメッセージを転送することによって、"転送不可" の使用制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="9faaf-143">メールのサービス側の復号化を設定しているかどうかに関係なく、暗号化されたメールの添付ファイルと権限保護されたメールは、iOS メールアプリでは表示できません。</span><span class="sxs-lookup"><span data-stu-id="9faaf-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="9faaf-144">IOS メールアプリユーザーに暗号化されたメッセージを送信することを許可しない場合、ユーザーには、メッセージを表示する権限がないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="9faaf-145">既定では、電子メールメッセージのサービス側の復号化は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="9faaf-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="9faaf-146">詳細と、クライアント環境の表示の詳細については、「 [iPhone または iPad で暗号化されたメッセージを表示](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="9faaf-147">Office 365 メッセージの暗号化によって保護されたメッセージを iOS メールアプリのユーザーが表示できるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="9faaf-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="9faaf-148">組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9faaf-149">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-149">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9faaf-150">AllowRMSSupportForUnenlightenedApps パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="9faaf-151">たとえば、iOS メールアプリなどの unenlightened アプリに送信される前にメッセージを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="9faaf-152">また、暗号化されていないメッセージを unenlightened アプリに送信しないようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="9faaf-153">個々のメールボックスポリシー (OWA/ActiveSync) は、これらの設定を上書きします (つまり、それぞれの OWA メールボックスポリシーまたは ActiveSync メールボックスポリシーで False に設定されている場合は、これらの構成は適用されません)。</span><span class="sxs-lookup"><span data-stu-id="9faaf-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="9faaf-154">Web ブラウザメールクライアントの電子メール添付ファイルのサービス側復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="9faaf-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="9faaf-155">通常、Office 365 メッセージの暗号化を使用すると、添付ファイルは自動的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="9faaf-156">管理者は、ユーザーが web ブラウザーからダウンロードした電子メール添付ファイルに対して、サービス側の復号化を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="9faaf-157">サービス側の復号化を使用すると、ファイルの復号化されたコピーがサービスによってデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="9faaf-158">メッセージはまだ暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="9faaf-158">The message is still encrypted.</span></span> <span data-ttu-id="9faaf-159">また、電子メールの添付ファイルは、ブラウザーがクライアント側の使用権限をユーザーに適用しない場合でも、使用権限に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="9faaf-160">ユーザーは、元の権限がない場合でも、電子メールの添付ファイルをコピーまたは印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="9faaf-161">ただし、ユーザーが Microsoft 365 メールサーバーを必要とするアクション (添付ファイルの転送など) を完了しようとした場合、ユーザーが最初に使用権限を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="9faaf-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="9faaf-162">添付ファイルのサービス側の復号化を設定しているかどうかに関係なく、ユーザーは、暗号化されていて、権限で保護されたメールの添付ファイルを iOS メールアプリで表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="9faaf-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="9faaf-163">暗号化された電子メール添付ファイルを許可しない場合、既定では、ユーザーには添付ファイルを表示する権限がないというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="9faaf-164">Microsoft 365 で、[暗号化のみ] オプションを使用して電子メールおよび電子メール添付ファイルの暗号化を実装する方法の詳細については、「[暗号化のみ」のオプション](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="9faaf-165">Web ブラウザーからのダウンロード時に電子メールの添付ファイルの暗号化を解除するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="9faaf-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="9faaf-166">組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9faaf-167">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-167">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9faaf-168">DecryptAttachmentForEncryptOnly パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="9faaf-169">たとえば、ユーザーが web ブラウザーから電子メールの添付ファイルをダウンロードするときに、添付ファイルを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="9faaf-170">暗号化された電子メール添付ファイルをダウンロード時に残すようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="9faaf-171">すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取ることを確認する</span><span class="sxs-lookup"><span data-stu-id="9faaf-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="9faaf-172">カスタムブランド化テンプレートを使用すると、受信者が Outlook または web 上の Outlook を使用するのではなく、OME ポータルで暗号化された電子メールを読み取ることを指示するラッパーメールを強制的に受信することができます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="9faaf-173">受信者が受信するメールの使用方法をより細かく制御する場合は、この操作を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="9faaf-174">たとえば、外部の受信者が web ポータルで電子メールを表示する場合、電子メールの有効期限を設定し、電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="9faaf-175">これらの機能は、OME ポータルでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9faaf-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="9faaf-176">メールフロールールを作成するときは、[暗号化] オプションと [転送不可] オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9faaf-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="9faaf-177">カスタムテンプレートを使用して、すべての外部受信者が OME ポータルと暗号化された電子メールを強制的に使用するようにする</span><span class="sxs-lookup"><span data-stu-id="9faaf-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="9faaf-178">組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9faaf-179">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9faaf-180">New-transportrule コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="9faaf-181">各部分の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9faaf-181">where:</span></span>

   - <span data-ttu-id="9faaf-182">`mail flow rule name`は、新しいメールフロールールに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="9faaf-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="9faaf-183">`option name`は、またはのいずれか `Encrypt` `Do Not Forward` です。</span><span class="sxs-lookup"><span data-stu-id="9faaf-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="9faaf-184">`template name`は、カスタムブランド化テンプレートに指定した名前です (例 `OME Configuration` :)。</span><span class="sxs-lookup"><span data-stu-id="9faaf-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="9faaf-185">"OME Configuration" テンプレートを使用してすべての外部電子メールを暗号化し、暗号化のみのオプションを適用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="9faaf-186">"OME Configuration" テンプレートを使用してすべての外部電子メールを暗号化し、[転送しない] オプションを適用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="9faaf-187">電子メールメッセージと OME ポータルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="9faaf-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="9faaf-188">組織に合わせて OME をカスタマイズする方法の詳細については、「[組織のブランドを暗号化されたメッセージに追加](add-your-organization-brand-to-encrypted-messages.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="9faaf-189">OME の新機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="9faaf-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="9faaf-190">この記事は提供されていませんが、必要な場合は、OME の新機能を無効にすることは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="9faaf-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="9faaf-191">最初に、新しい OME 機能を使用するように作成したメールフロールールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9faaf-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="9faaf-192">メールフロールールの削除の詳細については、「[メールフロールールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-192">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="9faaf-193">次に、Exchange Online の PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="9faaf-194">OME の新機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="9faaf-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="9faaf-195">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9faaf-196">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9faaf-196">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9faaf-197">Web 上の Outlook で [**暗号化**] ボタンを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行することによって、そのボタンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="9faaf-198">それ以外の場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="9faaf-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="9faaf-199">OME の新機能を無効にするには、AzureRMSLicensingEnabled パラメーターを false に設定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9faaf-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
