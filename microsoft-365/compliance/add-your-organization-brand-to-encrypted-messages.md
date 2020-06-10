---
title: 暗号化されたメッセージに組織ブランドを追加する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 組織の暗号化された電子メールメッセージおよび暗号化ポータルの内容に、組織のブランド化を適用します。
ms.openlocfilehash: 86636b319151a96e9ec827f85cc943282c30f63c
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679111"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>暗号化されたメッセージに組織のブランドを追加する

Exchange Online または Exchange Online Protection 管理者として、会社のブランドを適用して、ビジネスメッセージの暗号化の電子メールメッセージおよび暗号化ポータルの内容を組織の Microsoft 365 用にカスタマイズすることができます。 取得した、暗号化された電子メールメッセージの受信者については、次のように、Windows PowerShell コマンドレットを使用して、以下の点をカスタマイズできます。
  
- 暗号化メッセージを含む電子メールの導入部のテキスト

- 暗号化メッセージを含む電子メールの免責事項のテキスト

- 組織のプライバシーに関する声明の URL

- OME ポータルに表示されるテキスト

- 電子メールメッセージと OME ポータルに表示されるロゴ、またはロゴを使用するかどうか

- 電子メールメッセージと OME ポータルの背景色

いつでも既定のルック アンド フィールに戻すこともできます。

より詳細な制御を希望する場合は、Office 365 Advanced Message Encryption を使用して、組織から送信される暗号化電子メール用に複数のテンプレートを作成することができます。 これらのテンプレートを使用すると、電子メールメッセージの外観だけでなく、エンドユーザーの操作性の部分を制御することもできます。 たとえば、このテンプレートが適用されているメールの受信者と、Google、Yahoo、および Microsoft のアカウントを使用するユーザーが、これらのアカウントを使用して Office 365 メッセージ暗号化ポータルにサインインできるようにするかどうかを指定できます。 テンプレートを使用して、次のようないくつかのユースケースを満たすことができます。

- 各部門のテンプレート (Finance、Sales など)。

- さまざまな製品のテンプレート

- さまざまな地域または国のテンプレート

- 電子メールの失効を許可するかどうか

- 指定した日数が経過した後に、外部の受信者に送信される電子メールの有効期限を指定するかどうか。

テンプレートを作成したら、Exchange メールフロールールを使用して暗号化された電子メールにそれらを適用することができます。 Office 365 の高度なメッセージ暗号化を使用している場合は、これらのテンプレートを使用して、ブランド化されたすべての電子メールを取り消すことができます。

## <a name="work-with-ome-branding-templates"></a>OME ブランド化テンプレートを操作する

ブランド設定テンプレート内のいくつかの機能を変更することができます。 既定のテンプレートを変更することはできますが、削除することはできません。 高度なメッセージ暗号化を使用している場合は、カスタムテンプレートを作成、変更、および削除することもできます。 Windows PowerShell を使用して、一度に1つのブランド化テンプレートを操作します。 これらのコマンドレットを使用するには、組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントが必要です。

