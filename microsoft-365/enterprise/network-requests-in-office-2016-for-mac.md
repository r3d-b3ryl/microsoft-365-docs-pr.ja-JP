---
title: Office for Mac でのネットワーク要求
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: この記事では、アプリケーションがアクセスしようとするエンドポイントOffice for Mac URL、および提供されるサービスについて説明します。
ms.openlocfilehash: abb744d4ee75b06e66ac6a9aa43c7fd18d8a452f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59177751"
---
# <a name="network-requests-in-office-for-mac"></a>Office for Mac でのネットワーク要求

Office for Macアプリケーションは、macOS プラットフォーム上のネイティブ アプリ エクスペリエンスを提供します。 各アプリは、ネットワーク アクセスが利用できない状態など、さまざまなシナリオで動作するように設計されています。 コンピューターがネットワークに接続されると、アプリケーションは一連の Web ベースのサービスに自動的に接続して、強化された機能を提供します。 次の情報は、アプリケーションが到達しようとするエンドポイントと URL、および提供されるサービスについて説明します。 この情報は、ネットワーク構成の問題をトラブルシューティングし、ネットワーク プロキシ サーバーのポリシーを設定する場合に役立ちます。 この記事の詳細は、Microsoft OFFICE 365[](urls-and-ip-address-ranges.md)を実行しているコンピューターのエンドポイントを含む、URL とアドレス範囲のWindows。 特に説明しない限り、この記事の情報は Office 2019 for Mac および Office 2016 for Mac にも適用されます。これは、小売店からの 1 回限りの購入またはボリューム ライセンス契約を通じて利用できます。 

  
この記事の大部分は、そのエンドポイントによって提供されるサービスまたは機能のネットワーク URL、種類、および説明を詳述する表です。 各アプリのOfficeサービスとエンドポイントの使用状況が異なる場合があります。 次のアプリは、以下の表で定義されています。
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
URL の種類は次のように定義されます。
  
- ST: Static - URL はクライアント アプリケーションにハードコードされています。
    
- SS: Semi-Static - URL は Web ページまたはリダイレクターの一部としてエンコードされます。
    
- CS: Config Service - URL は、サーバー構成サービスの一部Officeされます。

    
## <a name="office-for-mac-default-configuration"></a>Office for Mac既定の構成

 **インストールと更新**
  
次のネットワーク エンドポイントを使用して、Microsoft Office for Macからインストール プログラムをダウンロードContent Delivery Network (CDN)。
  
|**URL**|**型**|**説明**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365インストール ポータルのリンク サービスを最新のインストール パッケージに転送します。  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |インストール パッケージの場所は、Content Delivery Network。  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |インストール パッケージの場所は、Content Delivery Network。  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Microsoft AutoUpdate の管理制御エンドポイント  <br/> |
   
 **最初のアプリの起動**
  
次のネットワーク エンドポイントは、最初の起動時に接続Office アプリ。 これらのエンドポイントは、ユーザー Office機能を強化し、ライセンスの種類 (ボリューム ライセンスのインストールを含む) に関係なく URL に連絡します。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |'Flighting' 構成 - 機能のライトアップと実験が可能です。  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |'Flighting' ネットワーク構成テスト  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |'Flighting' ネットワーク構成テスト  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |OfficeConfiguration Service - サービス エンドポイントのマスター リスト。  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |OfficeRules Telemetry download - テレメトリ サービスにアップロードするデータとイベントについてクライアントに通知します。  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |×  <br/> |CS  <br/> |OneNoteテレメトリ サービス  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Officeテレメトリ アップロードレポート - "Heartbeart" と、クライアントで発生するエラー イベントがテレメトリ サービスにアップロードされます。  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |OfficeTemplate Service - オンライン ドキュメント テンプレートをユーザーに提供します。  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Officeテンプレートのダウンロード - PNG Storageの画像を表示します。  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |アプリのストア構成Officeします。  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Officeドキュメント統合サービス カタログ (サービスとエンドポイントの一覧) と Home Realm Discovery。  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Home Realm Discovery v2 のリソース (15.40 以降)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft AutoUpdate Manifests - 利用可能な更新プログラムが含まれていますか確認する  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft Ajax JavaScript ライブラリ  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |構成とリソースOfficeウィキペディア アプリ。  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing構成とリソースOfficeアプリをマップします。  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |ユーザー Graph構成とリソースOfficeアプリを作成します。  <br/> |
|```https://www.onenote.com/```  <br/> |×  <br/> |ST  <br/> |[新しいコンテンツ] OneNote。  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |×  <br/> |ST  <br/> |ユーザーの新しいOneNote。  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |×  <br/> |SS  <br/> |新しい画像のOneNote。  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |アプリ内サポート サービス。  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |メール アカウント検出サービス。  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook自動情報開示  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |OutlookサービスのMicrosoft 365エンドポイント。  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |アドインOutlookアイコン。  <br/> |
   
