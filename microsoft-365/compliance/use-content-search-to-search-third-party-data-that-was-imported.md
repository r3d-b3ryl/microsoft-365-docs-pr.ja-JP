---
title: コンテンツ検索を使用してサードパーティのインポートされたデータを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: コンテンツ検索電子情報開示ツールを使用して、クエリを作成してサード パーティのデータ ソースからMicrosoft 365内のメールボックスにインポートされたアイテムを検索します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29c033f7d31aca14b527aa6b7fd83d533a5875e7
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939457"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>コンテンツ検索を使用して、カスタム パートナー コネクタによってインポートされたサード パーティのデータを検索する

Microsoft Purview コンプライアンス ポータルの[コンテンツ検索電子情報開示ツール](content-search.md)を使用して、サード パーティのデータ ソースからMicrosoft 365のメールボックスにインポートされたアイテムを検索できます。 インポートされたすべてのサード パーティのデータ項目を検索するクエリを作成することも、特定のサード パーティのデータ項目を検索するクエリを作成することもできます。 また、クエリ ベースのアイテム保持ポリシーまたはクエリ ベースの電子情報開示ホールドを作成して、サード パーティのデータを保持することもできます。
  
パートナーと協力してサード パーティのデータをインポートする方法と、Microsoft 365にインポートできるサード パーティのデータ型の一覧については、「[パートナーと連携してOffice 365でサード パーティのデータをアーカイブする](work-with-partner-to-archive-third-party-data.md)」を参照してください。

> [!IMPORTANT]
> この記事のガイダンスは、カスタム パートナー コネクタによってインポートされたサード パーティのデータにのみ適用されます。 この記事は、Microsoft コンプライアンス センターのサード パーティ製データ コネクタを使用してインポートされた [サード パーティのデータ](archiving-third-party-data.md#third-party-data-connectors) には適用されません。
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>すべてのサード パーティのデータを検索するクエリを作成する

Office 365にインポートした任意の種類のサード パーティ製データを検索 (または保留) するには、コンテンツ検索のキーワード ボックスのメッセージ プロパティと値のペアを使用するか、クエリ ベースの保留を作成するときに使用`kind:externaldata`します。 たとえば、サード パーティのデータ ソースからインポートされたアイテムを検索し、インポートされたアイテムの Subject プロパティに "contoso" という単語を含めるには、次のクエリを使用します。 
  
```powershell
kind:externaldata AND subject:contoso
```

前のキーワード クエリの例には、subject プロパティが含まれています。 キーワード クエリに含めることができるサード パーティのデータ項目のその他のプロパティの一覧については、「[パートナーと連携して、Office 365でサード パーティのデータをアーカイブする](work-with-partner-to-archive-third-party-data.md#more-information)」の「詳細情報」セクションを参照してください。
  
サード パーティのデータを検索および保持するクエリを作成するときに、条件を使用して検索結果を絞り込むこともできます。 コンテンツ検索クエリの作成の詳細については、「コンテンツ検索 [のキーワード クエリと検索条件」を参照](keyword-queries-and-search-conditions.md)してください。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>特定の種類のサード パーティのデータを検索するクエリを作成する

すべての種類のサード パーティデータを検索する代わりに、コンテンツ検索のキーワード ボックスの値のペアである次のメッセージ *プロパティ* を使用して、指定した種類のサード パーティデータのみを検索するクエリを作成できます。
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

たとえば、Subject プロパティで "contoso" という単語を含む Facebook データを検索するには、次のクエリを使用します。
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

次の表に、検索できるサード パーティのデータ型と、その種類のサード パーティデータを  `itemclass:` 具体的に検索するためにメッセージ プロパティに使用する値を示します。 クエリ構文では大文字と小文字が区別されません。 
  
|**サード パーティのデータ型**|**プロパティの  `itemclass:` 値**|
|:-----|:-----|
|目的  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL with Pivot クライアント  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|アレス  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs プレースホルダー  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|バザーボイス  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|Bittorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|ブラックベリー  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry 通話ログ  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|ブルームバーグ  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg メッセージ  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Bloomberg Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|検索ボックス  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|Gotomypc  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|ホップスター  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM 接続  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|IceChat  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Mind Align  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|Myspace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|ピボット  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS チャット  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|Winmx  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo！  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
