---
title: Office for Mac でのネットワーク要求
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: この記事では、アプリケーションが到達しようとしているエンドポイントと URL Office for Mac、および提供されるサービスについて説明します。
ms.openlocfilehash: 477225cf99ead3f5609c8082644293d4ac006603
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091129"
---
# <a name="network-requests-in-office-for-mac"></a>Office for Mac でのネットワーク要求

Office for Mac アプリケーションは、macOS プラットフォームでネイティブ アプリ エクスペリエンスを提供します。 各アプリは、ネットワーク アクセスが利用できない場合の状態など、さまざまなシナリオで動作するように設計されています。 コンピューターがネットワークに接続されると、アプリケーションは一連の Web ベースのサービスに自動的に接続して、強化された機能を提供します。 次の情報では、アプリケーションが到達しようとしているエンドポイントと URL、および提供されたサービスについて説明します。 この情報は、ネットワーク構成の問題のトラブルシューティングやネットワーク プロキシ サーバーのポリシーの設定に役立ちます。 この記事の詳細は、microsoft Windowsを実行しているコンピューターのエンドポイントを含む、[Office 365 URL とアドレス範囲](urls-and-ip-address-ranges.md)に関する記事を補完することを目的としています。 この記事の情報は、特に記載のない限り、2019 for Mac および Office 2016 for Mac Officeにも適用されます。これは、小売店またはボリューム ライセンス契約から 1 回限りの購入として利用できます。 

  
この記事の大部分は、そのエンドポイントによって提供されるサービスまたは機能のネットワーク URL、種類、説明を詳しく説明するテーブルです。 各Office アプリは、サービスとエンドポイントの使用状況が異なる場合があります。 次の表では、次のアプリが定義されています。
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
URL の種類は次のように定義されます。
  
- ST: 静的 - URL はクライアント アプリケーションにハードコーディングされます。
    
- SS: Semi-Static - URL は Web ページまたはリダイレクターの一部としてエンコードされます。
    
- CS: Config Service - URL は、Office Configuration Service の一部として返されます。

    
## <a name="office-for-mac-default-configuration"></a>既定の構成Office for Mac

 **インストールと更新**
  
次のネットワーク エンドポイントは、Microsoft Content Delivery Network (CDN) からOffice for Macインストール プログラムをダウンロードするために使用されます。
  
|**URL**|**型**|**説明**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |聖  <br/> |Microsoft 365インストール ポータルの最新のインストール パッケージにリンク サービスを転送します。  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Content Delivery Network上のインストール パッケージの場所。  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Content Delivery Network上のインストール パッケージの場所。  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |聖  <br/> |Microsoft AutoUpdate の管理制御エンドポイント  <br/> |
   
 **最初のアプリの起動**
  
次のネットワーク エンドポイントは、Office アプリの初回起動時に接続されます。 これらのエンドポイントは、ユーザーに対して強化されたOffice機能を提供し、URL はライセンスの種類 (ボリューム ライセンスのインストールを含む) に関係なく連絡されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |聖  <br/> |'Flighting' 構成 - 機能の明るさと実験を可能にします。  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |聖  <br/> |"Flighting" ネットワーク構成テスト  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |聖  <br/> |"Flighting" ネットワーク構成テスト  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |聖  <br/> |Office Configuration Service - サービス エンドポイントのマスター リスト。  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |聖  <br/> |Office規則テレメトリのダウンロード - テレメトリ サービスにアップロードするデータとイベントについてクライアントに通知します。  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote テレメトリ サービス  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |聖  <br/> |Office テレメトリ アップロード レポート - クライアントで発生した "Heartbeart" イベントとエラー イベントは、テレメトリ サービスにアップロードされます。  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office テンプレート サービス - オンライン ドキュメント テンプレートをユーザーに提供します。  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office テンプレートのダウンロード - PNG テンプレート イメージのStorage。  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office アプリの構成を格納します。  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Document Integration Services Catalog (サービスとエンドポイントの一覧) と Home Realm Discovery。  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Home Realm Discovery v2 のリソース (15.40 以降)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |聖  <br/> |Microsoft AutoUpdate マニフェスト - 利用可能な更新プログラムがあるかどうかを確認する  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft Ajax JavaScript ライブラリ  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |構成とリソースをOfficeするための Wikipedia アプリ。  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Officeの構成とリソースのマップ アプリBing。  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |ユーザーは、Officeの構成とリソースのためにアプリをGraphします。  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |聖  <br/> |OneNoteの新しいコンテンツ。  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |聖  <br/> |OneNoteの新しいコンテンツ。  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |OneNoteの新しいイメージ。  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |聖  <br/> |アプリ内サポート サービス。  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |聖  <br/> |電子メール アカウント検出サービス。  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |聖  <br/> |自動検出のOutlook  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |聖  <br/> |Microsoft 365 サービスのエンドポイントをOutlookします。  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |聖  <br/> |Outlook アドインのアイコン。  <br/> |
   
