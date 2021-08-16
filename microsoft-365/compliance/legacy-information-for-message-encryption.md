---
title: Office 365 Message Encryption の古い情報
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 従来のファイルを組織Office 365 Message Encryption (OME) に移行する方法について説明します。
ms.openlocfilehash: 6f2b2719a66449f01b3810c8bb65020c49568248de253a7e35b84c8ae283f220
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53859838"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 Message Encryption の古い情報

組織を新しい OME 機能にまだ移動していないが、既に OME を展開している場合は、この記事の情報が組織に適用されます。 Microsoft では、組織に妥当な場合は、すぐに新しい OME 機能に移行する計画を立てをお勧めします。 手順については、「Azure Information Protection の上にOffice 365 Message Encryption新しい機能をセットアップ[する」を参照してください](set-up-new-message-encryption-capabilities.md)。 新しい機能の最初の動作の詳細については、「Office 365 Message Encryption」[を参照してください](ome.md)。 この記事の残りの部分は、新しい OME 機能のリリース前の OME 動作を参照します。
  
Office 365 Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。 Office 365 Message Encryption Outlook.com、Yahoo、Gmail、その他のメール サービスで動作します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
  
次に、いくつかの例を示します:
  
- 銀行の従業員が顧客にクレジット カードの明細書を送信する

- 保険会社の担当者が顧客にポリシーの詳細を提供する

- 住宅ローンブローカーが顧客からローン アプリケーションの財務情報を要求する

- 医療提供者が患者に医療情報を送信する

- 弁護士が顧客または他の弁護士に機密情報を送信する

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>新Office 365 Message Encryption機能なしで動作する方法

Office 365 Message Encryptionは、Microsoft Azure Rights Management (Azure RMS) に基Microsoft Azureオンライン サービスです。 Azure RMS を使用すると、管理者はメール フロー ルールを定義して、暗号化の条件を決定できます。 たとえば、ルールでは、特定の受信者にアドレス指定されたメッセージの暗号化を要求できます。
  
暗号化ルールに一致する電子Exchange Onlineメッセージを送信すると、メッセージは HTML 添付ファイルと一緒に送信されます。 受信者は HTML 添付ファイルを開き、指示に従って暗号化されたメッセージをポータルに表示Office 365 Message Encryptionします。 受信者は、Microsoft アカウントまたは Office 365 に関連付けられた仕事または学校でサインインするか、1 回きりパス コードを使用してメッセージを表示できます。 どちらのオプションも、指定された受信者のみが暗号化されたメッセージを表示できるようにするために役立ちます。 このプロセスは、新しい OME 機能とは大異なります。
  
下の図は、暗号化と復号化のプロセスにおける電子メール メッセージの流れをまとめたものです。
  
![暗号化された電子メールのパスを示す図](../media/O365-Office365MessageEncryption-Concept.png)
  
