---
title: Microsoft 365 の展開で多要素認証を計画する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 での多要素認証について、および設定するために従う必要のある手順について説明します。
ms.openlocfilehash: c68fdb5c1a144c6bfe1161d95e1d6808461e2456
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627706"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>Microsoft 365 の展開で多要素認証を計画する

多要素認証 (MFA) では、複数の確認方法を使用することが求められ、ユーザーのサインインとトランザクションに加えてもう 1 つのセキュリティ レイヤーを追加する認証方法です。 これは、次のようなユーザーアカウントのパスワード以外の情報を使用して、追加の確認手順が必要になります。
  
- ランダムに生成されるパス コード
    
- 電話
    
- スマート カード (仮想または物理) 
    
- 生体認証デバイス 
    
## <a name="multi-factor-authentication-in-microsoft-365"></a>Microsoft 365 での多要素認証

Microsoft 365 では、複数要素認証を使用して、セキュリティを強化し、Microsoft 365 管理センターから管理することができます。 Microsoft 365 では、次のような Azure 多要素認証機能のサブセットをサブスクリプションの一部として提供しています。 
  
- エンドユーザーに対して MFA を有効にし、適用する機能
    
- 第 2 認証要素としてモバイル アプリ (オンラインおよびワンタイム パスワード [OTP]) を使用する
    
- 第 2 認証要素として電話を使用する
    
- 第 2 認証要素としてショート メッセージ サービス (SMS) のメッセージを使用する
    
- 非ブラウザークライアントのアプリケーションパスワード (たとえば、Microsoft Lync 2013 通信ソフトウェア)
    
- 電話認証時の既定の案内応答
    