> [!NOTE]
> Office Configuration Service は、Mac だけでなく、すべてのMicrosoft Office クライアントの自動検出サービスとして機能します。 応答で返されるエンドポイントは半静的であり、その変更は非常にまれですが、引き続き可能です。 
  
 **サインイン**
  
クラウドベースのストレージにサインインすると、次のネットワーク エンドポイントに接続されます。 アカウントの種類に応じて、異なるサービスに連絡する場合があります。 次に例を示します。
  
- **MSA: Microsoft アカウント** - 通常、コンシューマーとリテールのシナリオに使用されます 
    
- **OrgID: 組織アカウント** - 通常、商用シナリオに使用されます 
    
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |聖  <br/> |Windows Authorization Service  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |聖  <br/> |Microsoft 365 Login Service (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |聖  <br/> |Microsoft アカウント ログイン サービス (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft アカウント ログイン サービス ヘルパー (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 ログイン ブランド (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |ロケーター Storageドキュメントと場所  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |最近使用した (MRU) ドキュメント サービス  <br/> |
   
> [!NOTE]
> サブスクリプション ベースのライセンスとリテール ライセンスの場合、両方のサインインによって製品がアクティブ化され、OneDriveなどのクラウド リソースへのアクセスが可能になります。 ボリューム ライセンスのインストールでは、ユーザーは引き続き (既定で) サインインを求められますが、これは、製品が既にアクティブ化されているため、クラウド リソースへのアクセスにのみ必要です。 
  
 **製品のアクティブ化**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションライセンスとリテール ライセンスのライセンス認証に適用されます。 具体的には、ボリューム ライセンスのインストールには適用されません。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office Licensing Service  <br/> |
   
 **新着情報コンテンツ**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションにのみ適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |新しい JSON ページの内容。  <br/> |
   
 **リサーチ ツール**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションにのみ適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Researcher Web Service  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |研究者の静的コンテンツ  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |研究者コンテンツ プロバイダー  <br/> |
   
 **スマート検索**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションとリテール/ボリューム ライセンスの両方のライセンス認証に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |インサイト Web サービス  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery ライブラリ  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |JavaScript ライブラリのサポート  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |インサイト コンテンツ プロバイダー  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |インサイト コンテンツ プロバイダー  <br/> |
   
 **PowerPoint デザイナー**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションにのみ適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Designer Web サービス  <br/> |
   
 **PowerPoint クイックスターター**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションにのみ適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint QuickStarter Web サービス  <br/> |
   
 **笑顔を送る/顔をひそめる**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションとリテール/ボリューム ライセンスの両方のライセンス認証に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |スマイル サービスを送信する  <br/> |
   
 **サポートにお問い合わせください**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションとリテール/ボリューム ライセンスの両方のライセンス認証に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |サポート サービスにお問い合わせください  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |アプリ内サポート サービス  <br/> |
   
 **PDF 形式で保存**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションとリテール/ボリューム ライセンスの両方のライセンス認証に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Word ドキュメント変換サービス (PDF)  <br/> |
   
 **Office アプリ (別名アドイン)**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションとリテール/ボリューム ライセンスの両方のライセンス認証に適用されます(アプリ アドインOffice信頼されている場合)。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Office アプリ ストアの構成  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia アプリのリソース  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing アプリ リソースのマップ  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |アプリ リソースGraphユーザー  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office リダイレクト サービス  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office JavaScript ライブラリ  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Office アプリのテレメトリとレポート サービス  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft Ajax JavaScript ライブラリ  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft Ajax JavaScript ライブラリ  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office JavaScript ライブラリ  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |リソースをサポートする  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |リソースをサポートする  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |リソースをサポートする  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript ライブラリ  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |エラー報告  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |フォント リソース  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |テレメトリ サービス  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |テレメトリ レポート  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store アセット ライブラリ  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia ページのリソース  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia メディア リソース  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia サンドボックス フレーム  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |マップ テンプレート  <br/> |
   
 **リンク保護**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションに対してのみすべてのOffice アプリケーションに適用されます。
  
|**URL**|**型**|**説明**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft セーフ Link Service  <br/> |
   
 **クラッシュ レポート**
  
次のネットワーク エンドポイントは、Microsoft 365 サブスクリプションとリテール/ボリューム ライセンスの両方のライセンス認証のすべてのOffice アプリケーションに適用されます。 プロセスが予期せずクラッシュすると、レポートが生成され、Watson サービスに送信されます。
  
|**URL**|**型**|**説明**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |聖  <br/> |Microsoft エラー 報告サービス  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |聖  <br/> |Office コラボレーション インサイト サービス  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>ネットワーク要求とトラフィックを減らすためのオプション

Office for Macの既定の構成では、機能とマシンを最新の状態に保つという点で、最高のユーザー エクスペリエンスが提供されます。 一部のシナリオでは、アプリケーションがネットワーク エンドポイントに接続できないようにしたい場合があります。 このセクションでは、これを行うためのオプションについて説明します。
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Cloud Sign-InとOffice Add-Insを無効にする
  
ボリューム ライセンスのお客様は、ドキュメントをクラウドベースのストレージに保存するための厳格なポリシーを持っている場合があります。 次のアプリケーションごとの基本設定を設定して、MSA/OrgID サインインを無効にし、Office アドインにアクセスできます。
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

ユーザーがSign-In関数にアクセスしようとすると、ネットワーク接続が存在しないというエラーが表示されます。 この設定ではオンライン製品のアクティブ化もブロックされるため、ボリューム ライセンスのインストールにのみ使用する必要があります。 具体的には、この設定を使用すると、Office アプリケーションが次のエンドポイントにアクセスできなくなります。
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- 上記の 「サインイン」セクションに記載されているすべてのエンドポイント。
    
- 上の 「スマート ルックアップ」セクションに記載されているすべてのエンドポイント。
    
- 上記の「製品のアクティブ化」セクションに記載されているすべてのエンドポイント。
    
- 上記の 「Office アプリ (別名アドイン)」セクションに記載されているすべてのエンドポイント。
    
ユーザーの完全な機能を再確立するには、基本設定を "2" に設定するか、削除します。
  
> [!NOTE]
> この設定では、ビルド 15.25 (160726) 以降Office for Mac必要です。 
  
### <a name="telemetry"></a>テレメトリ
  
Office for Macは、テレメトリ情報を定期的に Microsoft に送信します。 データは "Nexus" エンドポイントにアップロードされます。 テレメトリ データは、エンジニアリング チームが各Office アプリの正常性と予期しない動作を評価するのに役立ちます。 テレメトリには 2 つのカテゴリがあります。
  
- **ハートビート** には、バージョンとライセンスの情報が含まれています。 このデータは、アプリの起動時にすぐに送信されます。 
    
- **使用状況** には、アプリの使用方法と致命的でないエラーに関する情報が含まれています。 このデータは 60 分ごとに送信されます。 
    
Microsoft では、お客様のプライバシーを非常に重視しています。 Microsoft のデータ収集ポリシーについては、以下をご覧 [https://privacy.microsoft.com](https://privacy.microsoft.com)ください。 アプリケーションが "Usage" テレメトリを送信しないようにするには、 **SendAllTelemetryEnabled** 設定を調整できます。 この設定はアプリケーションごとであり、macOS 構成プロファイルを使用するか、ターミナルから手動で設定できます。 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

ハートビート テレメトリは常に送信され、無効にすることはできません。
  
### <a name="crash-reporting"></a>クラッシュ レポート
  
致命的なアプリケーション エラーが発生すると、アプリケーションは予期せず終了し、クラッシュ レポートを "Watson" サービスにアップロードします。 クラッシュ レポートは呼び出し履歴で構成されます。これは、アプリケーションがクラッシュに至るまで処理していた手順の一覧です。 これらの手順は、エンジニアリング チームが失敗した正確な関数とその理由を特定するのに役立ちます。
  
場合によっては、ドキュメントの内容によってアプリケーションがクラッシュすることがあります。 アプリがドキュメントを原因として識別した場合は、ドキュメントを呼び出し履歴と共に送信しても問題ないかユーザーに確認します。 ユーザーは、この質問に対して情報に基づいた選択を行うことができます。 IT 管理者は、ドキュメントの送信に関して厳しい要件を持ち、ユーザーに代わってドキュメントを送信しないという決定を下す場合があります。 ドキュメントの送信を禁止し、ユーザーに対するプロンプトを抑制するには、次の設定を設定できます。
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> **SendAllTelemetryEnabled** が **FALSE** に設定されている場合、そのプロセスのすべてのクラッシュ レポートは無効になります。 使用状況テレメトリを送信せずにクラッシュ レポートを有効にするには、次の設定を設定できます。 ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>更新プログラム
  
Microsoft はOffice for Mac更新プログラムを定期的にリリースします (通常は月に 1 回)。 ユーザーと IT 管理者は、最新のセキュリティ修正プログラムを確実にインストールするために、コンピューターを最新の状態に保つことを強くお勧めします。 IT 管理者がコンピューターの更新プログラムを厳密に制御および管理する必要がある場合は、次の設定を設定して、AutoUpdate プロセスが製品の更新プログラムを自動的に検出して提供できないようにすることができます。
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>ファイアウォール/プロキシを使用して要求をブロックする
  
組織がファイアウォールまたはプロキシ サーバー経由で URL への要求をブロックする場合は、このドキュメントに記載されている URL を許可として構成するか、40X 応答 (403 や 404 など) で一覧表示されているブロックを構成してください。 40 倍の応答により、Office アプリケーションはリソースにアクセスできないことを正常に受け入れ、接続を切断するよりも高速なユーザー エクスペリエンスが提供されます。これにより、クライアントは再試行されます。
  
プロキシ サーバーで認証が必要な場合は、クライアントに 407 応答が返されます。 最適なエクスペリエンスを得るには、NTLM サーバーと Kerberos サーバーを操作するための特定の修正プログラムが含まれているため、Office for Mac ビルド 15.27 以降を使用していることを確認してください。
  
  
## <a name="see-also"></a>関連項目

[Office 365 の URL と IP アドレスの範囲](urls-and-ip-address-ranges.md)

