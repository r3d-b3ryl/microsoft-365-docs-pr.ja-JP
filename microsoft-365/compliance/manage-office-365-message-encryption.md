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
ms.localizationpriority: medium
ms.date: 03/04/2022
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: メッセージ暗号化 (OME) Office 365設定が完了したら、いくつかの方法でデプロイをカスタマイズする方法について説明します。
ms.openlocfilehash: b3d7ffe5db987b9fb3bd29682c8e101ffd99946a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635285"
---
# <a name="manage-office-365-message-encryption"></a>Office 365 Message Encryption

メッセージ暗号化 (OME) Office 365設定が完了したら、いくつかの方法でデプロイの構成をカスタマイズできます。 たとえば、1 回限りのパス コードを有効にするか、Outlook on the webで **[暗号化**] ボタンを表示するかを構成できます。 この記事のタスクでは、その方法について説明します。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Google、Yahoo、Microsoft アカウントの受信者がこれらのアカウントを使用してOffice 365メッセージ暗号化ポータルにサインインできるかどうかを管理する

新しいOffice 365 メッセージ暗号化機能を設定すると、組織内のユーザーは、組織外の受信者にメッセージを送信できます。 受信者が Google アカウント、Yahoo アカウント、Microsoft アカウントなどの *ソーシャル ID を* 使用している場合、受信者はソーシャル ID を使用して OME ポータルにサインインできます。 必要に応じて、受信者がソーシャル ID を使用して OME ポータルにサインインできないように選択できます。

### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>受信者がソーシャル ID を使用して OME ポータルにサインインできるかどうかを管理するには