追加された機能の一覧については、「[バージョンごとの機能の比較](https://go.microsoft.com/fwlink/?LinkId=506927)」を参照してください。 Azure Multi-Factor Authentication サービスを購入すると、すべての機能をいつでも利用できます。 
  
さまざまな機能のサブセットを取得するには、Microsoft 365 のクラウドのみの展開、またはシングルサインオンと Active Directory フェデレーションサービス (AD FS) を使用したハイブリッドセットアップのどちらを使用するかによって異なります。 
  
|**Microsoft 365 を管理する場所**|**MFA の第 2 要素のオプション**|
|:-----|:-----|
|クラウドのみ  <br/> |Azure Active Directory MFA (テキストまたは電話)  <br/> |
|ハイブリッド セットアップ、オンプレミスで管理  <br/> | ユーザー ID をオンプレミスで管理する場合、次のような選択肢があります。  <br/>  物理または仮想スマート カード (AD FS)  <br/> [Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (AD FS 用モジュール)  <br/>  Azure AD MFA  <br/> |
   
  
次の図は、最新の Windows 版 Office 2013 のデバイス アプリで MFA を使用してユーザーがどのようにサインインするかを示しています。 Office 2013 デバイス アプリは、[Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) を使用して多要素認証をサポートしています。 Azure AD は、ユーザーがサインインする Web ページをホストします。 ID プロバイダーは、Azure AD の場合も、AD FS などのフェデレーション ID プロバイダーの場合もあります。 フェデレーション ユーザーを認証する場合は、次の手順に従います。
  
1. Azure AD は、組織のレコードの id プロバイダーによってホストされているサインイン web ページにユーザーをリダイレクトします。 この ID プロバイダーは、ユーザーのサインイン名に指定されたドメインに基づいて決定されます。
    
2. ユーザーは、自分のデバイスに表示されたサインイン用の Web ページでサインインを行います。 
    
3. サインインが正常に完了すると、ID プロバイダーから Azure AD にトークンが返されます。
    
4. Azure AD は、Office デバイスアプリに対して JSON Web Token (JWT) を返し、デバイスアプリは、Microsoft 365 を使用して JWT を使用して認証されます。 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Office 2013 クライアントアプリの要件

Office 2013 クライアント アプリで MFA を有効にするには、[クイック実行ベースのインストール](#click-to-run-based-installations)か、[MSI ベースのインストール](#msi-based-installations)かに基づいて、次のソフトウェアがインストールされている必要があります (以下に記載されているバージョンまたはそれ以降のバージョン)。
  
Office のインストールがクイック実行または MSI ベースかどうかを判断するには、次を実行します。
  
1. Outlook 2013 を起動します。
    
2. [**ファイル**] メニューの [ **Office アカウント**] をクリックします。
    
3. Outlook 2013 のクイック実行インストールの場合、[ **更新オプション**] アイテムが表示されます。 MSI ベースのインストールの場合、[ **更新オプション**] アイテムは表示されません。 
    
    ![Office 2013 のインストールがクイック実行または MSI ベースかどうかを確認する方法](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

詳細については、「[モダン認証 wiki の FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)」の記事を参照してください。
  
### <a name="click-to-run-based-installations"></a>クイック実行ベースのインストール

クイック実行ベースのインストールの場合、次のソフトウェアがインストールされている必要があります。ファイルのバージョンは、以下のファイルバージョンになります。 ファイル バージョンが記載されているバージョンよりも古い場合は、次の手順に従って更新します。
  
|**ファイル名**|**パスをコンピューターにインストールする**|**ファイル バージョン**|
|:-----|:-----|:-----|
|MSO.DLL.ライブラリ  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|CSI.ライブラリ  <br/> |CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|ADAL.ライブラリ  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |可変  <br/> |
   
### <a name="msi-based-installations"></a>MSI ベースのインストール

MSI ベースのインストールの場合、次のソフトウェアがインストールされている必要があります (以下に記載されているファイル バージョンまたはそれ以降のファイル バージョン)。ファイル バージョンが記載されているバージョンよりも古い場合は、サポート技術情報の更新記事の列のリンクを使用して更新します。
  
|**ファイル名**|**パスをコンピューターにインストールする**|**更新プログラムを取得する場所**|**バージョン**|
|:-----|:-----|:-----|:-----|
|MSO.DLL.ライブラリ  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|CSI.ライブラリ  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|ADAL.ライブラリ  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |該当しない  <br/> |
   
## <a name="enable-mfa"></a>MFA を有効にする

サブスクリプションで MFA を有効にするには、次の手順を実行します。
  
1. 必要に応じ[て、Windows デバイスで Office 2013 の先進認証を有効](enable-modern-authentication.md)にします。
    
  - サードパーティのディレクトリ サービスを使用して Azure MFA をセットアップします。
    
    このプログラムに受け入れられる特定の id プロバイダーの情報については[、「Azure 多要素認証」および「サードパーティ VPN ソリューションを使用した高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。 
    
2. [Microsoft 365 用の多要素認証をセットアップする](set-up-multi-factor-authentication.md)
    
3. 個人ユーザーに、MFA によるサインイン方法を指示します。 [2 段階認証で Microsoft 365 にサインイン](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)します。

> [!IMPORTANT]
> 先進認証が有効になっていない Office 2013 が実行されているデバイスをユーザーが使用している場合、ユーザーに対して Azure AD MFA を有効にしても、それらのデバイスではアプリケーション パスワードを使用する必要があります。 アプリケーション パスワード、パスワードを使用するタイミング、場所、方法については、「[Azure Multi-Factor Authentication でのアプリケーション パスワード](https://go.microsoft.com/fwlink/p/?LinkId=528178)」を参照してください。
  
## <a name="faq"></a>FAQ

[Wiki の記事「先進認証についてよく寄せられる質問」](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a>既知の問題

[Office 2013 および Microsoft 365 Apps for enterprise モダン authentication: オンボードの前に知っておくべきこと](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Azure Multi-Factor Authentication のトラブルシューティング**
  
「[Azure Multi-Factor Authentication についてよく寄せられる質問](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)」を参照してください。
  
[AD FS を運用している組織のモダン認証によるサインイン問題のトラブルシューティング](https://support.microsoft.com/kb/3052203/)
  
 **代替 ID が機能しない場合の対応策:**
  
[How to use PowerShell to fix duplicate UPN (PowerShell を使用してユーザー プリンシパル名の重複を修正する方法)](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[ユーザー プリンシパル名の重複を修正するためのスクリプト](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **クライアント アクセスのフィルタリング:**
  
[エンタープライズモダン認証およびクライアントアクセスフィルターポリシー用の Office 2013 および Microsoft 365 アプリ: オンボードの前に知っておくべきこと](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **MFA をサポートするアプリ**
  
|**Windows**|**Mac**|**iOS**|**Android スマートフォン**|**Android タブレット**|
|:-----|:-----|:-----|:-----|:-----|
|Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013、Skype for Business の先進認証は、このリリースでサポートされています。  <br/> |Word 2016 for Mac、Excel 2016 for Mac、PowerPoint 2016 for Mac の先進認証は、このリリースでサポートされています。  <br/> |Word for iPad、Excel for iPad、PowerPoint for iPad の先進認証は、このリリースでサポートされています。  <br/> |Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。  <br/> |Word for Android、Excel for Android、PowerPoint for Android の先進認証は、このリリースでサポートされています。  <br/> |
|Outlook 2013 と Outlook 2016 の先進認証は、このリリースでサポートされています。  <br/> |Outlook 2016 for Mac の先進認証は、このリリースでサポートされています。  <br/> |iPad 版 Outlook の先進認証は、このリリースでサポートされています。  <br/> |||
   

