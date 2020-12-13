---
title: 暗号化されたメッセージに組織のブランドを追加する
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
- seo-marvel-jun2020
description: 365 Office管理者が暗号化ポータルのコンテンツを使用して暗号化された電子メール メッセージに組織の&を適用する方法について学習します。
ms.openlocfilehash: 77fd5e08afa1a4d8ae5f6386fa65b88b6ea2be4d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663234"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>組織のブランドを Microsoft 365 for Business Message Encryption で暗号化されたメッセージに追加する

会社のブランド化を適用して、組織の電子メール メッセージと暗号化ポータルの外観をカスタマイズできます。 作業を開始する前に、グローバル管理者のアクセス許可を仕事または学校のアカウントに適用する必要があります。 これらのアクセス許可を取得したら、Get-OMEConfiguration コマンドレットと Set-OMEConfiguration Windows PowerShell コマンドレットを使用して、暗号化された電子メール メッセージの次の部分をカスタマイズします。
  
- 導入テキスト

- 免責事項テキスト

- 組織のプライバシーに関する声明の URL

- OME ポータルのテキスト

- 電子メール メッセージと OME ポータルに表示されるロゴ、またはロゴを使用するかどうか

- 電子メール メッセージと OME ポータルの背景色

いつでも既定のルック アンド フィールに戻すこともできます。

より詳細な制御が必要な場合は、Office 365 Advanced Message Encryption を使用して、組織から発信された暗号化された電子メール用の複数のテンプレートを作成します。 これらのテンプレートを使用して、エンド ユーザー エクスペリエンスの一部を制御します。 たとえば、受信者が Google、Yahoo、Microsoft アカウントを使用して暗号化ポータルにサインインできるかどうかを指定します。 テンプレートを使用して、次のようないくつかの使用例を満たします。

- 財務、営業など、個々の部署。

- 異なる製品

- 地理的に異なる地域または国

- メールの取り消しを許可するかどうかを指定します

- 外部の受信者に送信された電子メールを、指定した日数後に期限切れにするかどうかを指定します。

テンプレートを作成したら、Exchange メール フロー ルールを使用して、暗号化された電子メールにテンプレートを適用できます。 365 Advanced Message Encryption Office使用している場合は、これらのテンプレートを使用して、ブランド化したメールを取り消す可能性があります。

## <a name="work-with-ome-branding-templates"></a>OME ブランド 化テンプレートを使用する

ブランド化テンプレート内のいくつかの機能を変更できます。 既定のテンプレートは変更できますが、削除はできます。 Advanced Message Encryption を使用している場合は、カスタム テンプレートを作成、変更、削除することもできます。 一Windows PowerShellを使用して 1 つのブランドテンプレートを使用します。