1. [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 次のように、SocialIdSignIn パラメーターを使用してSet-OMEConfigurationコマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   たとえば、ソーシャル ID を無効にするには、次のようにします。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   ソーシャル ID を有効にするには:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Office 365 メッセージ暗号化ポータルのワンタイム パス コードの使用を管理する

OME によって暗号化されたメッセージの受信者が、受信者が使用するアカウントに関係なく Outlook を使用しない場合、受信者はメッセージを読み取ることができる期間限定の Web ビュー リンクを受け取ります。 このリンクには、1 回限りのパス コードが含まれています。 管理者は、受信者がワンタイム パス コードを使用して OME ポータルにサインインできるかどうかを決定できます。

### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>OME で 1 回限りのパス コードが生成されるかどうかを管理するには

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用し、Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. OTPEnabled パラメーターを使用して、Set-OMEConfiguration コマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   たとえば、ワンタイム パス コードを無効にするには、次のようにします。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   ワンタイム パス コードを有効にするには:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Outlook on the webの [暗号化] ボタンの表示を管理する

管理者は、このボタンをエンド ユーザーに表示するかどうかを管理できます。

### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>[暗号化] ボタンがOutlook on the webに表示されるかどうかを管理するには

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用し、Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. SimplifiedClientAccessEnabled パラメーターを使用して、Set-IRMConfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   たとえば、[ **暗号化** ] ボタンを無効にするには、次のようにします。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   **[暗号化**] ボタンを有効にするには:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>iOS メール アプリ ユーザーのメール メッセージのサービス側復号化を有効にする

iOS メール アプリでは、Office 365メッセージ暗号化で保護されたメッセージを復号化できません。 Microsoft 365 管理者は、iOS メール アプリに配信されたメッセージにサービス側の復号化を適用できます。 サービス側の復号化を使用することを選択すると、サービスはメッセージの復号化されたコピーを iOS デバイスに送信します。 クライアント デバイスは、メッセージの暗号化解除されたコピーを格納します。 また、iOS メール アプリがクライアント側の使用権をユーザーに適用していない場合でも、このメッセージは使用権に関する情報を保持します。 ユーザーは、最初にメッセージをコピーする権限を持っていない場合でも、メッセージをコピーまたは印刷できます。 ただし、ユーザーが Microsoft 365 メール サーバーを必要とするアクション (メッセージの転送など) を完了しようとすると、ユーザーが最初に使用権を持っていない場合、サーバーはアクションを許可しません。 ただし、エンド ユーザーは、iOS メール アプリ内の別のアカウントからメッセージを転送することで、"転送しない" 使用制限を回避できます。 メールのサービス側の復号化を設定するかどうかに関係なく、暗号化されたメールと権限で保護されたメールの添付ファイルを iOS メール アプリで表示することはできません。

暗号化解除されたメッセージを iOS メール アプリユーザーに送信することを許可しない場合、ユーザーはメッセージを表示する権限がないことを示すメッセージを受け取ります。 既定では、電子メール メッセージのサービス側の復号化は有効になっていません。

詳細とクライアント エクスペリエンスの詳細については、「 [iPhone または iPad で暗号化されたメッセージを表示する](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)」を参照してください。

### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>iOS メール アプリのユーザーが Office 365 メッセージ暗号化によって保護されたメッセージを表示できるかどうかを管理するには

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用し、Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. AllowRMSSupportForUnenlightenedApps パラメーターを使用して、Set-ActiveSyncOrganizations コマンドレットを実行します。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   たとえば、iOS メール アプリなどの非対応アプリにメッセージが送信される前にメッセージを復号化するようにサービスを構成するには、次のようにします。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   または、暗号化されていないアプリに暗号化解除されたメッセージを送信しないようにサービスを構成するには、次の手順を実行します。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> 個々のメールボックス ポリシー (OWA/ActiveSync) は、これらの設定をオーバーライドします (つまり、それぞれの OWA メールボックス ポリシー内で -IRMEnabled が False に設定されている場合、または ActiveSync メールボックス ポリシーの場合、これらの構成は適用されません)。

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Web ブラウザーメール クライアントのメール添付ファイルのサービス側復号化を有効にする

通常、Office 365メッセージ暗号化を使用すると、添付ファイルは自動的に暗号化されます。 管理者は、ユーザーが Web ブラウザーからダウンロードするメール添付ファイルにサービス側の復号化を適用できます。

サービス側の復号化を使用すると、サービスはファイルの復号化されたコピーをデバイスに送信します。 メッセージは引き続き暗号化されます。 また、ブラウザーがクライアント側の使用権限をユーザーに適用していない場合でも、電子メールの添付ファイルは使用権限に関する情報を保持します。 ユーザーは、電子メールの添付ファイルをコピーまたは印刷できます。元のユーザーがメール添付ファイルをコピーする権限を持っていない場合でも、メールの添付ファイルをコピーまたは印刷できます。 ただし、ユーザーが Microsoft 365 メール サーバーを必要とするアクション (添付ファイルの転送など) を完了しようとすると、ユーザーが最初に使用権を持っていない場合、サーバーはアクションを許可しません。

添付ファイルのサービス側の復号化を設定するかどうかに関係なく、ユーザーは iOS メール アプリで暗号化された権限で保護されたメールへの添付ファイルを表示できません。

暗号化解除された電子メールの添付ファイル (既定) を許可しないことを選択した場合、ユーザーは添付ファイルを表示する権限がないことを示すメッセージを受け取ります。

Microsoft 365 がEncrypt-Only オプションを使用して電子メールと電子メールの添付ファイルの暗号化を実装する方法の詳細については、「[電子メールの暗号化のみオプション」を](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)参照してください。

### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Web ブラウザーからのダウンロード時に電子メールの添付ファイルが暗号化解除されるかどうかを管理するには

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用し、Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. DecryptAttachmentForEncryptOnly パラメーターを使用して、Set-IRMConfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   たとえば、ユーザーが Web ブラウザーから電子メールの添付ファイルをダウンロードしたときにメールの添付ファイルを復号化するようにサービスを構成するには、次のようにします。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   暗号化された電子メールの添付ファイルをそのままにするようにサービスを構成するには、次の手順を実行します。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取っていることを確認する

カスタム ブランド テンプレートを使用すると、Outlook やOutlook on the webを使用する代わりに、受信者に OME ポータルで暗号化されたメールを読み取るメッセージを送信するラッパー メールを受信者に強制的に受信させることができます。 受信者が受信したメールを使用する方法をより細かく制御する場合は、これを行う必要があります。 たとえば、外部の受信者が Web ポータルでメールを表示する場合、メールの有効期限を設定し、電子メールを取り消すことができます。 これらの機能は、OME ポータルでのみサポートされます。 メール フロー ルールを作成するときに、[暗号化] オプションと [転送不可] オプションを使用できます。

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>カスタム テンプレートを使用して、すべての外部受信者に OME ポータルと暗号化された電子メールの使用を強制する

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用し、Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. New-TransportRule コマンドレットを実行します。

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    各部分の意味は次のとおりです。

   - `mail flow rule name` は、新しいメール フロー ルールに使用する名前です。

   - `option name` は 、 `Encrypt` または `Do Not Forward`.

   - `template name` は、カスタム ブランド テンプレートに指定した名前です 。たとえば `OME Configuration`、

   "OME 構成" テンプレートを使用してすべての外部メールを暗号化し、Encrypt-Only オプションを適用するには:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   "OME 構成" テンプレートを使用してすべての外部メールを暗号化し、[転送不可] オプションを適用するには:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>電子メール メッセージと OME ポータルの外観をカスタマイズする

組織のMicrosoft Purview Message Encryptionをカスタマイズする方法の詳細については、「[暗号化されたメッセージに組織のブランドを追加する」を](add-your-organization-brand-to-encrypted-messages.md)参照してください。 暗号化されたメッセージを追跡および取り消す機能を有効にするには、カスタム ブランドを OME ポータルに追加する必要があります。

## <a name="disable-microsoft-purview-message-encryption"></a>Microsoft Purview Message Encryptionを無効にする

それが実現しないことを願っていますが、必要に応じて、Microsoft Purview Message Encryptionを無効にすることは非常に簡単です。 まず、Microsoft Purview Message Encryptionを使用して作成したメール フロー ルールをすべて削除する必要があります。 メール フロー ルールの削除の詳細については、「 [メール フロー](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) ルールの管理」を参照してください。 次に、PowerShell Exchange Onlineで次の手順を実行します。

### <a name="to-disable-microsoft-purview-message-encryption"></a>Microsoft Purview Message Encryptionを無効にするには

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、powerShell Exchange Online接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. Outlook on the webで **[暗号化**] ボタンを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを使用してSet-IRMConfigurationコマンドレットを実行して無効にします。 それ以外の場合は、この手順をスキップします。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. AzureRMSLicensingEnabled パラメーターが false に設定されたSet-IRMConfiguration コマンドレットを実行して、Microsoft Purview Message Encryptionを無効にします。

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
