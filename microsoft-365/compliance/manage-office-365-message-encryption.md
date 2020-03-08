---
title: Office 365 Message Encryption を管理する
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
description: Office 365 Message Encryption (OME) の設定を終了すると、いくつかの方法で展開の構成をカスタマイズできます。 たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web に [保護] ボタンを表示したり、その他の設定を行ったりすることができます。 この記事のタスクでは、その方法について説明します。
ms.openlocfilehash: 102d57681e049bf803b377fea97cc0fdb11affb2
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42562026"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="34779-105">Office 365 Message Encryption を管理する</span><span class="sxs-lookup"><span data-stu-id="34779-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="34779-106">Office 365 Message Encryption (OME) の設定を終了すると、いくつかの方法で展開の構成をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="34779-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="34779-107">たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web の [**暗号化**] ボタンを表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="34779-107">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="34779-108">この記事のタスクでは、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34779-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="34779-109">Google、Yahoo、Microsoft アカウントの受信者がこれらのアカウントを使用して Office 365 メッセージ暗号化ポータルにサインインできるかどうかを管理する</span><span class="sxs-lookup"><span data-stu-id="34779-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="34779-110">新しい Office 365 メッセージ暗号化機能をセットアップすると、組織内のユーザーは、Office 365 組織外の受信者にメッセージを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="34779-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="34779-111">受信者が Google account、Yahoo アカウント、Microsoft アカウントなどの*ソーシャル id*を使用している場合、受信者はソーシャル ID で OME ポータルにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="34779-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="34779-112">必要に応じて、受信者がソーシャル Id を使用して OME ポータルにサインインすることを許可しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="34779-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="34779-113">受信者がソーシャル Id を使用して OME ポータルにサインインできるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="34779-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="34779-114">[リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="34779-114">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="34779-115">次のように、指定された引数を指定して、OMEConfiguration/コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="34779-116">たとえば、ソーシャル Id を無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="34779-117">ソーシャル Id を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="34779-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="34779-118">Office 365 メッセージ暗号化ポータルの1回限りのパスコードの使用を管理する</span><span class="sxs-lookup"><span data-stu-id="34779-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="34779-119">OME によって暗号化されたメッセージの受信者が Outlook を使用していない場合は、受信者によって使用されるアカウントに関係なく、受信者は、メッセージを読むことができる限られた時間の web 表示リンクを受信します。</span><span class="sxs-lookup"><span data-stu-id="34779-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="34779-120">このリンクには、1回限りのパスコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34779-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="34779-121">管理者は、受信者がワンタイムパスコードを使用して OME ポータルにサインインできるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="34779-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="34779-122">OME がワンタイムパスコードを生成するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="34779-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="34779-123">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="34779-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="34779-124">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="34779-125">OTPEnabled パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="34779-126">たとえば、ワンタイムパスコードを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="34779-127">1回限りのパスコードを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="34779-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="34779-128">Outlook on the web で [暗号化] ボタンの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="34779-128">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="34779-129">管理者は、このボタンをエンドユーザーに表示するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="34779-129">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="34779-130">Outlook on the web に [暗号化] ボタンを表示するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="34779-130">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="34779-131">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="34779-131">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="34779-132">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="34779-133">SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-133">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="34779-134">たとえば、[**暗号化**] ボタンを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-134">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="34779-135">[**暗号化**] ボタンを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="34779-135">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="34779-136">IOS メールアプリユーザーの電子メールメッセージのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="34779-136">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="34779-137">IOS メールアプリは、Office 365 メッセージの暗号化で保護されたメッセージを解読できません。</span><span class="sxs-lookup"><span data-stu-id="34779-137">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="34779-138">Office 365 管理者は、iOS メールアプリに配信されるメッセージに対してサービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="34779-138">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="34779-139">サービス側の復号化を使用することを選択すると、サービスは、復号化されたメッセージのコピーを iOS デバイスに送信します。</span><span class="sxs-lookup"><span data-stu-id="34779-139">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="34779-140">クライアントデバイスは、復号化されたメッセージのコピーを格納します。</span><span class="sxs-lookup"><span data-stu-id="34779-140">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="34779-141">また、iOS メールアプリでユーザーにクライアント側の使用権限が適用されない場合でも、メッセージは使用権限に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="34779-141">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="34779-142">ユーザーは、メッセージをコピーまたは印刷する権限を持っていない場合でも、メッセージをコピーまたは印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="34779-142">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="34779-143">ただし、ユーザーが Office 365 メールサーバーを必要とする操作 (メッセージの転送など) を実行しようとした場合、ユーザーが最初に使用権限を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="34779-143">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="34779-144">ただし、エンドユーザーは、iOS メールアプリ内の別のアカウントからメッセージを転送することによって、"転送不可" の使用制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="34779-144">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="34779-145">メールのサービス側の復号化を設定しているかどうかに関係なく、暗号化されたメールの添付ファイルと権限保護されたメールは、iOS メールアプリでは表示できません。</span><span class="sxs-lookup"><span data-stu-id="34779-145">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="34779-146">IOS メールアプリユーザーに暗号化されたメッセージを送信することを許可しない場合、ユーザーには、メッセージを表示する権限がないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34779-146">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="34779-147">既定では、電子メールメッセージのサービス側の復号化は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="34779-147">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="34779-148">詳細と、クライアント環境の表示の詳細については、「 [iPhone または iPad で暗号化されたメッセージを表示](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-148">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="34779-149">Office 365 メッセージの暗号化によって保護されたメッセージを iOS メールアプリのユーザーが表示できるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="34779-149">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="34779-150">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="34779-150">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="34779-151">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-151">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="34779-152">AllowRMSSupportForUnenlightenedApps パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-152">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="34779-153">たとえば、iOS メールアプリなどの unenlightened アプリに送信される前にメッセージを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-153">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="34779-154">また、暗号化されていないメッセージを unenlightened アプリに送信しないようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-154">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="34779-155">個々のメールボックスポリシー (OWA/ActiveSync) は、これらの設定を上書きします (つまり、それぞれの OWA メールボックスポリシーまたは ActiveSync メールボックスポリシーで False に設定されている場合は、これらの構成は適用されません)。</span><span class="sxs-lookup"><span data-stu-id="34779-155">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="34779-156">Web ブラウザメールクライアントの電子メール添付ファイルのサービス側復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="34779-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="34779-157">通常、Office 365 メッセージの暗号化を使用すると、添付ファイルは自動的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="34779-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="34779-158">Office 365 管理者は、ユーザーが web ブラウザーからダウンロードした電子メール添付ファイルに対して、サービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="34779-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="34779-159">サービス側の復号化を使用すると、ファイルの復号化されたコピーがサービスによってデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="34779-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="34779-160">メッセージはまだ暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="34779-160">The message is still encrypted.</span></span> <span data-ttu-id="34779-161">また、電子メールの添付ファイルは、ブラウザーがクライアント側の使用権限をユーザーに適用しない場合でも、使用権限に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="34779-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="34779-162">ユーザーは、元の権限がない場合でも、電子メールの添付ファイルをコピーまたは印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="34779-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="34779-163">ただし、ユーザーが Office 365 メールサーバーを必要とするアクション (添付ファイルの転送など) を完了しようとした場合、ユーザーの使用権限が最初に付与されていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="34779-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="34779-164">添付ファイルのサービス側の復号化を設定しているかどうかに関係なく、ユーザーは、暗号化されていて、権限で保護されたメールの添付ファイルを iOS メールアプリで表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="34779-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="34779-165">暗号化された電子メール添付ファイルを許可しない場合、既定では、ユーザーには添付ファイルを表示する権限がないというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34779-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="34779-166">Office 365 で、[暗号化のみ] オプションを使用してメールおよび電子メール添付ファイルの暗号化を実装する方法の詳細については、「encryption [-only](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="34779-167">Web ブラウザーからのダウンロード時に電子メールの添付ファイルの暗号化を解除するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="34779-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="34779-168">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="34779-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="34779-169">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="34779-170">DecryptAttachmentForEncryptOnly パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="34779-171">たとえば、ユーザーが web ブラウザーから電子メールの添付ファイルをダウンロードするときに、添付ファイルを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="34779-172">暗号化された電子メール添付ファイルをダウンロード時に残すようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="34779-173">すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取ることを確認する</span><span class="sxs-lookup"><span data-stu-id="34779-173">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="34779-174">カスタムブランド化テンプレートを使用すると、受信者が Outlook または web 上の Outlook を使用するのではなく、OME ポータルで暗号化された電子メールを読み取ることを指示するラッパーメールを強制的に受信することができます。</span><span class="sxs-lookup"><span data-stu-id="34779-174">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="34779-175">受信者が受信するメールの使用方法をより細かく制御する場合は、この操作を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34779-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="34779-176">たとえば、外部の受信者が web ポータルで電子メールを表示する場合、電子メールの有効期限を設定し、電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="34779-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="34779-177">これらの機能は、OME ポータルでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34779-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="34779-178">メールフロールールを作成するときは、[暗号化] オプションと [転送不可] オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34779-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="34779-179">カスタムテンプレートを使用して、すべての外部受信者が OME ポータルと暗号化された電子メールを強制的に使用するようにする</span><span class="sxs-lookup"><span data-stu-id="34779-179">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="34779-180">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="34779-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="34779-181">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="34779-182">New-transportrule コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-182">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="34779-183">各部分の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34779-183">where:</span></span>

   - <span data-ttu-id="34779-184">`mail flow rule name`は、新しいメールフロールールに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="34779-184">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="34779-185">`option name`は、 `Encrypt`また`Do Not Forward`はのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="34779-185">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="34779-186">`template name`は、カスタムブランド化テンプレートに指定した名前です`OME Configuration`(例:)。</span><span class="sxs-lookup"><span data-stu-id="34779-186">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="34779-187">「1週間の販売」テンプレートを使用してすべての外部電子メールを暗号化し、暗号化のみのオプションを適用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34779-187">To encrypt all external email with the "One week sale" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<OME Configuration>"
   ```

   <span data-ttu-id="34779-188">"OME Configuration" テンプレートを使用してすべての外部電子メールを暗号化し、[転送しない] オプションを適用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-188">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<OME Configuration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="34779-189">電子メールメッセージと OME ポータルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="34779-189">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="34779-190">組織に合わせて OME をカスタマイズする方法の詳細については、「[組織のブランドを暗号化されたメッセージに追加](add-your-organization-brand-to-encrypted-messages.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-190">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="34779-191">OME の新機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="34779-191">Disable the new capabilities for OME</span></span>

<span data-ttu-id="34779-192">この記事は提供されていませんが、必要な場合は、OME の新機能を無効にすることは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="34779-192">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="34779-193">最初に、新しい OME 機能を使用するように作成したメールフロールールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34779-193">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="34779-194">メールフロールールの削除の詳細については、「[メールフロールールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-194">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="34779-195">次に、Exchange Online の PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-195">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="34779-196">OME の新機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="34779-196">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="34779-197">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="34779-197">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="34779-198">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-198">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="34779-199">Web 上の Outlook で [**暗号化**] ボタンを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行することによって、そのボタンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="34779-199">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="34779-200">それ以外の場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="34779-200">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="34779-201">OME の新機能を無効にするには、AzureRMSLicensingEnabled パラメーターを false に設定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34779-201">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