- [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - 作成した既定のブランドテンプレートまたはカスタム ブランド テンプレートを変更します。
- [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - 新しいブランドテンプレートを作成します。Advanced Message Encryption のみ。
- [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - カスタム ブランド テンプレートを削除します。Advanced Message Encryption のみ。 既定のブランド化テンプレートは削除できない。
  
## <a name="modify-an-ome-branding-template"></a>OME ブランドテンプレートを変更する

一Windows PowerShell 1 つのブランド テンプレートを変更するには、次のコマンドを使用します。 Advanced Message Encryption を使用している場合は、カスタム テンプレートを作成、変更、削除することもできます。

1. 組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) Set-OMEConfiguration説明に従って次のコマンドレットを使用するか、ガイダンスとして次の図と表を使用します。

![カスタマイズ可能な電子メール パーツ](../media/ome-template-breakout.png)

|**カスタマイズする暗号化エクスペリエンスの特性**|**使用するコマンド**|
|:-----|:-----|
|背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> 背景の色について詳しくは、この記事で後の「 [背景の](#background-color-reference) 色」セクションをご覧ください。|
|ロゴ|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> ロゴ画像の最適なサイズ: 170x70 ピクセル。 画像がこれらのサイズを超える場合、サービスはポータルに表示するロゴのサイズを変更します。 サービスは、グラフィック ファイル自体を変更しません。 最適な結果を得る場合は、最適なサイズを使用してください。|
|送信者の名前とメール アドレスの横のテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|[メッセージの読み取り] ボタンに表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|[メッセージの読み取り] ボタンの下に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|[プライバシーに関する声明] リンクの URL|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|このカスタム テンプレートのワンタイム パス コードを使用して認証を有効または無効にするには|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **例:** <br/>このカスタム テンプレートのワンタイム パスコードを有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> このカスタム テンプレートのワンタイム パスコードを無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|このカスタム テンプレートの Microsoft、Google、または Yahoo ID を使用した認証を有効または無効にするには|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **例:** <br/>このカスタム テンプレートのソーシャル ID を有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> このカスタム テンプレートのソーシャル ID を無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>OME ブランド化テンプレートを作成する (Advanced Message Encryption)

365 Advanced Message Encryption Officeしている場合は [、New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) コマンドレットを使用して、組織のカスタム ブランド テンプレートを作成できます。 テンプレートを作成したら、「OME ブランド化テンプレートの変更」の説明に従って Set-OMEConfiguration コマンドレットを使用してテンプレート [を変更します](#modify-an-ome-branding-template)。 複数のテンプレートを作成できます。

新しいカスタム ブランドテンプレートを作成するには:

1. 組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. 新しい [テンプレートを作成するには、New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) コマンドレットを使用します。

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   例えば、

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>既定のブランドテンプレートを元の値に戻す

ブランドのカスタマイズなど、既定のテンプレートからすべての変更を削除するには、次の手順を実行します。
  
1. 組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. **Set-OMEConfiguration コマンドレット** の説明に従 [って、Set-OMEConfiguration コマンドレットを使用します](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)。 DisclaimerText、EmailText、および PortalText の値から組織のブランド化されたカスタマイズを削除するには、値を空の文字列に設定します `""` 。 ロゴなどのすべての画像の値に対して、値を次のように設定します  `"$null"` 。

   次の表では、暗号化カスタマイズ オプションの既定値について説明します。

   **この暗号化の機能を既定のテキストと画像に戻すには**|**使用するコマンド**|
   |:-----|:-----|
   |暗号化された電子メール メッセージに付属する既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **既定値に戻す例:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |ロゴ|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **既定値に戻す例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **既定値に戻す例:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>カスタム ブランド テンプレートを削除する (Advanced Message Encryption)

削除または削除できるのは、作成したブランド化テンプレートのみです。 既定のブランド化テンプレートは削除できない。

カスタム ブランド テンプレートを削除するには:
  
1. 組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. **Remove-OMEConfiguration コマンドレットは次** のように使用します。

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   例えば、

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   詳細については [、「Remove-OMEConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)。

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>暗号化されたメールにカスタム ブランドを適用する Exchange メール フロー ルールを作成する

既定のテンプレートを変更するか、新しいブランド化テンプレートを作成したら、特定の条件に基づいてカスタム ブランド化を適用する Exchange メール フロー ルールを作成できます。 このようなルールは、次のシナリオでカスタム ブランド化を適用します。

- 電子メールが Outlook または Outlook on the web を使用してエンド ユーザーによって手動で暗号化された場合、以前はOutlook Web App

- Exchange メール フロー ルールまたはデータ損失防止ポリシーによって電子メールが自動的に暗号化された場合

暗号化を適用する Exchange メール フロー ルールを作成する方法については [、「365](define-mail-flow-rules-to-encrypt-email.md)で電子メール メッセージを暗号化するメール フロー ルールを定義する」をOfficeしてください。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている学校または学校のアカウントを使用して、Office [365 にサインインします](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. [管理者] **タイルを選択** します。

3. Microsoft 365 管理センターで、Exchange 管理センター **を選択** \> **します**。

4. EAC で、[メール フロー ルール] に **移動** し、[新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。 EAC の使用の詳細については、Exchange Online の [Exchange 管理センターを参照してください](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. [ **名前]** に、営業部門のブランド化などのルールの名前を入力します。

6. [**次の場合に** このルールを適用する] で、送信者が組織内に存在する条件と、使用可能な条件の一覧から必要なその他の条件を選択します。 たとえば、次の場合に特定のブランド化テンプレートを適用できます。

   - 財務部門のメンバーから送信された暗号化された電子メールすべて
   - "外部" や "パートナー" などの特定のキーワードで送信された暗号化された電子メール
   - 特定のドメインに送信される暗号化された電子メール

7. From **Do the following,** select **Modify the message security** Apply \> **custom branding to OME messages**. 次に、ドロップダウンからブランド テンプレートを選択します。

8. (省略可能)暗号化とカスタム ブランド化を適用するメール フロー ルールを構成できます。 From **Do the following,** select **Modify the message security,** and then choose **Apply Office 365 Message Encryption and rights protection**. 一覧から RMS テンプレートを選択し、[保存]**を選択して****、[OK]** を選択します。
  
   テンプレートの一覧には、既定のテンプレートとオプション、および作成するカスタム テンプレートが含まれます。 リストが空の場合は、新しい機能を使用して Office 365 Message Encryption を設定してください。 手順については [、「Set up new Office 365 Message Encryption capabilities 」を参照してください](set-up-new-message-encryption-capabilities.md)。 既定のテンプレートの詳細については、「Azure Information Protection 用のテンプレートの構成と [管理」を参照してください](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 転送しないオプション **の詳細については、メール** の転送 [を行う前にオプションを参照してください](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 暗号化専用オプションの詳細 **については、「** メールの暗号化 [のみ」オプションを参照してください](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   別 **のアクションを** 指定する場合は、[アクションの追加] を選択します。

## <a name="background-color-reference"></a>背景色の参照

背景色に使用できる色の名前は制限されています。 色の名前の代わりに、16 進コード値 (#RRGGBB) を使用できます。 色の名前に対応する 16 進コード値を使用するか、ユーザー設定の 16 進コード値を使用できます。 必ず 16 進数のコード値を二重引用符 (たとえば) で囲んでください `"#f0f8ff"` 。

使用可能な背景色の名前と対応する 16 進コードの値を次の表に示します。

|||
|---|---|
|**色の名前**|**カラー コード**|
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