- [ [-Omeconfiguration 設定](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration)-既定のブランド化テンプレートまたは作成したカスタムブランド設定テンプレートを変更する。
- [新機能-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) /新しいブランド化テンプレートを作成し、高度なメッセージ暗号化のみを行います。
- [削除-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) /カスタムブランド設定テンプレートを削除し、高度なメッセージ暗号化のみを行います。 既定のブランド設定テンプレートを削除することはできません。
  
## <a name="modify-an-ome-branding-template"></a>OME ブランド化テンプレートを変更する

Windows PowerShell を使用して、一度に1つのブランド化テンプレートを変更します。 高度なメッセージ暗号化を使用している場合は、カスタムテンプレートを作成、変更、および削除することもできます。

1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. テンプレートを変更するには、次の図と表を参考にして、set [-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)コマンドレットを使用します。

![カスタマイズ可能な電子メールパーツ](../media/ome-template-breakout.png)

|**カスタマイズする暗号化エクスペリエンスの特性**|**使用するコマンド**|
|:-----|:-----|
|背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> 背景色の詳細については、このトピックで後述する「[背景色](#background-color-reference)」を参照してください。|
|ロゴ|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> ロゴイメージの最適なサイズ: 170x70 ピクセル。 画像がこれらのサイズを超える場合、ポータルに表示されるように、サービスによってロゴのサイズが変更されます。 サービスによってグラフィックファイル自体が変更されることはありません。 最適な結果を得るには、最適なサイズを使用します。|
|送信者の名前と電子メールアドレスの横のテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|[メッセージの読み取り] ボタンに表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|[メッセージの読み取り] ボタンの下に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|プライバシーに関する声明のリンクの URL|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|このカスタムテンプレートのワンタイムパスコードで認証を有効または無効にするには|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **例:** <br/>このカスタムテンプレートで1回限りのパスコードを有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> このカスタムテンプレートで1回限りのパスコードを無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|このカスタムテンプレートの Microsoft、Google、または Yahoo の id による認証を有効または無効にするには|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **例:** <br/>このカスタムテンプレートのソーシャル Id を有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> このカスタムテンプレートのソーシャル Id を無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>OME ブランド化テンプレートを作成する (高度なメッセージ暗号化)

Office 365 の高度なメッセージ暗号化を使用している場合は、[新しい/omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration)コマンドレットを使用して、組織のカスタムブランド化テンプレートを作成できます。 テンプレートを作成したら、「 [modify a OME ブランド化テンプレート](#modify-an-ome-branding-template)」に説明されているように、を設定して、テンプレートを変更します。 複数のテンプレートを作成できます。

新しいカスタムブランド化テンプレートを作成するには、次のようにします。

1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. 新しいテンプレートを作成するには、[新しい-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration)コマンドレットを使用します。

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   以下に例を示します。

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>既定のブランド設定テンプレートを元の値に戻す

ブランド化のカスタマイズなど、すべての変更を既定のテンプレートから削除するには、次の手順を実行します。
  
1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. **Set-omeconfiguration コマンドレット**を使用します[。](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) 組織のブランド化されたカスタマイズを DisclaimerText、EmailText、および PortalText の値から削除するには、値を空の文字列に設定し `""` ます。 ロゴなどのすべてのイメージ値について、値をに設定 `"$null"` します。

   次の表では、暗号化のカスタマイズオプションの既定値について説明します。

   **この暗号化の機能を既定のテキストと画像に戻すには**|**使用するコマンド**|
   |:-----|:-----|
   |暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **既定値に戻す例:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |ロゴ|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **既定値に戻す例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **既定値に戻す例:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>カスタムブランド設定テンプレートを削除する (高度なメッセージ暗号化)

作成したブランド設定テンプレートのみを削除または削除できます。 既定のブランド設定テンプレートを削除することはできません。

カスタムブランド化テンプレートを削除するには、次のようにします。
  
1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. 次のように、**削除**コマンドレットを使用します。

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   以下に例を示します。

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   詳細については、「[削除-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)を参照してください。

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>暗号化された電子メールにカスタムブランド化を適用する Exchange メールフロールールを作成する

既定のテンプレートを変更したか、または新しいブランド化テンプレートを作成したら、Exchange メールフロールールを作成して、特定の条件に基づいてカスタムブランド化を適用できます。 このようなルールは、次のシナリオでカスタムブランド化を適用します。

- Outlook または web 上の outlook (旧称 Outlook Web App) クライアントからエンドユーザーによって電子メールが手動で暗号化されている場合

- 電子メールが Exchange メールフロールールまたはデータ損失防止ポリシーによって自動的に暗号化された場合

暗号化を適用する Exchange メールフロールールを作成する方法については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [**管理**] タイルを選択します。

3. Microsoft 365 管理センターで、[**管理センター** ] [Exchange] を選択し \> **Exchange**ます。

4. EAC で、[**メールフロー** ] [ルール] に移動し、 \> **Rules** [新しい**New** ![ 新規作成] アイコンを選択して ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [**名前**] に、[営業部門のブランド化] など、ルールの名前を入力します。

6. [**このルールを適用**する条件] で、使用可能な条件の一覧から、**送信者が組織内に配置さ**れている条件とその他の条件を選択します。 たとえば、特定のブランド化テンプレートを次のように適用することができます。

   - 財務部門のメンバーから送信されるすべての暗号化された電子メール
   - 「外部」や「パートナー」などの特定のキーワードで暗号化された電子メール
   - 特定のドメインに送信される暗号化された電子メール

7. [**実行する処理] 次**に、[**メッセージセキュリティを変更**します] を選択して、  >  **OME メッセージにカスタムブランドを適用**します。 次に、ドロップダウンから、作成または変更したブランド化テンプレートを選択します。

8. オプションカスタムブランド化に加えて、メールフロールールが暗号化を適用するようにするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。 一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。
  
   テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。 リストが空の場合は、「office の[365 新しいメッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」の説明に従って、Office 365 メッセージの暗号化を新しい機能で設定していることを確認してください。 既定のテンプレートの詳細については、「 [Azure Information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。 [**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。 [**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。

   別のアクションを指定する場合は、[**アクションの追加**] を選択します。

## <a name="background-color-reference"></a>背景色の参照

背景色に使用できる色の名前は制限されています。 色の名前ではなく、16進コード値 (#RRGGBB) を使用できます。 色の名前に対応する16進コード値を使用することも、カスタムの16進コード値を使用することもできます。 16進コード値は二重引用符で囲んでください (例: `"#f0f8ff"` )。

次の表では、使用可能な背景色の名前と、それに対応する16進コードの値について説明します。

|||
|---|---|
|**色の名前**|**色コード**|
|aliceblue|#f0f8ff|
|antiquewhite|#faebd7|
|明るい|#00ffff|
|アクアマリン|#7fffd4|
|azure|#f0ffff|
|ベージュ|#f5f5dc|
|bisque|#ffe4c4|
|black|#000000|
|blanchedalmond|#ffebcd|
|青|#0000ff|
|blueviolet|#8a2be2|
|灰色|#a52a2a|
|burlywood|#deb887|
|cadetblue|#5f9ea0|
|chartreuse|#7fff00|
|チョコ|#d2691e|
|coral|#ff7f50|
|cornflowerblue|#6495ed|
|cornsilk|#fff8dc|
|クリムゾン|#dc143c|
|シアン|#00ffff|
|darkblue|#00008b|
|darkcyan|#008b8b|
|darkgoldenrod|#b8860b|
|darkgray|#a9a9a9|
|darkgreen|#006400|
|darkkhaki|#bdb76b|
|darkmagenta|#8b008b|
|darkolivegreen|#556b2f|
|darkorange|#ff8c00|
|darkorchid|#9932cc|
|darkred|#8b0000|
|darksalmon|#e9967a|
|darkseagreen|#8fbc8f|
|darkslateblue|#483d8b|
|darkslategray|#2f4f4f|
|darkturquoise|#00ced1|
|darkviolet|#9400d3|
|deeppink|#ff1493|
|deepskyblue|#00bfff|
|dimgray|#696969|
|dodgerblue|#1e90ff|
|焼討ブリック|#b22222|
|floralwhite|#fffaf0|
|forestgreen|#228b22|
|紫色|#ff00ff|
|gainsboro|#dcdcdc|
|ghostwhite|#f8f8ff|
|(金)|#ffd700|
|ゴールデンロッド|#daa520|
|灰色|#808080|
|green|#008000|
|greenyellow|#adff2f|
|honeydew|#f0fff0|
|ホットピンク|#ff69b4|
|indianred|#cd5c5c|
|indigo|#4b0082|
|ivory|#fffff0|
|カーキ|#f0e68c|
|ラベンダー|#e6e6fa|
|lavenderblush|#fff0f5|
|lawngreen|#7cfc00|
|lemonchiffon|#fffacd|
|lightblue|#add8e6|
|lightcoral|#f08080|
|ライト水色|#e0ffff|
|lightgoldenrodyellow|#fafad2|
|ライトグレー|#d3d3d3|
|ライトグレー|#d3d3d3|
|lightgreen|#90ee90|
|ライトピンク|#ffb6c1|
|ライトサーモンピンク|#ffa07a|
|lightseagreen|#20b2aa|
|lightskyblue|#87cefa|
|ライト slategray|#778899|
|ライト・ステップブルー|#b0c4de|
|ライト黄|#ffffe0|
|黄緑|#00ff00|
|limegreen|#32cd32|
|linen|#faf0e6|
|赤|#ff00ff|
|紫|#800000|
|mediumaquamarine|#66cdaa|
|mediumblue|#0000cd|
|mediumorchid|#ba55d3|
|mediumpurple|#9370db|
|mediumseagreen|#3cb371|
|mediumslateblue|#7b68ee|
|mediumspringgreen|#00fa9a|
|mediumturquoise|#48d1cc|
|mediumvioletred|#c71585|
|midnightblue|#191970|
|mintcream|#f5fffa|
|mistyrose|#ffe4e1|
|cascasin|#ffe4b5|
|ナビゲーション a・ホワイト|#ffdead|
|海軍|#000080|
|oldlace|#fdf5e6|
|オリーブ|#808000|
|olivedrab|#6b8e23|
|orange|#ffa500|
|orang|#ff4500|
|オーキッド|#da70d6|
|中|#eee8aa|
|男性|#98fb98|
|(男性) 水色|#afeeee|
|中|#db7093|
|papayawhip|#ffefd5|
|peachpuff|#ffdab9|
|ペルー|#cd853f|
|pink|#ffc0cb|
|プラム|#dda0dd|
|powderblue|#b0e0e6|
|purple|#800080|
|red|#ff0000|
|rosybrown|#bc8f8f|
|royalblue|#4169e1|
|saddlebrown|#8b4513|
|サーモンピンク|#fa8072|
|sandybrown|#f4a460|
|seagreen|
|seashell|#fff5ee|
|sienna|#a0522d|
|シルバー|#c0c0c0|
|skyblue|#87ceeb|
|slateblue|#6a5acd|
|slategray|#708090|
|溜り|#fffafa|
|springgreen|#00ff7f|
|steelblue|#4682b4|
|tan|#d2b48c|
|teal|#008080|
|thistle|#d8bfd8|
|tomato|#ff6347|
|水色|#40e0d0|
|バイオレット|#ee82ee|
|小麦|#f5deb3|
|white|#ffffff|
|ホワイトリスト|#f5f5f5|
|yellow|#ffff00|
|yellowgreen|#9acd32|
