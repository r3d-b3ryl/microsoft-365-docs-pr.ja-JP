---
title: 暗号化されたメッセージにブランドを追加する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 5/12/2022
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
description: グローバル管理者Office 365組織のブランドを暗号化ポータルのコンテンツ&暗号化された電子メール メッセージに適用する方法について説明します。
ms.openlocfilehash: bf6f3b9de64185778be7eeb4da6cc8e537f0305a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66637023"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>組織のブランドを Microsoft 365 for business Message Encryption で暗号化されたメッセージに追加する

会社のブランドを適用して、組織の電子メール メッセージと暗号化ポータルの外観をカスタマイズできます。 作業を開始する前に、職場または学校アカウントにグローバル管理者アクセス許可を適用する必要があります。 これらのアクセス許可を取得したら、Exchange Online PowerShell のGet-OMEConfigurationコマンドレットとSet-OMEConfiguration コマンドレットを使用して、暗号化された電子メール メッセージのこれらの部分をカスタマイズします。

- 入門テキスト
- 免責事項テキスト
- 組織のプライバシーに関する声明の URL
- OME ポータルのテキスト
- 電子メール メッセージと OME ポータルに表示されるロゴ、またはロゴをまったく使用するかどうか
- 電子メール メッセージと OME ポータルの背景色

いつでも既定のルック アンド フィールに戻すこともできます。

より詳細な制御が必要な場合は、Microsoft Purview Advanced Message Encryption を使用して、組織から送信された暗号化された電子メール用の複数のテンプレートを作成します。 これらのテンプレートを使用して、エンド ユーザー エクスペリエンスの一部を制御します。 たとえば、受信者が Google、Yahoo、Microsoft アカウントを使用して暗号化ポータルにサインインできるかどうかを指定します。 テンプレートを使用して、次のようないくつかのユース ケースを満たします。

- 財務、営業など、個々の部門。
- さまざまな製品
- 異なる地理的地域または国
- 電子メールの取り消しを許可するかどうか
- 指定した日数が経過した後に、外部受信者に送信されたメールの有効期限を切れるかどうかを指定します。

テンプレートを作成したら、Exchange メール フロー ルールを使用して、暗号化されたメールに適用できます。 Microsoft Purview Advanced Message Encryption をお持ちであれば、これらのテンプレートを使用してブランド化したメールを取り消すことができます。

## <a name="work-with-ome-branding-templates"></a>OME ブランド テンプレートを操作する

ブランド テンプレート内の複数の機能を変更できます。 既定のテンプレートは変更できますが、削除することはできません。 高度なメッセージ暗号化を使用している場合は、カスタム テンプレートを作成、変更、削除することもできます。 Exchange Online PowerShell を使用して、一度に 1 つのブランド 化テンプレートを操作します。

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - 作成した既定のブランド 化テンプレートまたはカスタム ブランド テンプレートを変更します。
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - 新しいブランド 化テンプレートを作成します。高度なメッセージ暗号化のみ。
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - カスタム ブランド テンプレートを削除します。高度なメッセージ暗号化のみ。 既定のブランド化テンプレートは削除できません。

## <a name="modify-an-ome-branding-template"></a>OME ブランド テンプレートを変更する

Exchange Online PowerShell を使用して、一度に 1 つのブランド 化テンプレートを変更します。 高度なメッセージ暗号化を使用している場合は、カスタム テンプレートを作成、変更、削除することもできます。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、powerShell Exchange Online接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) の説明に従ってSet-OMEConfigurationコマンドレットを使用するか、次の図と表を使用してガイダンスを作成します。

![カスタマイズ可能な電子メール パーツ。](../media/ome-template-breakout.png)

