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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: コンテンツ検索電子情報開示ツールを使用して、クエリを作成して、Microsoft 365データ ソースからメールボックスにインポートされたアイテムを検索します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: afed5e519b789baffca4f16b95c842ccfe575b4f
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58507640"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>コンテンツ検索を使用して、カスタム パートナー コネクタによってインポートされたサードパーティのデータを検索する

コンテンツ検索電子情報開示[](content-search.md)ツールを使用して、Microsoft 365 コンプライアンス センターデータ ソースから、Microsoft 365メールボックスにインポートされたアイテムを検索できます。 インポートされたサード パーティのすべてのデータ アイテムを検索するクエリを作成するか、特定のサード パーティのデータ アイテムを検索するクエリを作成できます。 また、クエリ ベースのアイテム保持ポリシーまたはクエリ ベースの電子情報開示保持を作成して、サード パーティのデータを保持することもできます。
  
パートナーと一緒にサード パーティ データをインポートする方法と、Microsoft 365 にインポートできるサード パーティのデータ型の一覧の詳細については、「パートナーと一緒に作業して Office 365 でサード パーティのデータをアーカイブする」[を参照してください](work-with-partner-to-archive-third-party-data.md)。

> [!IMPORTANT]
> この記事のガイダンスは、カスタム パートナー コネクタによってインポートされたサードパーティのデータにのみ適用されます。 この記事は、Microsoft コンプライアンス センターでサード パーティのデータ コネクタ[](archiving-third-party-data.md#third-party-data-connectors)を使用してインポートされるサード パーティのデータには適用されません。
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>すべてのサード パーティのデータを検索するためのクエリの作成

Office 365 にインポートした任意の種類のサードパーティ データを検索 (または保留) するには、コンテンツ検索のキーワード ボックスまたはクエリ ベースの保留リストを作成するときに、メッセージ プロパティと値のペアを使用できます。 `kind:externaldata` たとえば、サードパーティのデータ ソースからインポートされたアイテムを検索し、インポートしたアイテムの Subject プロパティに "contoso" という単語を含むには、次のクエリを使用します。 
  
```powershell
kind:externaldata AND subject:contoso
```

前のキーワード クエリの例には、subject プロパティが含まれています。 キーワード クエリに含めるサードパーティのデータ アイテムのその他のプロパティの一覧については、「パートナーと一緒に作業して、Office 365 でサード パーティのデータをアーカイブする」の「詳細[」セクションを参照してください](work-with-partner-to-archive-third-party-data.md#more-information)。
  
サードパーティのデータを検索および保持するためのクエリを作成する場合は、条件を使用して検索結果を絞り込む方法も使用できます。 コンテンツ検索クエリの作成の詳細については、「コンテンツ検索のキーワード クエリと [検索条件」を参照してください](keyword-queries-and-search-conditions.md)。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>特定の種類のサード パーティ製データを検索するためのクエリの作成

すべての種類のサード パーティ製データを検索する代わりに、コンテンツ検索のキーワード ボックスの値ペアというメッセージ プロパティを使用して、指定した種類のサードパーティ データのみを検索するクエリを作成できます。
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

たとえば、Subject プロパティの "contoso" という単語を含む Facebook データを検索するには、次のクエリを使用します。
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

次の表に、検索できるサード パーティのデータ型と、その種類のサード パーティ データを具体的に検索する message プロパティに使用する値  `itemclass:` を示します。 クエリ構文では大文字と小文字が区別されません。 
  
|**サード パーティ製のデータ型**|**プロパティの  `itemclass:` 値**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL with Pivot クライアント  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs プレースホルダー  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry 通話ログ  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|ブルームバーグ  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg メッセージ  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|ブルームバーグ メッセージング  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
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
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
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
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
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
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