詳細については、「新しい OME 機能のリリース前Office 365 Message Encryptionレガシ サービスのサービス情報」[を参照してください](legacy-information-for-message-encryption.md#LegacyServiceInfo)。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>新しい OME 機能をOffice 365 Message Encryptionメール フロー ルールを定義する

新しい機能Office 365 Message Encryptionを有効にするには、Exchange Online管理者Exchange Online Protectionメール フロー ルールExchange定義します。 これらのルールは、電子メール メッセージを暗号化する条件と、メッセージの暗号化を削除するための条件を決定します。 ルールに対して暗号化アクションが設定されている場合、サービスは、メッセージを送信する前に、ルールの条件に一致するメッセージに対してアクションを実行します。

メール フロー ルールは柔軟であるため条件を組み合わせることができ、1 つのルールで特定のセキュリティ要件を満たすことができます。 たとえば、指定したキーワードを含み、外部の受信者に宛てられたすべてのメッセージを暗号化するルールを作成できます。 Office 365 Message Encryption、暗号化された電子メールの受信者からの返信も暗号化し、電子メール ユーザーの便宜上、それらの返信を解読するルールを作成できます。 そうすることで、組織内のユーザーは、返信を表示するために暗号化ポータルにサインインする必要が生じしません。
  
メール フロー ルールを作成する方法のExchange詳細については、「Define [Rules for Office 365 Message Encryption」 を参照してください](define-mail-flow-rules-to-encrypt-email.md)。
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能なしで電子メール メッセージを暗号化するメール フロー ルールを作成する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている仕事または学校のアカウントを使用して、管理者に[サインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365。

2. [管理] **タイルを選択** します。

3. Microsoft 365 管理センター で、**[管理センター]** \> **[Exchange]** の順に選択します。

4. EAC で、[メールフロー ルール] に移動し、[新しい新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。 EAC の使用の詳細については、「Exchange[管理センター」を参照](/exchange/exchange-admin-center)Exchange Online。

5. [ **名前]** に、ルールの名前を入力します (たとえば、メールの暗号化 DrToniRamos@hotmail.com。

6. **[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。

   1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。

   2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。

      - 既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。

      - 新しい名前を入力するには、[チェック名] ボックスに電子メール アドレス **を** 入力し、[名前の確認] \> **を選択します。[OK] を選択します**。

7. 条件を追加するには、[その他のオプション] **を選択** し、[条件の追加] を **選択し** 、一覧から選択します。

   たとえば、受信者が組織の外部にある場合にのみルールを適用するには、[条件の追加] を選択し、[受信者が組織の外部 **/** 内部である] \>  \> **[OK] を選択します**。

8. 新しい OME 機能を使用せずに暗号化を有効にするには、[次の操作] で、[メッセージ セキュリティの変更] \> **[OME** の以前のバージョンを適用する] を選択し、[保存] を **選択します**。

   IRM ライセンスが有効になっていないというエラーが表示された場合は、従来の OME を使用しません。

9. (省略可能)[アクション **の追加] を** 選択して、別のアクションを指定します。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>PowerShell Exchange Onlineを使用して、新しい OME 機能なしで電子メール メッセージを暗号化するメール フロー ルールを作成する

1. Exchange Online PowerShell に接続します。 詳細については、「[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. **New-TransportRule コマンドレットを使用してルールを作成** し _、ApplyOME_ パラメーターをに設定します `$true` 。

   この例では、ユーザーに送信される電子メール メッセージ DrToniRamos@hotmail.com 暗号化する必要があります。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   ここで

   - 新しいルールの一意の名前は"Dr Toni Ramos の暗号化ルール" です。
   - _SentTo パラメーター_ は、メッセージ受信者 (名前、電子メール アドレス、識別名など) を指定します。 この例では、受信者は電子メール アドレス "DrToniRamos@hotmail.com" で識別されます。
   - _SentToScope パラメーター_ は、メッセージ受信者の場所を指定します。 この例では、受信者のメールボックスはホットメールに含まれるので、組織の一部ではないので、値が `NotInOrganization` 使用されます。

   詳細な構文とパラメーターについては、「[New-TransportRule](/powershell/module/exchange/New-TransportRule)」を参照してください。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>新しい OME 機能なしで暗号化されたメール返信から暗号化を削除する

電子メール ユーザーが暗号化メッセージを送信した場合、これらのメッセージの受信者は、暗号化された返信で応答することができます。 メール フロー ルールを作成して、返信から暗号化を自動的に削除して、組織内の電子メール ユーザーが暗号化ポータルにサインインして表示する必要が生じないので、メール フロー ルールを作成できます。 これらのルールを定義するには、EAC または Windows PowerShellコマンドレットを使用できます。 組織内から送信されるメッセージ、または組織内から送信されたメッセージへの返信であるメッセージを復号化できます。 組織外から発信された暗号化されたメッセージを復号化することはできません。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能なしで暗号化された電子メール返信から暗号化を削除するためのルールを作成する

1. Web ブラウザーで、管理者のアクセス許可が付与されている仕事または学校のアカウントを使用して、管理者に[サインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365。

2. [管理] **タイルを選択** します。

3. Microsoft 365 管理センター で、**[管理センター]** \> **[Exchange]** の順に選択します。

4. EAC で、[メールフロー ルール] に移動し、[新しい新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。 EAC の使用の詳細については、「Exchange[管理センター」を参照](/exchange/exchange-admin-center)Exchange Online。

5. [ **名前]** に、受信メールから暗号化を削除するなどのルールの名前を入力します。

6. [**このルールを適用する]** で、受信者が組織内にあるなど、メッセージから暗号化を削除する必要がある条件 \> **を選択します**。

7. [ **次の操作] で**、[メッセージ セキュリティ **の変更] を選択** \> **します 以前のバージョンの OME を削除します**。

8. **[保存]** を選択します。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>PowerShell Exchange Onlineを使用して、新しい OME 機能なしで暗号化された電子メール返信から暗号化を削除するルールを作成する

1. Exchange Online PowerShell に接続します。 詳細については、「[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. **New-TransportRule コマンドレットを使用してルールを作成** し _、RemoveOME_ パラメーターをに設定します `$true` 。

   次の使用例は、組織内の受信者に送信されるメールの暗号化を削除します。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   ここで

   - 新しいルールの一意の名前は、「受信メールから暗号化を削除する」です。
   - _SentToScope パラメーター_ は、メッセージ受信者の場所を指定します。 この例では、値 `InOrganization` の値が使用され、次のいずれかを示します。
     - 受信者は、組織内のメールボックス、メール ユーザー、グループ、またはメールが有効なパブリック フォルダーです。
     - 受信者の電子メール アドレスは、権限を持つドメインまたは組織内の 内部の中継ドメイン として構成されている受け入れ可能なドメインに含め、認証された接続を通してメッセージが送信または受信されました。

詳細な構文とパラメーターについては、「[New-TransportRule](/powershell/module/exchange/New-TransportRule)」を参照してください。

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>新しい機能なしで暗号化されたメッセージの送信、表示、返信

このOffice 365 Message Encryption、管理者が定義したルールに基づいて電子メール メッセージが自動的に暗号化されます。 暗号化されたメッセージを含む電子メールが、添付された HTML ファイルを含む受信者の受信トレイに到着します。
  
受信者は、メッセージの指示に従って添付ファイルを開き、Microsoft アカウントまたはユーザーに関連付けられた仕事または学校を使用して認証Office 365。 受信者がどちらのアカウントも持ってない場合は、暗号化されたメッセージを表示するためにサインインできる Microsoft アカウントを作成します。 または、受信者はメッセージを表示する 1 回のパス コードを取得できます。 サインインまたはワンタイム パス コードを使用した後、受信者は復号化されたメッセージを表示し、暗号化された返信を送信できます。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>暗号化されたメッセージをユーザー設定でOffice 365 Message Encryption

管理者Exchange Online管理者Exchange Online Protection、暗号化されたメッセージをカスタマイズできます。 たとえば、会社のブランドとロゴを追加し、概要を指定し、暗号化されたメッセージと受信者が暗号化されたメッセージを表示するポータルに免責事項のテキストを追加できます。 Windows PowerShell のコマンドレットを使用して、暗号化された電子メール メッセージが受信者に表示される際の以下の側面をカスタマイズできます。

- 暗号化メッセージを含む電子メールの導入部のテキスト

- 暗号化メッセージを含む電子メールの免責事項のテキスト

- メッセージ表示ポータルに表示されるポータルのテキスト

- 電子メール メッセージおよび表示ポータルに表示されるロゴ

いつでも既定のルック アンド フィールに戻すこともできます。
  
以下の例は、電子メールの添付ファイルに表示される ContosoPharma のカスタム ロゴです。

> [!div class="mx-imgBorder"]
> ![暗号化メッセージ ページの表示例](../media/TA-OME-3attachment2.jpg)
  
**組織のブランドで暗号化メール メッセージと暗号化ポータルをカスタマイズするには**
  
1. Connect PowerShell Exchange Online使用する方法の説明に従って、リモート[PowerShell ConnectをExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. ここで説明Set-OMEConfiguration [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) を使用するか、次の表を使用してガイダンスを参照してください。

   **暗号化のカスタマイズ オプション**

   | カスタマイズする暗号化エクスペリエンスの特性 | 使用する Windows PowerShell コマンド |
   |:-----|:-----|
   |暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
   |暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
   |暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
   |ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **例:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> 最適なロゴ画像のサイズ:170x70 ピクセル  <br/> |

**暗号化電子メール メッセージと暗号化ポータルからブランドのカスタマイズを削除するには**
  
1. Connect PowerShell Exchange Online使用する方法の説明に従って、リモート[PowerShell ConnectをExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. ここで説明Set-OMEConfiguration [Set-OMEConfiguration コマンドレットを使用します](/powershell/module/exchange/set-omeconfiguration)。 DisclaimerText、EmailText、PortalText の各値から組織のブランド化されたカスタマイズを削除するには、値を空の文字列に設定します  `""` 。 Logo などのすべての画像値に対して、値をに設定します  `"$null"` 。

   **暗号化のカスタマイズ オプション**

   | この暗号化の機能を既定のテキストと画像に戻すには | 使用する Windows PowerShell コマンド |
   |:-----|:-----|
   |暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
   |暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
   |暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **既定に戻す例:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
   |ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **既定に戻す例:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>新しい OME 機能Office 365 Message Encryption以前のレガシ サービスのサービス情報
<a name="LegacyServiceInfo"> </a>

次の表に、新しい OME 機能のリリース前Office 365 Message Encryptionサービスの技術的な詳細を示します。
  
| サービスの詳細情報 | Description |
|:-----|:-----|
|クライアント デバイスの要件  <br/> |暗号化されたメッセージは、Form Post をサポートする最新のブラウザーで HTML 添付ファイルを開くことができれば、任意のクライアント デバイスで表示できます。  <br/> |
|暗号化アルゴリズムと連邦情報処理規格 (FIPS) への準拠  <br/> |Office 365 Message Encryption は、Windows Azure Information Rights Management (IRM) と同じ暗号化キーを使用し、暗号化モード 2 をサポートします (RSA システム用の 2K キーと SHA-1 システム用の 256 ビット キー)。 基になる IRM 暗号化モードの詳細については、「RMS 暗号化モードAD [を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))。  <br/> |
|サポートされているメッセージの種類  <br/> |Office 365 Message Encryption は、**IPM.Note** のメッセージ クラス ID があるアイテムでのみサポートされます。 詳細については、「アイテムの種類 [とメッセージ クラス」を参照してください](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes)。  <br/> |
|メッセージ サイズの制限  <br/> |Office 365 Message Encryption は、25 メガバイトまでのメッセージを暗号化できます。 メッセージ サイズの制限の詳細については、「Exchange Online[を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。  <br/> |
|Exchange Online保持ポリシーの設定  <br/> |Exchange Onlineメッセージは保存されません。  <br/> |
|Office 365 Message Encryption の言語サポート  <br/> | Office 365メッセージの暗号化は、Microsoft 365言語をサポートします。  <br/>  受信メール メッセージと添付 HTML ファイルは、送信者の言語設定に基づいてローカライズされます。  <br/>  表示するためのポータルは、受信者のブラウザーの設定に基づいてローカライズされます。  <br/>  暗号化されたメッセージの本文 (コンテンツ) は、ローカライズされません。  <br/> |
|OME ポータルと OME Viewer アプリの個人情報  <br/> |[Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) には、お客様の個人情報を使用して Microsoft が行うことと行わないことについて詳しく記されています。  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>従来の OME に関するよく寄せられる質問
<a name="LegacyServiceInfo"> </a>

ユーザーに関する質問Office 365 Message Encryption? いくつかの回答を次に示します。 必要な情報が見当たらない場合は[、Microsoft Tech](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)CommunityフォーラムでOffice 365。
  
 **Q.ユーザーは、組織外の受信者に暗号化された電子メール メッセージを送信します。外部受信者が、暗号化された電子メール メッセージを読み取り、返信するために行う必要Office 365 Message Encryption。**
  
暗号化されたメッセージを受信する組織Microsoft 365受信者は、次の 2 つの方法のいずれかを使用して表示できます。
  
- Microsoft アカウント、またはユーザーに関連付けられた仕事または学校のアカウントでサインインOffice 365。

- 1 回のパス コードを使用します。

 **Q.暗号化Microsoft 365は、クラウドまたは Microsoft サーバーに保存されますか?**
  
いいえ、暗号化されたメッセージは受信者の電子メール システムに保持され、受信者がメッセージを開くと、Microsoft サーバーで表示するために一時的に投稿されます。 メッセージはそこに保存されません。
  
 **Q. 暗号化された電子メール メッセージを独自のブランドでカスタマイズすることはできますか。**
  
はい。 Windows PowerShell コマンドレットを使用して、暗号化された電子メール メッセージの上に表示する既定のテキスト、免責事項テキスト、および電子メール メッセージや暗号化ポータルに使用するロゴをカスタマイズできます。 この機能は OMEv2 で利用できます。 詳細については、「[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)」を参照してください。
  
 **Q. このサービスは組織内のすべてのユーザーに対して 1 つのライセンスが必要ですか。**
  
暗号化された電子メールを送信する組織内のすべてのユーザーに対して 1 つのライセンスが必要です。
  
 **Q. 外部の受信者はサブスクリプションが必要ですか。**
  
いいえ。外部の受信者は、暗号化されたメッセージを読んで返信するためにサブスクリプションを必要としません。
  
 **Q.Rights Management Services (RMS Office 365 Message Encryptionの違いは何ですか?**
  
RMS は、組み込みのテンプレート (転送しない、会社機密など) を提供することで、組織の内部メールに対する Information Rights Protection 機能を提供します。 Office 365 Message Encryption外部受信者および内部受信者に送信されるメッセージの電子メール メッセージ暗号化をサポートしています。
  
 **Q.S/MIME Office 365 Message Encryptionの違いは?**
  
S/MIME は、基本的に、クライアント側の暗号化テクノロジであり、複雑な証明書管理と発行インフラストラクチャが必要です。 Office 365 Message Encryptionメール フロー ルール (トランスポート ルールとも呼ばれる) を使用し、証明書の発行には依存しない。
  
 **Q. モバイル デバイスで暗号化されたメッセージを読むことはできますか。**
  
はい、Android と iOS でメッセージを表示するには、Google Play ストアと Apple App ストアから OME ビューアー アプリをダウンロードします。 OME Viewer アプリの HTML 添付ファイルを開いてから、指示に従って暗号化されたメッセージを開きます。 その他のモバイル デバイスでは、メール クライアントが投稿フォームをサポートしている限り HTML 添付ファイルを開くことができます。
  
 **Q. 返信や転送されたメッセージは暗号化されますか。**
  
はい。返信はスレッド期間の間、暗号化されます。
  
 **Q.ローカライズOffice 365 Message Encryption提供しますか?**
  
受信電子メールと HTML コンテンツは、送信者の電子メール設定に基づいてローカライズされます。表示ポータルは、受信者のブラウザー設定に基づいてローカライズされます。ただし、暗号化されたメッセージの本文 (コンテンツ) はローカライズされません。
  
 **Q.使用する暗号化方法は何Office 365 Message Encryption。**
  
Office 365 Message Encryption暗号化インフラストラクチャとして Rights Management Services (RMS) を使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。
  
- RMS を使用Microsoft Azureキーを取得する場合は、暗号化モード 2 が使用されます。 暗号化モード 2 は、AD RMS 暗号実装を更新して強化した方式です。 この方式は署名と暗号化に RSA 2048 をサポートし、署名に関しては SHA-256 もサポートします。

- Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。使用される方法は、社内 AD RMS 展開によって異なります。暗号化モード 1 は、元来の AD RMS 暗号実装です。この方式は署名と暗号化に RSA 1024 をサポートし、署名に関しては SHA-1 もサポートします。このモードは、引き続き RMS の現在のすべてのバージョンでサポートされています。

詳細については、「RMS 暗号化 [モードADを参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))。
  
**Q.暗号化されたメッセージの中には、メールから** 送信されたと言う Office365@messaging.microsoft.com。
  
暗号化された返信が暗号ポータルから、または OME ビューアー アプリを介して送信されるとき、送信元電子メール アドレスは Office365@messaging.microsoft.com に設定されます。暗号化メッセージは Microsoft エンドポイントを介して送信されるためです。これにより、暗号化されたメッセージがスパムとしてマークされるのを回避できます。このラベルがあるため、暗号化ポータル内の電子メールとアドレスの表示名が変更されることはありません。また、このラベルが適用されるのは、ポータルを介して送信されるメッセージだけで、他の電子メール クライアントを介して送信されるメッセージには適用されません。
  
 **Q.私は、Exchange暗号化 (EHE) サブスクライバーです。アップグレードの詳細については、どこで確認Office 365 Message Encryption。**
  
EHE のすべてのお客様は、Office 365 Message Encryption にアップグレードされました。 詳細については、「ホストされた暗号化[アップグレード センター Exchangeを参照してください](../security/office-365-security/exchange-online-protection-overview.md)。
  
 **Q.組織のファイアウォール内の URL、IP アドレス、またはポートを開き、組織のファイアウォールをサポートする必要Office 365 Message Encryption?**
  
はい。 Office 365 Message Encryption によって暗号化されたメッセージの認証を有効にするには、ご自分の組織の許可リストに Exchange Online の URL を追加する必要があります。 URL の一覧Exchange Online URL と[IP Microsoft 365を参照してください](../enterprise/urls-and-ip-address-ranges.md)。
  
 **Q.暗号化されたメッセージを送信できるMicrosoft 365の数。**
  
受信者の制限は、メッセージごとに 500 人の受信者、または配布リストの展開後に組み合わせると、メッセージの **[宛先** ] フィールドの 11,980 文字です。どちらが最初に表示されます。
  
 **Q. 特定の受信者に送信されたメッセージを取り消すことは可能ですか。**
  
いいえ。 送信後に特定のユーザーにメッセージを取り消す事はできない。
  
 **Q. 受信されて既読になった暗号化メッセージのレポートを表示することはできますか。**
  
暗号化されたメッセージが表示されたかどうかを示すレポートは表示されませんが、たとえば、特定のメール フロー ルール (トランスポート ルールとも呼ばれる) に一致するメッセージの数を判断するために利用できる Microsoft 365 レポートがあります。
  
 **Q. OME ポータルと OME Viewer アプリで提供した情報を Microsoft はどのように使用しますか。**
  
この[Office 365メッセージング暗号化ポータル](https://privacy.microsoft.com/privacystatement)のプライバシーに関する声明では、Microsoft が個人情報に対して何を行い、何を行わないかについての詳細な情報を提供します。

**Q.要求した後に 1 回のパス コードを受け取らない場合は、どうしますか。**

まず、メール クライアントの迷惑メール フォルダーまたは迷惑メール フォルダーを確認します。 組織の DKIM と DMARC の設定により、これらのメールがスパムとしてフィルター処理される可能性があります。

次に、セキュリティ コンプライアンス センターで&を確認します。 多くの場合、1 回きりパス コードを含むメッセージ(特に組織が最初に受け取ったメッセージ)は検疫に入ります。