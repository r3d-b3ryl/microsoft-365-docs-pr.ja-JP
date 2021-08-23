---
title: データの移行中および移行後
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: データ移動は、Microsoft がテナントのサービスと関連データを新しいデータセンター geo に移動するときに発生するバック エンド操作です。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d2c78ace4fb25d060ecaeab96903ba577a1d7316
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58394398"
---
# <a name="during-and-after-your-data-move"></a>データの移行中および移行後

データの移行は、エンドユーザーへの影響を最小限に抑えたバックエンドの操作です。 Microsoft が各サービスとお客様のテナントの関連データを新しいデータセンター geo に移動する際には、何も行う必要はありません。 データの転送および検証は事前にバックグラウンドで行われ、ユーザーへの影響は最小限に抑えられます。
  
> [!NOTE]
> 移動はサービスごとに、異なる時間に行われます。結果として、サービスごとに異なる時間に、説明されているような機能制限がかかります。 
  
各チャット サービスMicrosoft 365、オンライン、およびチャット サービスの完了時にExchange Onlineメッセージ センター SharePoint確認Teams確認してください。 次の表に示すように、登録期間が終了した後、最大 24 か月かかる場合、保存中の主要な顧客データが新しいデータセンター geo に移行します。   

|**サインアップ国を持つお客様**|**完了したすべての移動**|
|:-----|:-----|
|オーストラリア、ニュージーランド、フィジー  <br/> |2022 年 7 月 1 日  <br/> |
|日本  <br/> |2022 年 7 月 1 日  <br/> |
|インド  <br/> |2022 年 7 月 1 日  <br/> |
|カナダ  <br/> |2022 年 7 月 1 日  <br/> |
|韓国  <br/> |2022 年 7 月 1 日  <br/> |
|英国  <br/> |2022 年 7 月 1 日  <br/> |
|フランス  <br/> |2022 年 7 月 1 日  <br/> |
|アラブ首長国連邦  <br/> |2022 年 7 月 1 日  <br/> |
|南アフリカ  <br/> |2022 年 7 月 1 日  <br/> |
|スイス、リヒテンシュタイン  <br/> |2022 年 7 月 1 日  <br/> |
|ノルウェー  <br/> |2022 年 11 月 1 日  <br/> |
|ドイツ  <br/> |2023 年 5 月 1 日  <br/> |
|ブラジル  <br/> |2023 年 6 月 1 日  <br/> |

## <a name="exchange-online"></a>Exchange Online

各ユーザーをシングル テナントの新しいデータセンター geo に移動するのに時間がかかるため、移動中は一部のユーザーが古いデータセンター geo のまま、他のユーザーは新しいデータセンター geo という状態になります。 つまり、複数のメールボックスへのアクセスを伴う一部の機能は、移動プロセスの期間中に完全に機能しない可能性があります。この機能は、数週間前に発生する可能性があります。 該当する機能については、この後のセクションで取り上げます。
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Outlook Web Access で "共有フォルダー" を開く

一部のユーザーは、Outlook Web Access で "共有フォルダー" 機能を使用して、別のメールボックスから共有メール フォルダー (ユーザーが読み取りまたは書き込みアクセス許可を持つフォルダー) を開きます。次の表に、メールボックスの移動中に、共有フォルダーへのアクセス権がどのように動作するかを取り上げます。共有メールボックスへのフル アクセス許可があるユーザーは、移動中に Outlook Web Access を使用してメールボックスを開くことができます。 
  
|**構成**|**説明**|
|:-----|:-----|
|別のメールボックスへのメールボックス フォルダー アクセス許可があるユーザー  <br/> |制限される可能性があります。  <br/> テナントの移動中にユーザー A とメールボックス B が同じ geo になく、ユーザー A が持っているアクセス許可がメールボックス B の特定のフォルダーに対してのみの場合、ユーザー A は Outlook Web Access でメールボックス B のフォルダーを開くことができません。  <br/> 共有フォルダーを追加するには、左側のナビゲーション ウィンドウでユーザー名を右クリックし、 **[共有フォルダーの追加]** を選択します。  <br/> |
|別のメールボックスへのメールボックス フル アクセス許可があるユーザー  <br/> |完全にサポートされます。  <br/> ユーザー A がメールボックス B に対する "フル アクセス" 権限を持っている場合、ユーザー A は Outlook Web Access の左側のナビゲーション パネルで共有フォルダーをクリックして、メールボックス B を示すウィンドウを開きます。 ユーザーは、移動中に Web Access Outlookを使用して共有メールボックスを開き、悪影響を及ぼさずに実行できます。 制限は、メールボックス内のフォルダー レベルの共有だけに適用されます。           |
  
## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online を移行すると、以下のサービスのデータも移行されます。
  
- OneDrive for Business
    
- Microsoft 365ビデオ サービス
    
- Officeで使用する
    
- Microsoft 365 Apps for enterprise
    
- Visio ProのMicrosoft 365
    
SharePoint Online データの移行が完了すると、次に示す影響が現れる可能性があります。
  
### <a name="microsoft-365-video-services"></a>Microsoft 365ビデオ サービス

- ビデオのデータの移動は、SharePoint Online にある残りのコンテンツの移動より時間がかかります。
    
- SharePoint Online のコンテンツを移行すると、ビデオが再生できない時間が生じます。
    
- 以前のデータセンターからコード変換されたコピーを削除し、新しいデータセンターでコードを再変換しています。
    
### <a name="search"></a>検索

SharePoint Online データを移行する過程で、検索インデックスと検索設定を新しい場所に移行します。SharePoint Onlineデータの移行が **完了** するまで、ユーザーは引き続き元の場所でインデックスを利用できます。SharePoint Online データの移行が完了すると、新しい場所で、検索機能によってコンテンツのクロールが自動的に再開されます。これより以降、ユーザーは移行したインデックスを利用できます。移行後に生じたコンテンツの変更は、クロールで反映されるまで移行したインデックスに組み込まれません。SharePoint Online データの移行が完了した直後に結果の鮮度が低いと感じる顧客はほとんどいませんが、その後の 24 時間から 48 時間には一部の顧客が鮮度の低下に気付く可能性があります。 
  
次の検索機能が影響を受けます。
  
- 検索結果と検索 Web パーツ:移行後に生じた変更は、クロールで反映されるまで結果に含まれません。 
    
- Delve:移行後に生じた変更は、クロールで反映されるまで Delve に含まれません。
    
- サイトの人気と検索に関するレポート: 新しい場所での Excel レポートのカウントには、移行した数、および SharePoint Online データの移行完了後に実行された利用状況レポートの数のみが含まれます。中間の期間の数はすべて失われ、回復することはできません。この期間は、通常、2、3 日です。顧客によっては情報が失われている期間が増減することもあります。
    
- ビデオ ポータル:ビデオ ポータルの表示回数と統計情報は Excel レポートの統計情報に基づいているため、ビデオ ポータルの表示回数と統計情報は、Excel レポートと同じ期間失われます。
    
- 電子情報開示:移行中に変更されたアイテムは、クロールで変更が反映されるまでは表示されません。
    
- データ損失防止 (DLP):クロールで変更が反映されるまで、変更されたアイテムに対してポリシーは適用されません。

移行の一環として、既定の地域が変更され、すべての新しいコンテンツが新しい既定の領域に保存されます。 既存のコンテンツは、管理センターの SharePoint Online データの場所に最初に変更された後、最大 90 日間、バックグラウンドで移動します。

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft は、Exchange Online、SharePoint、OneDrive for Businessに加えて、Teams サービス データをローカル データセンターに移行します。

- Teams、プライベート メッセージやチャネル メッセージを含むチャット メッセージを作成します。
- Teamsで使用される画像を表示します。

TeamsファイルはオンラインにSharePointされTeamsチャット ファイルはオンラインにOneDrive for Business。 ボイスメール、予定表、チャット履歴、連絡先は、Exchange Online。 多くの場合、Exchange Online、SharePoint Online、OneDrive for Business は、ローカル データセンター geo の顧客によって既に使用され、対象となる顧客国の Microsoft 365 移行プログラムの一部です。

## <a name="skype-for-business"></a>Skype for Business

Skype for Business移動は使用できなくなりました。  [Skype for Businessオンラインは](/lifecycle/announcements/skype-for-business-online-retirement)2021 年 7 月 31 日に廃止されます。 その後、サービスにアクセスできなくなりました。 
  
## <a name="related-topics"></a>関連項目 
 
[データ移行を申請する方法](request-your-data-move.md)
    
[データ移行についての一般的な FAQ](data-move-faq.yml)
  
[Microsoft Dynamics CRM Online の新しいデータ センター geo](/power-platform/admin/new-datacenter-regions)
  
[Azure のリージョン](https://azure.microsoft.com/regions/)