> [!NOTE]
> この Office構成サービスは、Mac の場合ではなく、すべてのクライアントMicrosoft Office自動検出サービスとして機能します。 応答で返されるエンドポイントは、変更が非常にまれですが、可能な限り半静的です。 
  
 **サインイン**
  
クラウド ベースのストレージにサインインするときに、次のネットワーク エンドポイントに接続されます。 アカウントの種類に応じて、さまざまなサービスに連絡する場合があります。 例:
  
- **MSA: Microsoft アカウント** - 一般消費者および小売シナリオで使用される 
    
- **OrgID: Organization Account** - 一般に商用シナリオで使用される 
    
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows承認サービス  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365Login Service (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft アカウント ログイン サービス (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft アカウント ログイン サービス ヘルパー (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365ログイン ブランディング (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |ドキュメントと場所のStorageロケーター  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |最近使用した (MRU) ドキュメント サービス  <br/> |
   
> [!NOTE]
> サブスクリプション ベースライセンスとリテール ライセンスの場合は、両方のサインインによって製品がアクティブ化され、ライセンス認証などのクラウド リソースOneDrive。 ボリューム ライセンスのインストールでは、ユーザーはサインインを求めるメッセージが表示されますが (既定では)、製品が既にアクティブ化されているので、クラウド リソースへのアクセスにのみ必要です。 
  
 **製品のライセンス認証**
  
次のネットワーク エンドポイントは、サブスクリプションライセンスMicrosoft 365ライセンス認証に適用されます。 具体的には、ボリューム ライセンスのインストールには適用されません。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office Licensing Service  <br/> |
   
 **新機能コンテンツ**
  
次のネットワーク エンドポイントは、サブスクリプションMicrosoft 365適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |新しい JSON ページの内容  <br/> |
   
 **リサーチ ツール**
  
次のネットワーク エンドポイントは、サブスクリプションMicrosoft 365適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |リサーチ Web サービス  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |研究者静的コンテンツ  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |リサーチ コンテンツ プロバイダー  <br/> |
   
 **スマート検索**
  
次のネットワーク エンドポイントは、サブスクリプションライセンスとMicrosoft 365ライセンス認証の両方に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |インサイトWeb サービス  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery ライブラリ  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |JavaScript ライブラリのサポート  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |インサイトコンテンツ プロバイダー  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |インサイトコンテンツ プロバイダー  <br/> |
   
 **PowerPoint デザイナー**
  
次のネットワーク エンドポイントは、サブスクリプションMicrosoft 365適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPointDesigner Web サービス  <br/> |
   
 **PowerPoint クイックスターター**
  
次のネットワーク エンドポイントは、サブスクリプションMicrosoft 365適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPointQuickStarter Web サービス  <br/> |
   
 **Send a Smile/Frown**
  
次のネットワーク エンドポイントは、サブスクリプションライセンスとMicrosoft 365ライセンス認証の両方に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |スマイル サービスの送信  <br/> |
   
 **サポートに問い合わせ**
  
次のネットワーク エンドポイントは、サブスクリプションライセンスとMicrosoft 365ライセンス認証の両方に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |サポート サービスに問い合わせ  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |アプリ内サポート サービス  <br/> |
   
 **PDF として保存**
  
次のネットワーク エンドポイントは、サブスクリプションライセンスとMicrosoft 365ライセンス認証の両方に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Word ドキュメント変換サービス (PDF)  <br/> |
   
 **Officeアプリ (別名アドイン)**
  
次のネットワーク エンドポイントは、アプリ Microsoft 365が信頼されている場合に、サブスクリプションライセンスとOfficeライセンス認証の両方に適用されます。
  
|**URL**|**アプリ**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Office アプリストアの構成  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia アプリのリソース  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bingアプリ リソースのマップ  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |ユーザー Graphアプリ リソース  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Officeリダイレクト サービス  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |OfficeJavaScript ライブラリ  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |アプリの利用統計情報とレポート Officeサービス  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft Ajax JavaScript ライブラリ  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft Ajax JavaScript ライブラリ  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |OfficeJavaScript ライブラリ  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |サポート リソース  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |サポート リソース  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |サポート リソース  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript ライブラリ  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |エラー報告  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |フォント リソース  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |テレメトリ サービス  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |テレメトリ レポート  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Storeアセット ライブラリ  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia ページのリソース  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia のメディア リソース  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia サンドボックス フレーム  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |マップ テンプレート  <br/> |
   
 **リンク保護**
  
次のネットワーク エンドポイントは、サブスクリプションOfficeのすべてのMicrosoft 365適用されます。
  
|**URL**|**型**|**説明**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft セーフ リンク サービス  <br/> |
   
 **クラッシュレポート**
  
次のネットワーク エンドポイントは、サブスクリプションとOfficeライセンス認証の両方Microsoft 365アプリケーションに適用されます。 プロセスが予期せずクラッシュすると、レポートが生成され、Watson サービスに送信されます。
  
|**URL**|**型**|**説明**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Microsoft Error Reporting Service  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Officeコラボレーション インサイト サービス  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>ネットワーク要求とトラフィックを削減するためのオプション

コンピューターの既定の構成Office for Mac、機能とコンピューターを最新の状態に保つという点で、最高のユーザー エクスペリエンスを提供します。 一部のシナリオでは、アプリケーションがネットワーク エンドポイントに接続しなく場合があります。 このセクションでは、これを行うオプションについて説明します。
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Cloud Sign-InとOffice Add-Ins
  
ボリューム ライセンスのお客様は、クラウド ベースのストレージへのドキュメントの保存に関する厳しいポリシーを持っている可能性があります。 次のアプリケーションごとの基本設定を設定して、MSA/OrgID サインインを無効にし、アドインにアクセスOfficeできます。
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

ユーザーが Sign-In関数にアクセスすると、ネットワーク接続が存在しないというエラーが表示されます。 この基本設定はオンライン製品のライセンス認証もブロックしますので、ボリューム ライセンスのインストールにのみ使用する必要があります。 具体的には、この設定を使用すると、Officeアプリケーションが次のエンドポイントにアクセスできません。
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- 上記の [サインイン] セクションに記載されているすべてのエンドポイント。
    
- 上記の [スマート 参照] セクションに記載されているすべてのエンドポイント。
    
- 上記の [製品のライセンス認証] セクションに記載されているすべてのエンドポイント。
    
- 上記の 「Office (別名アドイン)」セクションに記載されているすべてのエンドポイント。
    
ユーザーの完全な機能を再確立するには、基本設定を '2' に設定するか、削除します。
  
> [!NOTE]
> この基本設定では、Office for Mac 15.25 [160726] 以降をビルドする必要があります。 
  
### <a name="telemetry"></a>テレメトリ
  
Office for Mac一定の間隔でテレメトリ情報を Microsoft に送信します。 データは 'Nexus' エンドポイントにアップロードされます。 テレメトリ データは、エンジニアリング チームが各ユーザーの正常性と予期しない動作を評価するのに役立Office アプリ。 テレメトリには 2 つのカテゴリがあります。
  
- **ハートビートには** 、バージョンとライセンス情報が含まれる。 このデータは、アプリの起動直後に送信されます。 
    
- **利用状況** には、アプリの使用方法と致命的でないエラーに関する情報が含まれています。 このデータは 60 分ごとに送信されます。 
    
Microsoft は、お客様のプライバシーを非常に真剣に受け止めてお客様のプライバシーを保護します。 Microsoft のデータ収集ポリシーについては、 を参照してください [https://privacy.microsoft.com](https://privacy.microsoft.com) 。 アプリケーションが 'Usage' テレメトリを送信しに行かねない場合は **、SendAllTelemetryEnabled** 基本設定を調整できます。 基本設定はアプリケーション単位で、macOS 構成プロファイルを使用するか、ターミナルから手動で設定できます。 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

ハートビートテレメトリは常に送信され、無効にすることはできません。
  
### <a name="crash-reporting"></a>クラッシュレポート
  
致命的なアプリケーション エラーが発生すると、アプリケーションは予期せず終了し、クラッシュ レポートを 'Watson' サービスにアップロードします。 クラッシュ レポートは、アプリケーションがクラッシュに至る処理を行っていたステップの一覧である呼び出しスタックで構成されます。 これらの手順は、エンジニアリング チームが失敗した正確な機能と理由を特定するのに役立ちます。
  
場合によっては、ドキュメントの内容によってアプリケーションがクラッシュすることがあります。 アプリがドキュメントを原因として識別する場合は、ユーザーに対して、通話履歴と共にドキュメントを送信しても問題ない場合は、ユーザーに確認を求めるメッセージが表示されます。 ユーザーは、この質問に対して情報に基づいた選択を行えます。 IT 管理者は、ドキュメントの送信に関する厳しい要件を持ち、ユーザーに代わってドキュメントを送信しないという決定を下す場合があります。 次の基本設定を設定すると、ドキュメントの送信を防止し、ユーザーに対するプロンプトを非表示にできます。
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> **SendAllTelemetryEnabled** が **FALSE** に設定されている場合、そのプロセスのすべてのクラッシュ レポートは無効になります。 使用状況テレメトリを送信せずにクラッシュ レポートを有効にするには、次の基本設定を設定できます。 ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>更新プログラム
  
Microsoft は定期的Office for Mac (通常は月に 1 回) 更新プログラムをリリースします。 ユーザーと IT 管理者は、最新のセキュリティ修正プログラムがインストールされていることを確認するために、コンピューターを最新の状態に保つ必要があります。 IT 管理者がコンピューターの更新プログラムを密接に制御および管理する場合は、AutoUpdate プロセスが製品更新プログラムを自動的に検出して提供しなかからなぐために、次の設定を設定できます。
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>ファイアウォール/プロキシを使用した要求のブロック
  
組織がファイアウォールまたはプロキシ サーバーを介して URL への要求をブロックする場合は、このドキュメントに記載されている URL を許可として構成するか、40X 応答 (403 または 404 など) で一覧表示されるブロックを構成してください。 40X 応答を使用すると、Office アプリケーションはリソースにアクセスできない状態を適切に受け入れ、単に接続を削除するよりも高速なユーザー エクスペリエンスを提供し、クライアントが再試行する原因になります。
  
プロキシ サーバーで認証が必要な場合は、407 応答がクライアントに返されます。 最適なエクスペリエンスを得る場合は、NTLM サーバーと Kerberos サーバーを操作するための特定の修正プログラムが含まれるので、Office for Mac ビルド 15.27 以降を使用してください。
  
  
## <a name="see-also"></a>関連項目

[Office 365 の URL と IP アドレスの範囲](urls-and-ip-address-ranges.md)

