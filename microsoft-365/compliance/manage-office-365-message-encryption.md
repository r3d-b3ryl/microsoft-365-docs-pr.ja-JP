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
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179872"
---
# <a name="manage-office-365-message-encryption"></a>Office 365 Message Encryption

OME (OME) のOffice 365 Message Encryptionしたら、いくつかの方法で展開の構成をカスタマイズできます。 たとえば、1 回のパス コードを有効にするかどうかを構成できます。[暗号化] ボタンを [暗号化] Outlook on the webなどです。 この記事のタスクでは、方法について説明します。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Google、Yahoo、Microsoft アカウントの受信者が、これらのアカウントを使用してポータルにサインインできるかどうかをOffice 365 Message Encryptionする

新しい組織の機能をOffice 365 Message Encryption、組織内のユーザーは組織外の受信者にメッセージを送信できます。 受信者が Google アカウント、Yahoo アカウント、Microsoft アカウントなどのソーシャル *ID* を使用している場合、受信者はソーシャル ID を使用して OME ポータルにサインインできます。 必要な場合は、受信者がソーシャル ID を使用して OME ポータルにサインインを許可しない場合に選択できます。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>受信者がソーシャル ID を使用して OME ポータルにサインインできるかどうかを管理するには
  
1. [Connect PowerShell をExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. SocialIdSignIn Set-OMEConfigurationを使用して、次のコマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   たとえば、ソーシャル ID を無効にするには、次のコマンドを実行します。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   ソーシャル ID を有効にするには、次の方法を使用します。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>ポータルの 1 回のパス コードの使用Office 365 Message Encryptionする

OME で暗号化されたメッセージの受信者が、受信者が使用するアカウントに関係なく、Outlook を使用しない場合、受信者は、メッセージを読み取る期間限定の Web ビュー リンクを受け取ります。 このリンクには、1 回のパス コードが含まれています。 管理者は、受信者がワンタイム パス コードを使用して OME ポータルにサインインできる場合に決定できます。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>OME が 1 回のパス コードを生成するかどうかを管理するには
  
1. 組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. OTPEnabled Set-OMEConfigurationを使用して、次のコマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   たとえば、1 回のパス コードを無効にするには、次のコマンドを実行します。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   1 回のパス コードを有効にするには、次の方法を使用します。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>[暗号化] ボタンの表示を管理Outlook on the web

管理者は、このボタンをエンド ユーザーに表示するかどうかを管理できます。
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>[暗号化] ボタンが [暗号化] ウィンドウに表示されるかどうかをOutlook on the web
  
1. 組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. -SimplifiedClientAccessEnabled パラメーターSet-IRMConfigurationを使用して、次のコマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   たとえば、[暗号化] ボタンを **無効にするには、次の操作を** 行います。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   [暗号化] ボタン **を有効にするには、次の操作を** 行います。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>iOS メール アプリ ユーザーの電子メール メッセージのサービス側の復号化を有効にする

iOS メール アプリは、アプリで保護されたメッセージを復号化Office 365 Message Encryption。 管理者はMicrosoft 365、iOS メール アプリに配信されるメッセージに対してサービス側の復号化を適用できます。 サービス側の復号化を使用する場合、サービスはメッセージの暗号化解除されたコピーを iOS デバイスに送信します。 クライアント デバイスは、メッセージの暗号化解除されたコピーを格納します。 また、iOS メール アプリがユーザーにクライアント側の使用権限を適用しない場合でも、使用権に関する情報も保持されます。 ユーザーは、最初にメッセージをコピーまたは印刷する権限を持っていなくても、コピーまたは印刷できます。 ただし、ユーザーがメッセージの転送など、Microsoft 365 メール サーバーを必要とするアクションを完了しようとすると、ユーザーが最初に使用権を持っていなかった場合、サーバーはアクションを許可しません。 ただし、エンド ユーザーは、iOS メール アプリ内の別のアカウントからメッセージを転送することで、"転送しない" 使用制限を回避できます。 サービス側でメールの暗号化解除を設定したかどうかに関係なく、暗号化されたメールと権利で保護されたメールへの添付ファイルを iOS メール アプリで表示できません。
  
暗号化解除されたメッセージを iOS メール アプリ ユーザーに送信しない場合、ユーザーはメッセージを表示する権限を持たなかったというメッセージを受信します。 既定では、サービス側の電子メール メッセージの復号化は有効になっていません。
  
クライアント エクスペリエンスの詳細とビューについては、「暗号化されたメッセージをユーザーまたはユーザーに表示する[iPhone」をiPad。](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>iOS メール アプリのユーザーがユーザーによって保護されたメッセージを表示できるかどうかをOffice 365 Message Encryption
  
1. 組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. AllowRMSSupportForUnenlightenedApps パラメーターを使用して、次のコマンドレットを実行します。 Set-ActiveSyncOrganizations

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   たとえば、iOS メール アプリのような、ライトされていないアプリにメッセージが送信される前にメッセージを復号化するサービスを構成するには、次の手順を実行します。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   または、暗号化解除されたメッセージをライト解除されていないアプリに送信しないサービスを構成するには、次の手順を実行します。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> 個々のメールボックス ポリシー (OWA/ActiveSync) は、これらの設定を上書きします (つまり、-IRMEnabled がそれぞれの OWA メールボックス ポリシーまたは ActiveSync メールボックス ポリシー内で False に設定されている場合、これらの構成は適用されません)。

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Web ブラウザーのメール クライアントのメール添付ファイルのサービス側の復号化を有効にする

通常、メッセージ暗号化を使用Office 365添付ファイルは自動的に暗号化されます。 管理者は、ユーザーが Web ブラウザーからダウンロードする電子メールの添付ファイルに対して、サービス側の復号化を適用できます。
  
サービス側の復号化を使用すると、サービスはファイルの暗号化解除されたコピーをデバイスに送信します。 メッセージは引き続き暗号化されます。 電子メールの添付ファイルは、ブラウザーがユーザーにクライアント側の使用権限を適用しない場合でも、使用権に関する情報を保持します。 ユーザーは、電子メールの添付ファイルをコピーまたは印刷できます。元の権限を持っていなくても、ユーザーは電子メールの添付ファイルを印刷できます。 ただし、ユーザーが添付ファイルの転送など、Microsoft 365 メール サーバーを必要とするアクションを完了しようとすると、ユーザーが最初に使用権を持っていなかった場合、サーバーはアクションを許可しません。
  
サービス側で添付ファイルの暗号化解除を設定したかどうかに関係なく、ユーザーは iOS メール アプリで暗号化されたメールおよび権利保護されたメールに対する添付ファイルを表示できません。
  
暗号化解除された電子メールの添付ファイルを許可しない場合(既定)、ユーザーは添付ファイルを表示する権限を持たなかったというメッセージを受信します。
  
Microsoft 365 オプションを使用して電子メールと電子メール添付ファイルの暗号化を実装する方法の詳細については、「Encrypt-Only の暗号化のみオプション」を[参照してください。](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Web ブラウザーからのダウンロード時に電子メールの添付ファイルが復号化されるかどうかを管理するには
  
1. 組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. DecryptAttachmentForEncryptOnly パラメーターを使用して、Set-IRMConfigurationコマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   たとえば、ユーザーが Web ブラウザーから電子メール添付ファイルをダウンロードするときにメールの添付ファイルを復号化するサービスを構成するには、次の手順を実行します。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   暗号化された電子メールの添付ファイルをダウンロード時にそのまま残すサービスを構成するには、次の手順を実行します。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取る

カスタム ブランド テンプレートを使用すると、Outlook または Outlook on the web を使用する代わりに、受信者に OME ポータルで暗号化されたメールを読み取るメールを送信するラッパー メールを強制的に受信できます。 受信者が受信したメールの使い方を制御する場合は、これを行う必要があります。 たとえば、外部の受信者が Web ポータルで電子メールを表示する場合は、メールの有効期限を設定し、電子メールを取り消します。 これらの機能は、OME ポータルを通じてのみサポートされます。 メール フロー ルールを作成する場合は、[暗号化] オプションと [転送しない] オプションを使用できます。

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>カスタム テンプレートを使用して、すべての外部受信者に強制的に OME ポータルを使用し、暗号化された電子メールを使用する

1. 組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. 次のコマンドレットNew-TransportRule実行します。

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    各部分の意味は次のとおりです。

   - `mail flow rule name` は、新しいメール フロー ルールに使用する名前です。

   - `option name` は、 `Encrypt` または `Do Not Forward` です。

   - `template name` は、カスタム ブランド テンプレートを指定した名前です。たとえば `OME Configuration` 。

   "OME 構成" テンプレートを使用してすべての外部メールを暗号化し、次のオプションをEncrypt-Onlyします。

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   "OME 構成" テンプレートを使用してすべての外部メールを暗号化し、[転送しない] オプションを適用するには、次の手順を実行します。

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>電子メール メッセージと OME ポータルの外観をカスタマイズする

組織の OME をカスタマイズする方法の詳細については、「暗号化されたメッセージに組織のブランドを追加 [する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disable-the-new-capabilities-for-ome"></a>OME の新機能を無効にする

この機能が実現しない場合は、OME の新機能を無効にした方が非常に簡単です。 最初に、新しい OME 機能を使用して作成したメール フロー ルールを削除する必要があります。 メール フロー ルールの削除の詳細については、「メール フロー ルールの [管理」を参照してください](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。 次に、PowerShell の次の手順Exchange Onlineします。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>OME の新機能を無効にするには
  
1. 組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. [暗号化]**ボタンを** 有効Outlook on the web、SimplifiedClientAccessEnabled パラメーターを使用して Set-IRMConfiguration コマンドレットを実行して無効にします。 それ以外の場合は、この手順をスキップします。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. AzureRMSLicensingEnabled パラメーターを false に設定Set-IRMConfigurationコマンドレットを実行して、OME の新機能を無効にします。

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