|カスタマイズする暗号化エクスペリエンスの特性|これらのコマンドを使用する|
|---|---|
|背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <p> 背景色の詳細については、この記事の後半の「 [背景色」](#background-color-reference) セクションを参照してください。|
|ロゴ|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <p> **例:**  <p> `Set-OMEConfiguration -Identity "Branding Template 1" -Image ([System.IO.File]::ReadAllBytes('C:\Temp\contosologo.png'))` <p> サポートされているファイル形式: .png、.jpg、.bmp、.tiff <p> ロゴ ファイルの最適なサイズ:40 KB 未満 <p> ロゴ イメージの最適なサイズ: 170 x 70 ピクセル。 イメージがこれらのサイズを超えた場合、ポータルに表示するロゴのサイズがサービスによって変更されます。 このサービスでは、グラフィック ファイル自体は変更されません。 最適な結果を得るには、最適なサイズを使用します。|
|送信者の名前と電子メール アドレスの横にあるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|[メッセージの読み取り] ボタンに表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|[メッセージの読み取り] ボタンの下に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|プライバシーに関する声明のリンクの URL|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|このカスタム テンプレートのワンタイム パス コードで認証を有効または無効にするには|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <p> **例:** <br/>このカスタム テンプレートに対してワンタイム パスコードを有効にするには <p> `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <p> このカスタム テンプレートのワンタイム パスコードを無効にするには <p> `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|このカスタム テンプレートの Microsoft、Google、または Yahoo ID で認証を有効または無効にするには|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <p> **例:** <br/>このカスタム テンプレートのソーシャル ID を有効にするには <p> `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <p> このカスタム テンプレートのソーシャル ID を無効にするには <p> `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>OME ブランド テンプレートを作成する (Advanced Message Encryption)

Microsoft Purview Advanced Message Encryption を使用している場合は、 [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) コマンドレットを使用して、組織のカスタム ブランド テンプレートを作成できます。 テンプレートを作成したら、「OME ブランド テンプレートの変更」の説明に従って、Set-OMEConfiguration コマンドレットを使用して [テンプレートを変更します](#modify-an-ome-branding-template)。 複数のテンプレートを作成できます。

新しいカスタム ブランド テンプレートを作成するには:

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、powerShell Exchange Online接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) コマンドレットを使用して、新しいテンプレートを作成します。

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   例えば、

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>既定のブランド化テンプレートを元の値に戻します

ブランドのカスタマイズなど、既定のテンプレートからすべての変更を削除するには、次の手順を実行します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、powerShell Exchange Online接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. **Set-OMEConfiguration** の説明に従って [、Set-OMEConfiguration コマンドレットを使用します](/powershell/module/exchange/Set-OMEConfiguration)。 DisclaimerText、EmailText、PortalText の値から組織のブランド化されたカスタマイズを削除するには、値を空の文字列に設定します `""`。 ロゴなど、すべての画像値に対して、値 `"$null"`を .

   次の表では、暗号化カスタマイズ オプションの既定値について説明します。

   |この暗号化の機能を既定のテキストと画像に戻すには|これらのコマンドを使用する|
   |:-----|:-----|
   |暗号化された電子メール メッセージに付属する既定のテキスト。 暗号化メッセージの表示手順の上に表示される既定のテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <p> **例:**  <p> `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <p> **既定に戻す例:** <p> `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |ロゴ|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <p> **既定に戻す例:** <p> `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <p> **既定に戻す例:** <p> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>カスタム ブランド テンプレートを削除する (Advanced Message Encryption)

作成したブランド 化テンプレートのみを削除または削除できます。 既定のブランド 化テンプレートを削除することはできません。

カスタム ブランド テンプレートを削除するには:

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、powerShell Exchange Online接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. **Remove-OMEConfiguration** コマンドレットを次のように使用します。

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   例えば、

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   詳細については、「 [Remove-OMEConfiguration」を](/powershell/module/exchange/remove-omeconfiguration)参照してください。

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>暗号化されたメールにカスタム ブランドを適用する Exchange メール フロー ルールを作成する

> [!IMPORTANT]
> メールをスキャンおよび変更するサード パーティ製アプリケーションでは、OME ブランドが正しく適用されない可能性があります。

既定のテンプレートを変更するか、新しいブランド 化テンプレートを作成した後、Exchange メール フロー ルールを作成して、特定の条件に基づいてカスタム ブランドを適用できます。 最も重要なのは、電子メールを暗号化する必要がある点です。 このようなルールは、次のシナリオでカスタム ブランドを適用します。

- Outlook またはOutlook on the webを使用してエンド ユーザーによって電子メールが手動で暗号化された場合は、以前はOutlook Web App
- Exchange メール フロー ルールまたはMicrosoft Purview データ損失防止 ポリシーによって電子メールが自動的に暗号化された場合

カスタム ブランドMicrosoft Purview Message Encryption適用するには、メール メッセージを暗号化するメール フロー ルールを設定します。 暗号化規則が最初に処理されるように、暗号化規則の優先順位はブランド化規則よりも高くする必要があります。 既定では、ブランド化ルールの前に暗号化規則を作成すると、暗号化ルールの優先度が高くなります。 暗号化を適用する Exchange メール フロールールを作成する方法については、「[Office 365で電子メール メッセージを暗号化するメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。 メール フロー ルールの優先度の設定については、「 [メール フロー](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#set-the-priority-of-a-mail-flow-rule) ルールの管理」を参照してください。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校アカウントを使用して、[Office 365にサインインします](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. **管理** タイルを選択します。

3. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で、[**管理 センター** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">**Exchange**</a>] を選択します。

4. EAC の [**メール フロー** \> **ルール**] に移動し、[**新しい新規**![] アイコンを選択します。](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**新しいルールを作成します**。 EAC の使用の詳細については、[Exchange Onlineの Exchange 管理センターに関するページを](/exchange/exchange-admin-center)参照してください。

5. **[名前]** に、ルールの名前 (営業部門のブランド化など) を入力します。

6. **[このルールを適用する場合**] で、**送信者が組織内にあり**、使用可能な条件の一覧から必要なその他の条件を選択します。 たとえば、特定のブランド 化テンプレートを次の目的に適用できます。

   - 財務部門のメンバーから送信されたすべての暗号化された電子メール
   - "外部" や "パートナー" などの特定のキーワードで送信された暗号化された電子メール
   - 特定のドメインに送信された暗号化された電子メール

7. 暗号化を適用するメール フロー ルールを既に定義している場合は、この手順をスキップしてください。 それ以外の場合は、暗号化を適用するようにメール フロー ルールを構成するには、[**次の操作]** から [**メッセージ セキュリティの変更**] を選択し、[メッセージ **の暗号化と権限の保護Office 365適用**] を選択します。 一覧から RMS テンプレートを選択し、[ **アクションの追加**] を選択します。

   テンプレートの一覧には、既定のテンプレートとオプション、および作成するカスタム テンプレートが含まれます。 リストが空の場合は、Microsoft Purview Message Encryptionを設定していることを確認します。 手順については、「[Microsoft Purview Message Encryptionのセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。 既定のテンプレートの詳細については、「[Azure Information Protection 用のテンプレートの構成と管理](/information-protection/deploy-use/configure-policy-templates)」を参照してください。 [ **転送しない** ] オプションの詳細については、「 [電子メールの転送不可オプション」を](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)参照してください。 **暗号化専用** オプションの詳細については、「[電子メールの暗号化のみオプション」を](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)参照してください。

8. **[次の操作を行う**] で、[**メッセージ セキュリティ**\>の変更] を選択し、**カスタム ブランドを OME メッセージに適用** します。 次に、ドロップダウンからブランド テンプレートを選択します。

   別のアクションを指定する場合は [ **アクションの追加** ] を選択するか、[ **保存]** を選択してから [ **OK] を選択します**。

## <a name="background-color-reference"></a>背景色の参照

背景色に使用できる色名は制限されています。 色名の代わりに、16 進コード値 ()`#RRGGBB` を使用できます。 色名に対応する 16 進コード値を使用することも、カスタムの 16 進コード値を使用することもできます。 16 進コード値は必ず引用符で囲んでください (たとえば)。 `"#f0f8ff"`

次の表では、使用可能な背景色の名前と対応する 16 進コード値について説明します。

|色の名前|カラー コード|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|
